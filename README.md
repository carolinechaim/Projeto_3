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

## Entregas

### Primeira entrega 

Para o dia 12.11, foi montado dois NoteBooks com propósitos diferentes. O [primeiro](https://github.com/carolinechaim/Projeto_3/blob/master/Codigo_nova_tabela.ipynb) foi utilizado como forma de criar uma nova tabela 
com os nossos "dummies" ou seja, todos os atores presentes no nosso [dataframe orignial](https://github.com/carolinechaim/Projeto_3/blob/master/Movie_Data.csv) foram transformados em QUALI para a futura montagem 
da regressão linear, fromando portanto um [novo dataframe.](https://github.com/carolinechaim/Projeto_3/blob/master/Movie_Data_Atualizado.csv)
