# Projeto_3
Projeto 3 de Ciências dos Dados. 2019/2

## Introdução
Foi proposto para que os alunos formulassem uma pergunta e que a mesma seja respondida atraves de um machine learning. O grupo 
formulou as seguintes: 

1)Para cada ator atuando em dado filme, qual vai ser a estimativa de faturamento deste filme?

2)Dado um filme pertencente a algum gênero, quais são os atores mais prováveis de estarem desempenhando algum papel no filme?

Em uma primeira avaliação, ambas as perguntas foram consideradas boas para a montagem do projeto, porém com sugestões de técnicas diferentes.
Na primeira foi sugerida Random Forest e linear regression enquanto na segunda foi sugerida CategoricalNB, Decision Trees.

Em um brainstorming final, o grupo decidiu escolher trabalhar em cima do primeiro tema:

_Para cada ator atuando em dado filme, qual vai ser a estimativa de faturamento deste filme?_


## Links


Segue os links que foram escolhidos para a montagem do machine learning. É importante ressaltar que foram escolhidos dois links, mas 
no primórdio do projeto somente o *primeiro* foi utilizado, apesar da maior quantidade de elementos presente no segundo.

1 - https://www.kaggle.com/PromptCloudHQ/imdb-data

2 - https://www.kaggle.com/rounakbanik/the-movies-dataset


Nota: A variável faturamento é dada sempre em milhões de dólares americanos


### Lendo o dataset 

Foi montado um NoteBook com o propósito de filtrar o dataset e fazer o One-Hot com a variável presença de ator. O [notebook](https://github.com/carolinechaim/Projeto_3/blob/master/Codigo_nova_tabela.ipynb) foi utilizado para criar uma nova tabela com os nossos "dummies" ou seja, todos os atores presentes no nosso [dataframe orignial](https://github.com/carolinechaim/Projeto_3/blob/master/Movie_Data.csv) foram transformados em QUALI para a futura montagem da regressão linear, formando um [novo dataframe.](https://github.com/carolinechaim/Projeto_3/blob/master/Movie_Data_Atualizado.csv). 

### Primeira tentativa 

Na primeira tentativa, foi possível realizar a regressão linear a partir do [novo dataframe] usando a presença de cada ator como variável explicativa e o faturamento do filme como variável dependente. Esse método gerou um fator r-quadrado de -0.20867585110589038 e um erro absoluto médio de 99.58424687064496, mostrando que não é um método confiável de previsão do faturamento.

### Segunda tentativa 

Na segunda tentativa, o mesmo [dataframe] foi utilizado, porém com um novo método: Random Forest Regressor. Usando, de novo, a presença de cada ator como variável explicativa e o faturamento do filme como variável dependente, esse método gerou um fator r-quadrado de 0.8217966958016902 e um erro absoluto médio de 19.14688161337864. Esse método prova-se portanto deveras eficiente e pode ser considerado confiável para a previsão de faturamento de um filme.

### Terceira tentativa

Na terceira tentativa, tudo foi feito de modo idêntico à segunda tentativa, mas o método utilizado foi Nearest Neighbors Regressor. Esse método gerou um fator r-quadrado de -0.46397647995286273 e um erro absoluto médio de 58.86852380952381, mostrando que é um método menos confiável que a regressão linear mas que gera menos erro.

### Conclusão

Com os resultados obtidos, conclui-se que o Random Forest Regressor (RFR, abreviado) é o melhor método para essa questão. Para estimar o faturamento de um filme, deve-se pegar o elenco e somar os coeficientes de cada ator gerados pelo RFR.

### Considerações

Na implementação dos métodos citados foram passados os argumentos random_state = 0 e n_estimators = 500 para o RFR e nenhum argumento relevante foi passado para Nearest Neighbors ou Regressão Linear.

Além disso, foi feito, em paralelo com a primeira tentativa, um esforço de filtrar outros arquivos csv, mais completos que https://github.com/carolinechaim/Projeto_3/blob/master/Movie_Data.csv, os arquivos https://github.com/carolinechaim/Projeto_3/blob/master/movie_metadata.csv e https://github.com/carolinechaim/Projeto_3/blob/master/credits.csv, que, em conjunto, resultariam em uma base de dados com mais de 200000 atores e mais de 5000 filmes para analisar, mas tal tarefa demanda mais processamento do que estava disponível e o esforço foi abandonado em nome de uma entrega mais completa e consistente.