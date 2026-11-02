
# Casos de Teste de Integração Gerados por GenAI

## Cenário

Integração entre uma API de Pedidos e uma API de Estoque.

## 1. Casos de teste - Cenários de integração

| ID | Cenário | Entrada/Situação | Resultado esperado |
|---|---|---|---|
| CT01 | Pedido realizado com sucesso | Produto disponível e quantidade válida | Pedido registrado e estoque atualizado |
| CT02 | Produto sem estoque | Quantidade disponível igual a zero | Pedido recusado e estoque não alterado |
| CT03 | Produto inexistente | ID de produto inválido | Operação recusada com indicação de produto não encontrado |
| CT04 | Serviço de estoque indisponível | API de estoque fora do ar | Erro tratado sem confirmar indevidamente o pedido |
| CT05 | Falha de comunicação | Timeout entre os serviços | Falha registrada e tratamento adequado da operação |
| CT06 | Erro na atualização do estoque | Falha durante a atualização | Pedido não deve ser confirmado sem consistência entre os serviços |
| CT07 | Dados inválidos | Quantidade negativa | Requisição rejeitada pela validação |
| CT08 | Pedido duplicado | Mesmo identificador enviado novamente | Não deve ocorrer duplicidade de processamento |

## 2. Casos de teste - Dados e validação de erros

| ID | Dados de entrada | Situação | Resultado esperado |
|---|---|---|---|
| DT01 | Produto: 101 / Quantidade: 2 | Dados válidos | Processamento permitido se houver estoque |
| DT02 | Produto: vazio / Quantidade: 2 | Produto ausente | Erro de validação |
| DT03 | Produto: 101 / Quantidade: 0 | Quantidade zero | Requisição rejeitada |
| DT04 | Produto: 101 / Quantidade: -5 | Quantidade negativa | Requisição rejeitada |
| DT05 | Produto: 9999 / Quantidade: 1 | Produto inexistente | Produto não encontrado |
| DT06 | Produto: 101 / Quantidade: 1000 | Estoque insuficiente | Pedido não confirmado |
| DT07 | Pedido: identificador repetido | Requisição duplicada | Evitar processamento duplicado |
| DT08 | Serviço de estoque sem resposta | Timeout | Erro tratado sem inconsistência no pedido |

## Observações

Os casos foram elaborados com auxílio de uma LLM e representam cenários propostos para testes de integração.

Os resultados esperados são referências para validação. A execução real depende da implementação das APIs e de seus respectivos contratos.

Os códigos de resposta HTTP e as regras específicas de compensação devem ser definidos conforme a arquitetura do sistema.
