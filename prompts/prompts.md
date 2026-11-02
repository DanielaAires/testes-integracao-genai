
# Prompts utilizados na atividade

## Ferramenta utilizada

- Ferramenta: ChatGPT
- Modelo: GPT-6
- Finalidade: apoiar a elaboração de cenários e dados para testes de integração.

## Cenário utilizado

Foi considerado um sistema composto por dois serviços REST:

1. API de Pedidos: responsável por receber e registrar pedidos.
2. API de Estoque: responsável por verificar a disponibilidade dos produtos e atualizar as quantidades após a confirmação do pedido.

O objetivo é avaliar a comunicação entre os serviços, considerando situações de sucesso e possíveis falhas.

---

## Prompt 1 - Geração de cenários de integração

**Objetivo:** gerar cenários positivos e negativos para testar a comunicação entre a API de Pedidos e a API de Estoque.

**Prompt utilizado:**

Atue como um engenheiro de testes de software especializado em testes de integração.

Considere um sistema composto por dois serviços REST:

1. API de Pedidos: recebe solicitações de compra.
2. API de Estoque: verifica a disponibilidade dos produtos e atualiza as quantidades após a confirmação do pedido.

Gere pelo menos 8 casos de teste de integração, incluindo cenários positivos e negativos.

Considere as seguintes situações:

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

Não invente endpoints, códigos HTTP ou regras de negócio que não foram informados. Quando necessário, indique as premissas adotadas.

---

## Prompt 2 - Geração de dados de teste e validação de erros

**Objetivo:** criar dados variados para verificar a comunicação entre os serviços.

**Prompt utilizado:**

Atue como um analista de qualidade de software (QA).

Considerando a integração entre uma API REST de Pedidos e uma API REST de Estoque, gere pelo menos 8 exemplos de dados de teste para validar a comunicação entre os dois serviços.

Inclua as seguintes situações:

- Dados válidos.
- Campos obrigatórios ausentes.
- Quantidade igual a zero.
- Quantidade negativa.
- Produto inexistente.
- Estoque insuficiente.
- Identificador de pedido duplicado.
- Falha ou timeout na comunicação com o serviço de estoque.

Para cada exemplo, informe:

- ID do teste.
- Dados de entrada.
- Situação que está sendo testada.
- Comportamento esperado.
- Problema que o teste pretende identificar.

Apresente os resultados em formato de tabela.

Utilize dados fictícios e não invente contratos específicos de API. Quando necessário, indique que o comportamento depende das regras de negócio definidas pelo sistema.

---

## Observação sobre a experimentação

Os dois prompts foram utilizados no ChatGPT para apoiar a elaboração dos cenários e dados de teste documentados neste repositório.

As respostas geradas foram organizadas e revisadas para melhorar a clareza, a cobertura dos cenários e a identificação dos resultados esperados.
