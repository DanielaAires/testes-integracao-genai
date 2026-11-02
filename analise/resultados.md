
# Análise dos Resultados

## 1. Influência do Prompt 1 - Geração de cenários de integração

O primeiro prompt foi utilizado para gerar cenários de integração entre a API de Pedidos e a API de Estoque.

Os resultados contribuíram para ampliar a cobertura dos testes, identificando situações positivas e negativas.

Entre os principais cenários identificados estão:

- Pedido realizado com sucesso.
- Produto sem estoque.
- Produto inexistente.
- Indisponibilidade de serviços.
- Falhas na comunicação entre as APIs.
- Erros na atualização do estoque.
- Dados inválidos.
- Requisições duplicadas.

A utilização de instruções específicas sobre objetivo, pré-condições, passos e resultados esperados tornou os casos de teste mais organizados e compreensíveis.

## 2. Influência do Prompt 2 - Geração de dados de teste e validação de erros

O segundo prompt teve como objetivo gerar dados variados para verificar o comportamento da integração em diferentes situações.

Os resultados permitiram contemplar dados válidos e inválidos, incluindo quantidades negativas, campos obrigatórios ausentes, produtos inexistentes, estoque insuficiente e situações de timeout.

Esse tipo de prompt contribuiu para aumentar a diversidade dos testes, permitindo avaliar não apenas o funcionamento normal da integração, mas também o tratamento de situações inesperadas.

## 3. Ajustes realizados nos prompts

Durante a experimentação, foi possível observar que prompts genéricos tendem a produzir respostas mais superficiais.

Para melhorar os resultados, foram realizados os seguintes ajustes:

- Definição do papel da IA como engenheiro de testes ou analista de QA.
- Descrição detalhada dos serviços envolvidos na integração.
- Inclusão de exemplos de situações positivas e negativas.
- Especificação da quantidade mínima de casos de teste.
- Solicitação de objetivo, pré-condições, passos e resultados esperados.
- Organização das respostas em tabelas.
- Orientação para não inventar endpoints ou regras de negócio não informados.

### Exemplo de refinamento de prompt

**Prompt inicial:**

"Gere casos de teste para uma integração entre uma API de Pedidos e uma API de Estoque."

Esse comando é muito amplo e não especifica quais situações devem ser avaliadas nem como os resultados devem ser apresentados.

**Prompt ajustado:**

"Atue como um engenheiro de testes de software. Considere uma API de Pedidos integrada a uma API de Estoque. Gere pelo menos oito casos de teste positivos e negativos, incluindo produto sem estoque, produto inexistente, falha de comunicação e pedido duplicado. Para cada caso, informe objetivo, pré-condições, passos de execução e resultado esperado. Organize os resultados em tabela e não invente regras de negócio."

**Resultado observado:**

O prompt ajustado apresentou instruções mais claras, permitindo obter cenários mais diversificados, organizados e adequados à finalidade dos testes de integração.

## 4. Avaliação geral

A utilização da GenAI demonstrou potencial para auxiliar na elaboração de suítes de testes de integração.

O principal benefício observado foi a capacidade de sugerir diferentes situações de teste em pouco tempo, incluindo cenários negativos que poderiam não ser considerados inicialmente.

O primeiro prompt contribuiu principalmente para a identificação e organização dos cenários de integração.

O segundo prompt contribuiu para diversificar os dados de entrada e explorar diferentes situações de validação e tratamento de erros.

Entretanto, os resultados gerados precisam ser revisados por um profissional de qualidade de software, pois a IA pode sugerir comportamentos que não correspondem às regras reais do sistema.

## 5. Conclusão

A experiência demonstrou que a qualidade dos resultados gerados por GenAI depende diretamente da clareza e do nível de detalhamento dos prompts.

Quanto mais específico o contexto fornecido, melhores tendem a ser os cenários produzidos.

Portanto, a GenAI pode atuar como copiloto no processo de testes de integração, aumentando a produtividade, ampliando a diversidade dos cenários e contribuindo para uma cobertura de testes mais abrangente.

Concluo que a inteligência artificial é uma ferramenta de apoio importante, mas não substitui a análise crítica e a validação dos casos de teste por profissionais da área.
