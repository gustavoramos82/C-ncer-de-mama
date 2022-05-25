# Câncer de Mama

![Badge em Desenvolvimento](http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge)

Este projeto, a partir de um dataset câncer de mama, tem o intuito de senvolver algoritmos de machine learning, aplicar ensebles e verificar se é possivel manter a perfomace aplicando o RFE e o PCA.

O dataset está disponivel no kaggle, nesse [link](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data?select=data.csv)

Temos como machine learning será usado como **ML**

## Índice

* [Visualização e entendimento do dataset](#visualização-e-entendimento-do-dataset)
* [Aplicando os algoritmos de ml sem otimização](#aplicando-os-algoritmos-de-ml-sem-otimização)
* [Aplicando ensemble](#aplicando-ensemble)
* [Aplicando RFE](#aplicando-rfe)
* [Aplicando PCA](#aplicando-pca)
* [Referências](#referências)

# Visualização e entendimento do dataset

O dataset tem em torno de 30 colunas, mas essas são as principais, as outras são variações dessa segundo também consta no link no kaggle.

![imagem](https://i.ibb.co/KhsWcJ2/Pasted-image-20220522092609.png)

  Os outros dados são variação disso e taxa de erro, além de que diagnosis que M é maligno e b é benigno (que foram tranformado e número categórios, sendo 0 benigno e 1 maligno, que como podemos ver no gráfico de pizza estão distribuido da seguinte forma:

![image](https://user-images.githubusercontent.com/39843884/170152547-b273add4-a0ef-4519-97bc-a6435485e079.png)

Podemos ver que temos mais casos benignos do que malignos, oq seria insteresante aplicar o *undersampling* e comparar a precisão e o recall se tem uma melhora.

Sobre o dataset, não se tem nehum dados faltantes, e temos a seguinte descrição dos dados:

![image](https://user-images.githubusercontent.com/39843884/170154064-e7e0428c-c4a2-4af7-9acc-d7cc30570a77.png)

Podemos ver que será necessário a normalização dos dados, já que temos variaveis com pesos muito diferentes.

Durante a observação, teve algumas visualização, como pode ser visto abaixo:

1) observando o boxplot do raio, podemos ver que a partir de 20 temos só caso maligno.

![image](https://user-images.githubusercontent.com/39843884/170153447-dde18d36-2558-4ef9-b411-6bee4dd31d5d.png)

2) Isso pode ser visto tambèm nos pontos côncavos, que a partir de 1, só temos casos malignos.

![image](https://user-images.githubusercontent.com/39843884/170153628-247eac22-a45a-4ddc-98fa-4d69084a75aa.png)




# Aplicando os algoritmos de ml sem otimização

:construction: Em construção :construction:

# Aplicando ensemble

:construction: Em construção :construction:

# Aplicando RFE

:construction: Em construção :construction:

# Aplicando PCA


:construction: Em construção :construction:

# Referências

:construction: Em construção :construction:
