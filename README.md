# Análise dos dados do TSE sobre candidatos as eleições de 2022


Dados coletados a partir do site do TSE: [dadosabertos.tse.jus.br/dataset/candidatos-2022](https://dadosabertos.tse.jus.br/dataset/candidatos-2022) em 18/9/2022.

## Introdução

A análise a seguir foi desenvolvida com base nos dados extraídos do portal do TSE, com o intuito de identificar a taxa de candidados negros, mulheres e bens declarados pelos candidatos. Importante mencionar que a análise em questão visa unicamente analisar e extraír informações pertinentes ao cenário de diversidade entre os partidos brasileiros, com base nas informações disponibilizadas pelos próprios partidos e abertos para consumo público. 

## Índice

- [1. Materiais e Métodos](#1-materiais)
- [2. Resultados e Discussão](#2-resultados)
- [3. Considerações Finais](#3-consideracoes)

## 1. Materiais e Métodos

Neste trabalho foi utilizada a linguagem de programação R e o software RStudio. Após extraír os dados brutos com informações gerais sobre os candidatos, foi realizado o tratamento e pré-processamento dos dados para então realizar as análise e construir as visualizações. Após etapa de processamento dos dados foi utilizado um algoritmo de clusterização para dividir os partidos em grupos com alta similaridade, tendo como base as variáveis consideradas neste estudo.

Seguem abaixo as variáveis utilizadas após processamento dos dados:


|Nome Variável|Descrição|
|---|---|
| SG_PARTIDO | Sigla dos partidos|
| TOTAL_CANDIDATOS | Quantidade de candidatos por partido|
| DS_COR_RACA_PRETA | Percentual de candidatos autodeclarados de cor/raça preta por partido|
| DS_COR_RACA_BRANCA | Percentual de candidatos autodeclarados de cor/raça branca por partido|
| GENERO_MASCULINO | Percentual de candidatos do gênero masculino por partido|
| GENERO_FEMININO | Percentual de candidatas do gênero feminino por partido|
| MEDIA_BENS_CANDIDATO | Valor mediano dos bens declarados por candidato/partido|
| CLUSTER | Número do cluster referente a cada partido|


## 2. Resultados e Discussão

## 2.1. Percentual de candidados Pretos

Agrupando os dados por partido é possível identificar o percentual de candidados autodeclarados pretos. Esta análise considera a amostra de candidados pretos e brancos, e o percentual em relação a cada grupo. Conforme gráfico abaixo, observamos que o partido PSOL possui o maior percentual de candidatos e candidatas autodeclarados pretos. Por outro lado, o partido NOVO possui o menor índice percentual.

<img src="https://raw.githubusercontent.com/brborges/analise-dados-tse/main/Percentual%20de%20candidados%20autodenominados%20Pretos%20por%20partido.png" alt="grupos-partidos-candidatos-pretos" width="750">

## 2.2. Valor mediano de bens dos candidatos

Analisando os dados foi possível identificar que cada candidato pode declarar n bens e seus respectivos valores. Foi gerada então a mediana de bens totais declarados por candidato para cada partido, visto que ao observar a mesma análise com a média aritmética os dados se mostraram sensíveis a outliers.

<img src="https://raw.githubusercontent.com/brborges/analise-dados-tse/main/Valor%20mediano%20de%20bens%20declarados%20por%20candidato%20em%20cada%20partido.png" alt="grupos-partidos-mediana-bens" width="750">

## 2.3. Distribuição de candidatas mulheres pretas

A análise a seguir visa identificar quais partidos são semelhantes entre si considerando a taxa percentual de mulheres pretas, além de a patir desta análise observar também o total desta representatividade dentro de cada partido considerando todos os demais canditados. 

Como mostra o gráfico a seguir, de forma geral os partidos apresentam baixa quantidade de mulheres, com uma mediana de 33%. Por outro lado, alguns partidos se destacam por ter uma quantidade maior de candidatas pretas mulheres, como por exemplo o PC do B e o UP. O partido identificado com menor percentual de mulheres pretas foi o partido NOVO, destacado como um grupo isolado no quadrande inferior esquerdo do gráfico.

Utilizando as variáveis normalizadas, aplicou-se o método de KMeans considerando 6 grupos. O resultado desta análise se dá pelo gráfico abaixo, onde as cores representam os grupos de partidos, as linhas horizontais e verticais representam a mediana de cada variável e o tamano dos pontos representam a quantidade de candidatos por partido.

<img src="https://raw.githubusercontent.com/brborges/analise-dados-tse/main/Distribui%C3%A7%C3%A3o%20de%20candidados%20Pretos%20versus%20total%20de%20candidatas%20Mulheres%20por%20partido.png" alt="grupos-partidos-diversidade" width="750">

## 2.4. Distribuição mediana de bens dos candidatos

Em seguida foi gerada uma análise da mediana de bens de cada candidato por partido considerando os canditados pretos, com o intuito de observar se há relação entre a cor/raça decladara pelo candidato e o total de bens que ele/ela possui declarados.

Com estes dados foi possível identificar que os partidos com menor percentual de candidatos pretos são proporcionalmente os partidos com maior mediana de bens por canditado. Como por exemplo o partido NOVO que possui menor taxa de candidatos pretos e maior valor de bens declarados. Por outro lado temos o partido UP que possui maior taxa de candidados, porém com menor quantidade de candidatos e menor mediada de bens declarados.

O mesmo método de clusterização foi utilizados, aplicando-se o método de KMeans considerando 6 grupos. O resultado desta análise se dá pelo gráfico abaixo, onde as cores representam os grupos de partidos, as linhas horizontais e verticais representam a mediana de cada variável e o tamano dos pontos representam a quantidade de candidatos por partido.

<img src="https://raw.githubusercontent.com/brborges/analise-dados-tse/main/Distribui%C3%A7%C3%A3o%20de%20candidados%20Pretos%20por%20valor%20mediano%20de%20bens%20dos%20candidatos.png" alt="grupos-partidos-diversidade-bens" width="750">

## 3. Considerações Finais

Este estudo teve como objetivo analisar o cenário de diversidade de cor e gênero dentros os partidos das eleições de 2022. Com os dados extraídos, pré-processados e analisados, foi possível chegar a algumas percepções sobre a distribuição de grupos minoritários nos partidos. Além destas análises, também é possível utilizando os dados abertos do TSE identificar nivel de escolaridade dos candidados, distribuição por faixa de idade, estado civíl e etc.  

Fonte: Dados coletados a partir do site do TSE: [dadosabertos.tse.jus.br/dataset/candidatos-2022](https://dadosabertos.tse.jus.br/dataset/candidatos-2022).
