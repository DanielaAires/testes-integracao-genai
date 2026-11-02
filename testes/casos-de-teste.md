
# Casos de Teste de Integração Gerados por GenAI

## 1. Cenário de integração

O cenário considerado envolve a comunicação entre dois serviços REST:

- API de Pedidos: responsável pelo registro de pedidos.
- API de Estoque: responsável pela consulta e atualização da disponibilidade dos produtos.

Os testes têm como objetivo verificar se os serviços se comunicam corretamente e se tratam adequadamente situações de sucesso e falha.

Os dados apresentados são fictícios e os resultados esperados representam o comportamento proposto para o cenário.

---

## 2. Casos de teste - Geração de cenários de integração

### CT01 - Pedido realizado com sucesso

**Objetivo:** verificar se um pedido é registrado corretamente quando existe estoque disponível.

**Pré-condições:** produto cadastrado e quantidade disponível no estoque.

**Passos para execução:**
1. Enviar uma solicitação de pedido com produto válido.
2. Informar uma quantidade disponível no estoque.
3. Verificar a comunicação entre a API de Pedidos e a API de Estoque.
4. Consultar o resultado do pedido e a quantidade em estoque.

**Resultado esperado:** pedido registrado com sucesso e estoque atualizado conforme a quantidade solicitada.

### CT02 - Produto sem estoque

**Objetivo:** verificar o comportamento do sistema quando não existe quantidade disponível.

**Pré-condições:** produto cadastrado com estoque igual a zero.

**Passos para execução:**
1. Enviar uma solicitação de pedido.
2. Informar o produto sem estoque.
3. Verificar a resposta da API de Estoque.
4. Consultar o estado do pedido.

**Resultado esperado:** pedido não confirmado e estoque mantido sem alterações.

### CT03 - Produto inexistente

**Objetivo:** verificar se o sistema identifica produtos que não estão cadastrados.

**Pré-condições:** identificador de produto inexistente.

**Passos para execução:**
1. Enviar uma solicitação de pedido.
2. Informar um identificador de produto inválido.
3. Verificar a resposta da API de Estoque.

**Resultado esperado:** operação rejeitada e indicação de produto não encontrado.

### CT04 - Serviço de estoque indisponível

**Objetivo:** verificar o tratamento de falhas quando a API de Estoque está indisponível.

**Pré-condições:** serviço de estoque fora do ar.

**Passos para execução:**
1. Enviar uma solicitação de pedido.
2. Simular a indisponibilidade do serviço de estoque.
3. Verificar o comportamento da API de Pedidos.

**Resultado esperado:** falha tratada adequadamente, sem confirmação indevida do pedido.

### CT05 - Falha de comunicação entre as APIs

**Objetivo:** verificar o comportamento da integração quando ocorre timeout na comunicação.

**Pré-condições:** comunicação entre os serviços interrompida ou com tempo de resposta excedido.

**Passos para execução:**
1. Enviar uma solicitação de pedido.
2. Simular atraso ou interrupção na comunicação.
3. Verificar o tratamento da falha.
4. Consultar o estado do pedido.

**Resultado esperado:** erro identificado e operação tratada sem gerar inconsistência entre os serviços.

### CT06 - Erro na atualização do estoque

**Objetivo:** verificar o comportamento do sistema quando ocorre uma falha durante a atualização do estoque.

**Pré-condições:** produto disponível e falha simulada na operação de atualização.

**Passos para execução:**
1. Enviar uma solicitação de pedido válida.
2. Permitir a consulta de disponibilidade.
3. Simular uma falha na atualização do estoque.
4. Verificar o estado final do pedido e do estoque.

**Resultado esperado:** sistema deve tratar a falha e evitar confirmar uma operação sem garantir a consistência dos dados, utilizando o mecanismo de compensação definido pela arquitetura.

### CT07 - Dados inválidos

**Objetivo:** verificar se a API rejeita informações inválidas.

**Pré-condições:** sistema disponível para receber requisições.

**Passos para execução:**
1. Enviar uma solicitação de pedido com quantidade negativa.
2. Verificar a validação dos dados.
3. Consultar se houve alteração no estoque.

**Resultado esperado:** requisição rejeitada e estoque sem alterações.

### CT08 - Pedido duplicado

**Objetivo:** verificar se o sistema evita o processamento duplicado de uma mesma solicitação.

**Pré-condições:** existência de um pedido já processado com determinado identificador.

**Passos para execução:**
1. Enviar uma solicitação de pedido.
2. Reenviar a mesma solicitação utilizando o mesmo identificador.
3. Verificar o processamento realizado pelos serviços.
4. Consultar o pedido e o estoque.

**Resultado esperado:** evitar a duplicidade de processamento e impedir que o estoque seja decrementado duas vezes.

---

## 3. Casos de teste - Dados e validação de erros

| ID | Dados de entrada | Situação | Resultado esperado |
|---|---|---|---|
| DT01 | Produto: 101 / Quantidade: 2 | Dados válidos | Processamento permitido se houver estoque |
| DT02 | Produto: vazio / Quantidade: 2 | Campo obrigatório ausente | Erro de validação |
| DT03 | Produto: 101 / Quantidade: 0 | Quantidade zero | Requisição rejeitada |
| DT04 | Produto: 101 / Quantidade: -5 | Quantidade negativa | Requisição rejeitada |
| DT05 | Produto: 9999 / Quantidade: 1 | Produto inexistente | Produto não encontrado |
| DT06 | Produto: 101 / Quantidade: 1000 | Estoque insuficiente | Pedido não confirmado |
| DT07 | Pedido: PED001 / Identificador repetido | Requisição duplicada | Evitar processamento duplicado |
| DT08 | Serviço de estoque sem resposta | Timeout | Falha tratada sem inconsistência |

---

## 4. Considerações sobre os testes

Os casos de teste foram elaborados com auxílio de uma LLM a partir dos prompts apresentados neste repositório.

Os cenários contemplam situações positivas e negativas, permitindo avaliar a comunicação entre os serviços, a validação dos dados e o tratamento de erros.

Os testes são propostas documentadas e ainda não foram executados em APIs reais.

A execução prática dependeria da implementação dos serviços, dos contratos de API e das regras de negócio estabelecidas pelo sistema.
