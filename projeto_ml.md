# Projeto de Previsão de Estoque com Machine Learning

## Introdução

Neste projeto, nosso objetivo é utilizar técnicas de Machine Learning para prever o estoque de um determinado produto. Utilizaremos o SageMaker Canvas para construir, treinar e analisar nosso modelo de previsão.

## Seleção do Dataset

Para este projeto, selecionamos o dataset de preço variável e renovação de estoque. Este dataset foi escolhido porque contém informações relevantes sobre as flutuações de preços e os padrões de renovação de estoque, além de incluir dados sobre feriados no Brasil, que podem influenciar nas vendas e, consequentemente, nos níveis de estoque. Abaixo estão as principais características do dataset:

- Tamanho: 1000 (número de linhas) e 4 (colunas)
- Principais variáveis: preço, quantidade em estoque, data de renovação, feriados

## Construção e Treinamento do Modelo

Importamos o dataset no SageMaker Canvas e configuramos as variáveis de entrada e saída da seguinte forma:

- Variáveis de entrada: preço, data de renovação, feriados
- Variável de saída: quantidade em estoque

Iniciamos o treinamento do modelo, que levou aproximadamente 20 minutos. 

## Análise do Modelo

Após o treinamento, examinamos as seguintes métricas de performance:

- **Avg. wQL (Weighted Quantile Loss):** 0.344
- **MAPE (Mean Absolute Percentage Error):** 0.936
- **WAPE (Weighted Absolute Percentage Error):** 0.569
- **RMSE (Root Mean Squared Error):** 34.950
- **MASE (Mean Absolute Scaled Error):** 0.832

As principais características que influenciam as previsões são:

- Preço
- Feriados
- Data de renovação

Realizamos os seguintes ajustes no modelo para melhorar a performance:

- Ajustamos os parâmetros de treinamento para melhorar a acurácia das previsões, especialmente em períodos de feriados.

## Previsão

Utilizamos o modelo treinado para fazer previsões de estoque. Os resultados foram exportados e analisados, conforme descrito abaixo:

- As previsões mostraram uma variação considerável nos níveis de estoque em função dos preços e dos feriados. Durante os períodos de feriados, notou-se um aumento nas vendas, resultando em uma redução dos níveis de estoque. A renovação de estoque após os feriados também mostrou um padrão significativo, com um aumento nos níveis de estoque.

As principais conclusões e insights obtidos a partir das previsões são:

- **Influência dos Feriados:** Os feriados têm um impacto significativo nas vendas e nos níveis de estoque. Durante os feriados, a demanda por produtos aumenta, resultando em uma redução dos níveis de estoque.
- **Padrões de Renovação:** A renovação de estoque após os feriados é crucial para manter a disponibilidade de produtos. As empresas devem planejar suas renovações de estoque com base nos padrões históricos e nas previsões de demanda.
- **Variação de Preços:** A variação de preços também influencia os níveis de estoque. Preços mais baixos tendem a aumentar a demanda, enquanto preços mais altos podem reduzir a demanda e manter os níveis de estoque mais altos.

## Conclusão

Em resumo, nosso modelo de Machine Learning conseguiu prever o estoque com uma precisão razoável, considerando as métricas de performance analisadas. O modelo destacou a importância de considerar feriados e variações de preços ao planejar os níveis de estoque. Para futuras iterações, poderíamos explorar outros fatores que podem influenciar as previsões, como promoções, sazonalidade de produtos e comportamentos específicos do consumidor.

Com estas informações, as empresas podem melhorar suas estratégias de gestão de estoque, garantindo a disponibilidade de produtos durante períodos de alta demanda e otimizando os níveis de estoque para minimizar custos.


