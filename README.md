# Projeto_3
Projeto 3 de Ciências dos Dados. 2019/2

## Introdução
Foi proposto para que os alunos formulassem uma pergunta e que a mesma seja respondida através da análise de um conjunto de dados, empregando técnicas de classificação e regressão para tal análise. O grupo formulou as seguintes perguntas: 

1)Para cada ator atuando em dado filme, qual vai ser a estimativa de faturamento deste filme?

2)Dado um filme pertencente a algum gênero, quais são os atores mais prováveis de estarem desempenhando algum papel no filme?

Em uma primeira avaliação, ambas as perguntas foram consideradas boas para a montagem do projeto, porém com sugestões de técnicas diferentes.
Na primeira foi sugerida Random Forest, Linear Regression e Nearest Neighbors enquanto na segunda foi sugerida CategoricalNB, Decision Trees.

Em um brainstorming final, o grupo decidiu escolher trabalhar em cima do primeiro tema:

_Para cada ator atuando em dado filme, qual vai ser a estimativa de faturamento deste filme?_

### Random Forest

> "A random forest is a meta estimator that fits a number of classifying decision trees on various sub-samples of the dataset and uses averaging to improve the predictive accuracy and control over-fitting."

Random Forest é um método de machine learning que utiliza bagging e decision trees para avaliar e combinar todos os possíveis _outcomes_ de um dataset, sendo assim um dos melhores métodos de classificação e regressão atualmente.

### Linear Regression

Linear Regression é um método que tem como objetivo principal construir um modelo que explica uma variável com base em outras variáveis independentes. Consiste em estimar coeficientes para cada variável explicativa de modo a construir o plano que melhor contempla o conjunto de valores da variável dependente.

### Nearest Neighbors

> "Neighbors-based regression can be used in cases where the data labels are continuous rather than discrete variables. The label assigned to a query point is computed based on the mean of the labels of its nearest neighbors."

Nearest Neighbors é um método que faz a previsão baseado nas características dos valores mais próximos do dataset. Ou seja, o modelo tenta passar o mais próximo possível de todos os dados simultaneamente. No caso, foi utilizado o K-Neighbors, que consiste em utilizar um número inteiro k de neighbors para fazer a estimativa.

## Fator R-Quadrado

O fator R-Quadrado é uma medida usada para comparar o dataset e o modelo. Quanto mais próximo de 1.0, melhor o modelo explica o conjunto de dados. Quanto mais próximo de 0.0, menos relacionados estão o modelo e o dataset. Um modelo muito ruim pode gerar um R-Quadrado negativo por causa da álgebra envolvida.

## Erro Absoluto Médio

É a média aritmética dos erros em módulo, por erros entendendo-se (valor estimado pelo modelo - valor real)

## Links


Segue os links que foram escolhidos para a montagem do machine learning. É importante ressaltar que foram escolhidos dois links, mas 
no primórdio do projeto somente o *primeiro* foi utilizado, apesar da maior quantidade de elementos presente no segundo.

1 - https://www.kaggle.com/PromptCloudHQ/imdb-data

2 - https://www.kaggle.com/rounakbanik/the-movies-dataset


Nota: A variável faturamento é dada sempre em milhões de dólares americanos


### [Lendo o dataset](https://github.com/carolinechaim/Projeto_3/blob/master/Codigo_nova_tabela.ipynb)

Foi montado um NoteBook com o propósito de filtrar o dataset e fazer o One-Hot com a variável presença de ator. O notebook foi utilizado para criar uma nova tabela com os nossos "dummies" ou seja, todos os atores presentes no nosso [dataframe orignial](https://github.com/carolinechaim/Projeto_3/blob/master/Movie_Data.csv) foram transformados em QUALI para a futura montagem da regressão linear, formando um [novo dataframe.](https://github.com/carolinechaim/Projeto_3/blob/master/Movie_Data_Atualizado.csv). 

### [Primeira tentativa](https://github.com/carolinechaim/Projeto_3/blob/master/Verificacao-regressao.ipynb)

Na primeira tentativa, foi possível realizar a regressão linear a partir do novo dataframe usando a presença de cada ator como variável explicativa e o faturamento do filme como variável dependente. Esse método gerou um fator r-quadrado de -0.20867585110589038 e um erro absoluto médio de 99.58424687064496, mostrando que não é um método confiável de previsão do faturamento.

### [Segunda tentativa](https://github.com/carolinechaim/Projeto_3/blob/master/Random_Forest.ipynb)

Na segunda tentativa, o mesmo dataframe foi utilizado, porém com um novo método: Random Forest Regressor. Usando, de novo, a presença de cada ator como variável explicativa e o faturamento do filme como variável dependente, esse método gerou um fator r-quadrado de 0.8217966958016902 e um erro absoluto médio de 19.14688161337864. Esse método prova-se portanto deveras eficiente e pode ser considerado confiável para a previsão de faturamento de um filme.

### [Terceira tentativa](https://github.com/carolinechaim/Projeto_3/blob/master/K_Neighbors.ipynb)

Na terceira tentativa, tudo foi feito de modo idêntico à segunda tentativa, mas o método utilizado foi K-Neighbors Regressor, utilizando um valor de neighbors k=5 (padrão). Esse método gerou um fator r-quadrado de -0.46397647995286273 e um erro absoluto médio de 58.86852380952381, mostrando que é um método menos confiável que a regressão linear mas que gera menos erro.

### Conclusão

Com os resultados obtidos, conclui-se que o Random Forest Regressor (RFR, abreviado) é o melhor método para essa questão. Para estimar o faturamento de um filme, deve-se passar o elenco principal para o RFR.

### Considerações

Na implementação dos métodos citados foram passados os argumentos random_state = 0 e n_estimators = 500 para o RFR e nenhum argumento relevante foi passado para Nearest Neighbors ou Regressão Linear.
