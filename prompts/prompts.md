
# Prompts utilizados na atividade

## Prompt 1 - Geração de cenários de integração

**Objetivo:** gerar cenários positivos e negativos para testar a comunicação entre a API de Pedidos e a API de Estoque.

**Prompt utilizado:**

Atue como um engenheiro de testes de software especializado em testes de integração.

Considere um sistema composto por dois serviços REST:

1. API de Pedidos: recebe solicitações de compra.
2. API de Estoque: verifica a disponibilidade dos produtos e atualiza as quantidades após a confirmação do pedido.

Gere pelo menos 8 casos de teste de integração, incluindo cenários de sucesso e falha.

Considere situações como:
- Pedido realizado com sucesso.
- Produto sem estoque.
- Produto inexistente.
- Serviço de estoque indisponível.
- Falha de comunicação entre as APIs.
- Erro na atualização do estoque.
- Dados inválidos.
- Requisição duplicada.

Para cada caso, apresente:
- ID do teste.
- Nome do cenário.
- Objetivo.
- Pré-condições.
- Passos para execução.
- Resultado esperado.

Organize a resposta em formato de tabela.

## Prompt 2 - Geração de dados de teste e validação de erros

**Objetivo:** criar dados variados para verificar a comunicação entre os serviços.

**Prompt utilizado:**

Atue como um analista de qualidade de software (QA).

Considerando a integração entre uma API REST de Pedidos e uma API REST de Estoque, gere dados de teste para validar a comunicação entre os dois serviços.

Crie pelo menos 8 exemplos, contemplando:
- Dados válidos.
- Campos obrigatórios ausentes.
- Quantidade igual a zero.
- Quantidade negativa.
- Produto inexistente.
- Estoque insuficiente.
- Identificador de pedido duplicado.
- Falha ou timeout na comunicação com o serviço de estoque.

Para cada exemplo, informe:
- Dados de entrada.
- Situação que está sendo testada.
- Resposta ou comportamento esperado.
- Qual problema o teste pretende identificar.

Não invente endpoints ou contratos específicos que não foram fornecidos. Quando necessário, indique que o comportamento depende das regras de negócio definidas pelo sistema.
