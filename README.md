# Insights-Project
# Projeto de Insights: House Rocket #
   O objetivo desse projeto é fornecer para o time de negócios, uma seleção de imóveis, dadas as melhores condições, para que a empresa possa realizar suas operações de compra e venda. Os insights fornecidos neste projeto visam demonstrar um valor de lucro máximo que a empresa pode obter dado as condições que a mesma pode definir num segundo momento.
## 1. Questão de negócio: ##
   A House Rocket é uma plataforma digital que tem como modelo de negócio, a compra e a venda de imóveis usando a tecnologia para analisar suas melhores oportunidades.
O objetivo do case é fornecer insights para a empresa encontrar as melhores oportunidades de negócio no mercado de imóveis. O CEO da House Rocket gostaria de maximizar a receita da empresa encontrando boas oportunidades de negócio.

   Sua principal estratégia é comprar boas casas em ótimas localizações com preços baixos e depois revendê-las posteriormente a preços mais altos. Quanto maior a diferença entre a compra e a venda, maior o lucro da empresa.
Entretanto, as casas possuem muitos atributos que as tornam mais ou menos atrativas aos compradores e vendedores, e a localização e o período do ano também podem influenciar os preços.

   Desta forma, o Cientista de Dados deverá criar um dashboard online para que o CEO da empresa visualize algumas informações do dataset disponibilizado, bem como possa verificar as sugestões de compra e venda indicada pela análise dos dados.

## 2.	Premissas do Negócio: ## 
   Dentro do processo de entendimento de negócio, exploração dos dados e decisão para fornecer os insights finais, foram adotadas as seguintes premissas:
   
•	Os valores iguais a zero em yr_renovated são casas que nunca foram reformadas;

•	O valor igual a 33 na coluna bathroom foi considerada um erro e por isso foi delatada das análises. Possivelmente poderia ser um erro de digitação, mas por falta dessa clareza, a exclusão foi optada;

•	A coluna price significa o preço que a casa foi ou será comprada pela empresa House Rocket.

## 3.	Planejamento da Solução: ## 

### 3.1 Coleta de Dados ###
    
Os dados foram extraídos do link abaixo, onde constam todos os imóveis em portfólio e disponíveis para a empresa.
https://www.kaggle.com/harlfoxem/housesalesprediction

•	Os dados são de 05/2014 até 05/2015.
•	A definição para cada um dos atributos encontra-se abaixo:

Dicionário de Dados

Incluir tabela

### 3.2 Limpeza de Dados ###
### 3.3 Análise Exploratória ###

•	Estatísticas descritivas:

Incluir tabela

•	Novas features:

o	constrution: ano de construção maior ou menor que 1955

o	basement: imóvel com ou sem porão

o	season: estação do ano da venda do imóvel

o	waterfront: vista ou não para água

o	renovated: imóvel foi ou não reformado

o	describe_condition: descrição da condição do imóvel, baseado no classificação assumida no item 1.4 deste ReadMe

o	status: indica se o imóvel deve ou não ser comprado

### 3.4 Aplicativo em Nuvem ###
Dado a necessidade de visualização dos imóveis foi elaborado um painel onde deve conter:

•	Quais propriedades a empresa deve comprar.

•	Uma visualização do mapa com as propriedades disponíveis.

•	Uma visão de tabela com filtros de atributos.

•	Lucro esperado de cada propriedade.

## 4.	Principais Insights ##

### H1 -Imóveis com vista para a água são em média mais caros ###

Inserir gráfico

Resultado: Verdadeiro

### H2 - Imóveis com data de construção menor que 1955 são em média mais baratos ####

Inserir gráfico

Resultado: Falso

### H3 - Imóveis sem porão são maiores do que imóveis com porão ###

Resultado: Verdadeira

### H4 - Houve crescimento do preço médio dos imóveis YoY ( Year over Year )###

Resultado: Falsa 

### H5 - Imóveis com mais quartos são em média mais caros ###

Resultado: Verdadeiro

## 5.	Principais Resultados: ## 

### 5.1	Dashboard de Visualização ###

O dashboard construído no streamlit com os resultados e as análises pode ser conferido através do link: 

### 5.2	Retorno Financeiro ###

Após toda a exploração e análise feita e seguindo as regras de negócio de venda definidas, os resultados financeiros foram os seguintes:








