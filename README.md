# Câncer de Mama

Este projeto, a partir de um dataset câncer de mama, tem o intuito de senvolver algoritmos de machine learning, aplicar ensebles e verificar se é possivel manter a perfomace aplicando o RFE e o PCA.

O dataset está disponivel no kaggle, nesse [link](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data?select=data.csv)

Temos como machine learning será usado como **ML**

## Índice

* [Visualização e entendimento do dataset](#visualização-e-entendimento-do-dataset)
* [Aplicando os algoritmos de ml sem otimização](#aplicando-os-algoritmos-de-ml-sem-otimização)
* [Aplicando ensemble](#aplicando-ensemble)

# Visualização e entendimento do dataset

- [Link de acesso ao notebook](https://github.com/gustavoramos82/C-ncer-de-mama/blob/main/breast_visualizacao.ipynb)

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

3) Podemos ver pelos dois gráficos de dispersão que dá pra delimitar uma área onde dá pra classifcar, pode ser que técnicas como o svm tenha uma boa perfomace nesse dataset.

![image](https://user-images.githubusercontent.com/39843884/170154808-e4832527-a208-4ea5-ad53-ce18aaddd136.png)

![image](https://user-images.githubusercontent.com/39843884/170154931-1111083b-205b-43c2-8074-1763cb55c601.png)

# Aplicando os algoritmos de ml sem otimização

- [Link do Notebook](https://github.com/gustavoramos82/C-ncer-de-mama/blob/main/breast_sem_oti.ipynb)

A partir dos materiais lidos, foi selecionados os seguintes algoritmos de classificação (todos os materiais constam nas referências):

- Regressão logistica
- KNN
- SVM
- Árvore de Decisão
- Naive Bayes

Aplicando o modelo no dataset e comparando os resultados, percebeu-se que o método de *undersampling* não teve uma melhora nos resultados, então será mostrado somente as metrica sem *undersampling*.

Comparando as métrica, teve os seguintes resultados:

- Svm
  -  Acuracia: 0,973
  -  Precisão: 0,966
  -  Recall: 0,958
  -  f1: 0,962
- KNN
  - Acuracia: 0,963
  - Precisão: 0,974
  - Recall: 0,924
  - f1: 0,947
- Naive Bayes
  - Acuracia: 0,931
  - Precisão: 0,906
  - Recall: 0,900
  - f1: 0,902
- Árvore de Decisão:
  - Acuracia: 0,917
  - Precisão: 0,858
  - Recall: 0,911
  - f1: 0,882
- Regressão Logistica:
  - Acuracia: 0,978
  - Pecisão: 0,974
  - Recall: 0,977
  - f1: 0,97
 
 Podemos ver que a *regressão logistica* e o *svm* foi o que tiveram os melhores resultados, a que teve o pior resultado foi a *árvore de decisão*, e interessante que todas as métricas, sem nenhuma otimização já estão em torno de 0,9 (ou 90%). Agora será escolhido as três melhores e aplicar os métodos ensemble.

# Aplicando ensemble

- [Link do Notebook](https://github.com/gustavoramos82/C-ncer-de-mama/blob/main/breast_oti_ada.ipynb)

Foi aplicado métodos ensemble como Voting Classifier, Bagging, Adaboost, Otimização dos Hiperparemtros e Random Forest, os melhores resultados foram:

- Voting Classifier com knn, árvore de decisão e regressão logistica:
  - Acuracia: 0,973
  - Precisão: 0,981
  - Recall: 0,945
  - f1: 0,962

- Bagging com Regressão Logistica:
  - Acuracia: 0,982
  - Precisão: 0,985
  - Recall: 0,968
  - f1: 0,976
- Adaboost com regressão logistica com lerning rate igual a 0,2:
  - Acuracia: 0,975
  - Precisão: 0,963
  - Recall: 0,967
  - f1: 0,964
 
 Podemos ver pelas métrica acima a no caso do Voting Classifier e do Bagging a acuracia e a precisão serem maiores que a regressão logistica sem otimização, podemos ver que o recall e o f1 são menores,, sendo que nesse contexto de saúde, o recall é uma métrica muito importante pra identifiac, logo o metdos ensemble aplicado não é melhor que a regressão logistica, considerando o recall.



# Referências

[1]- https://bmccancer.biomedcentral.com/track/pdf/10.1186/s12885-017-3877-1.pdf

[2]- https://repositorio.ufmg.br/bitstream/1843/BUOS-8CTFHK/1/344m.pdf

[3]- https://repositorio.ufu.br/bitstream/123456789/32251/1/Compara%C3%A7%C3%A3oAlgoritmosAprendizado.pdf

[4]- https://arxiv.org/abs/1711.07831

[5]- https://www.scielo.br/j/tema/a/yJSLsVLQmfYph8SThYCj8Xh/?format=pdf&lang=pt

