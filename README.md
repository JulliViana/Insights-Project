# Insights-Project
![banner](https://user-images.githubusercontent.com/92406177/141321050-7c0cca61-292e-43c4-aa64-955f86a4fa28.jpg)
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

|      Atributo          |      Descrição                                                                                                                            |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
|     id                 |     Numeração única de identificação de cada   imóvel                                                                                     |
|     date               |     Data da venda da casa                                                                                                                 |
|     price              |     Preço que a casa está sendo vendida pelo   proprietário                                                                               |
|     bedrooms           |     Número de quartos                                                                                                                     |
|     bathrooms          |     Número de banheiros (0.5 = banheiro em   um quarto, mas sem chuveiro)                                                                 |
|     sqft_living        |     Medida (em pés quadrado) do espaço   interior dos apartamentos                                                                        |
|     sqft_lot           |     Medida (em pés quadrado)quadrada do   espaço terrestre                                                                                |
|     floors             |     Número de andares do imóvel                                                                                                           |
|     waterfront         |     Variável que indica a presença ou não de   vista para água (0 = não e 1 = sim)                                                        |
|     view               |     Um índice de 0 a 4 que indica a   qualidade da vista da propriedade. Varia de 0 a 4, onde: 0 = baixa 4 = alta                         |
|     condition          |     Um índice de 1 a 5 que indica a condição   da casa. Varia de 1 a 5, onde:1 = baixo 5 = alta                                           |
|     grade              |     Um índice de 1 a 13 que indica a   construção e o design do edifício. Varia de 1 a 13, onde: 13 = baixo, 7 =   médio e 1113 = alta    |
|     sqft_basement      |     A metragem quadrada do espaço   habitacional interior acima do nível do solo                                                          |
|     yr_built           |     Ano de construção de cada imóvel                                                                                                      |
|     yr_renovated       |     Ano de reforma de cada imóvel                                                                                                         |
|     zipcode            |     CEP da casa                                                                                                                           |
|     lat                |     Latitude                                                                                                                              |
|     long               |     Longitude                                                                                                                             |
|     sqft_livining15    |     Medida (em pés quadrado) do espaço   interno de habitação para os 15 vizinhos mais próximo                                            |
|     sqft_lot15         |     Medida (em pés quadrado) dos lotes de   terra dos 15 vizinhos mais próximo                                                            |

Além do dataset acima citado, foi utilizado um arquivo geojson para a criação de mapas de densidade. A API foi extraída do site ArcGIS Hub.

### 3.2 Limpeza de Dados ###
### 3.3 Análise Exploratória ###

•	Estatísticas descritivas:


|      attributes      |      maximum      |      minimum     |      mean        |      median      |      std         |
|----------------------|-------------------|------------------|------------------|------------------|------------------|
|     price            |     7700000.00    |     75000.00     |     541645.37    |     450000.00    |     367314.32    |
|     bedrooms         |     11.00         |     0.00         |     3.37         |     3.00         |     0.91         |
|     bathrooms        |     8.00          |     0.00         |     2.12         |     2.25         |     0.77         |
|     sqft_living      |     13540.00      |     290.00       |     2082.73      |     1920.00      |     919.14       |
|     sqft_lot         |     1651359.00    |     520.00       |     15136.06     |     7614.00      |     41538.57     |
|     floors           |     3.50          |     1.00         |     1.50         |     1.50         |     0.54         |
|     view             |     4.00          |     0.00         |     0.24         |     0.00         |     0.77         |
|     condition        |     5.00          |     1.00         |     3.41         |     3.00         |     0.65         |
|     grade            |     13.00         |     1.00         |     7.66         |     7.00         |     1.17         |
|     sqft_above       |     9410.00       |     290.00       |     1791.00      |     1560.00      |     829.01       |
|     sqft_basement    |     4820.00       |     0.00         |     291.73       |     0.00         |     442.78       |
|     yr_built         |     2015.00       |     1900.00      |     1971.10      |     1975.00      |     29.38        |
|     yr_renovated     |     2015.00       |     0.00         |     84.73        |     0.00         |     402.43       |
|     sqft_living15    |     6210.00       |     399.00       |     1988.35      |     1840.00      |     685.68       |
|     sqft_lot15       |     871200.00     |     651.00       |     12786.34     |     7620.00      |     27375.41     |


Novas features:

•	constrution: ano de construção maior ou menor que 1955

•	basement: imóvel com ou sem porão

•	season: estação do ano da venda do imóvel

•	waterfront: vista ou não para água

•	renovated: imóvel foi ou não reformado

•	describe_condition: descrição da condição do imóvel, baseado no classificação assumida no item 1.4 deste ReadMe

•	status: indica se o imóvel deve ou não ser comprado

### 3.4 Aplicativo em Nuvem ###

Dado a necessidade de visualização dos imóveis foi elaborado um painel onde deve conter:

•	Quais propriedades a empresa deve comprar.

•	Uma visualização do mapa com as propriedades disponíveis.

•	Uma visão de tabela com filtros de atributos.

•	Lucro esperado de cada propriedade.

## 4.	Principais Insights ##

Os insights podem ajudar o time de negócios na tomada de decisão, insights valiosos podem fazer a diferença entre fazer um bom negócio ou não. Diante disso alguns insights econtrados a partir da analise e exploração dos dados foram:

### H1 -Imóveis com vista para a água são em média mais caros ###

- [x] Resultado: Verdadeiro

![h1](https://user-images.githubusercontent.com/92406177/142739685-f347b739-64b1-425d-b02c-b54e71a6a1bb.jpg)



### H2 - Imóveis com data de construção menor que 1955 são em média mais baratos ####

- [x]  Resultado: Falso

![h2](https://user-images.githubusercontent.com/92406177/142739911-269058a1-2cc4-442d-a295-00ce98da497e.jpg)

### H3 - Imóveis sem porão são maiores do que imóveis com porão ###

- [x]  Resultado: Verdadeira

![h3](https://user-images.githubusercontent.com/92406177/142739991-846c3c95-3c3f-49a1-bc53-23b486256171.jpg)

### H4 - Houve crescimento do preço médio dos imóveis YoY ( Year over Year )###

- [x]  Resultado: Falsa 

![h4](https://user-images.githubusercontent.com/92406177/142740026-4b49e87c-d3c1-44ee-b813-0006b7fc04a3.jpg)

### H5 - Imóveis com mais quartos são em média mais caros ###

- [x]  Resultado: Verdadeiro

![h5](https://user-images.githubusercontent.com/92406177/142740161-4a627267-ac7a-4621-ad5e-7a57e2db25c0.jpg)

## 5.	Resultados Financeiros: ## 

O objetivo desse projeto era fornecer uma lista de imóveis com opções de compra e venda, e consequentemente o lucro máximo que poderá ser obtido se todas as transações ocorrerem. Ou seja, o resultado financeiro apresentado abaixo representa o lucro máximo que pode ser obtido utilizando as recomendações informadas.

| Número de imóveis | Custo total          | Receita de vendas    | Lucro (profit)       |
|-------------------|----------------------|----------------------|----------------------|
| 10.505            | US$ 4.079.586.744.00 | US$ 5.266.225.532.20 | US$ 1.186.638.788.20 |


## 6. Conclusão:

## 7. Referências:

* Python from Zero to DS lessons on [Youtube](https://www.youtube.com/watch?v=1xXK_z9M6yk&list=PLZlkyCIi8bMprZgBsFopRQMG_Kj1IA1WG&ab_channel=SejaUmDataScientist)
* Blog [Seja um Data Scientist](https://sejaumdatascientist.com/os-5-projetos-de-data-science-que-fara-o-recrutador-olhar-para-voce/)
* Dataset House Sales in King County (USA) from [Kaggle](https://www.kaggle.com/harlfoxem/housesalesprediction)


## 8. Tecnologias:

![jupyter](https://user-images.githubusercontent.com/92406177/142740450-cc471f27-9bd0-4a5d-8cae-83f7521e185d.jpg)
![pycharn](https://user-images.githubusercontent.com/92406177/142740468-2df16be5-4e40-4212-83c0-c8df1f761411.jpg)
![python](https://user-images.githubusercontent.com/92406177/142740482-7d45a576-d134-49df-9d1e-d783a9e2f24a.jpg)








