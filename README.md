
# MachineLearningSellingPriceOfCars


![Project](https://img.shields.io/badge/MachineLearning-SellingPriceOfCars-blue)
![Version](https://img.shields.io/badge/Python-V1.0-blue)


Projeto utiliza a biblioteca **LinearSVC**, **SVC**, **DummyClassifier**, **DecisionTreeClassifier** e **StandardScaler** do **SKLEARN** para classificação e escala dos dados.
Também usa o **graphviz** para plotar os dados na tela.

O mesmo classifica preços de carros com base no ano do seu modelo e na sua quilometragem.

Após fazer a leitura do arquivo CSV com os dados, o algoritmo exibe a tabela que o mesmo possui:

![enter image description here](https://github.com/DouglasAugustoJunior/MachineLearningSellingPriceOfCars/blob/master/Images/1.png?raw=true)

Para melhor manipular os dados, as colunas são renomeadas, alteramos os dados da coluna *'vendido'* para *0 e 1*, adicionamos as colunas *'idade do modelo'* e *'km por ano'* e apagamos as colunas que não serão utilizadas, tendo a tabela abaixo para classificar:

![enter image description here](https://github.com/DouglasAugustoJunior/MachineLearningSellingPriceOfCars/blob/master/Images/2.png?raw=true)

Ao realizar a classificação com o *LinearSVC* obtemos uma acurácia de **58%**, então vamos comparar esse resultado com uma ***baseline*** para verificar se está bom.

Ao utilizar o *DummyClassifier* do SKLEARN com parâmetro *dummy_stratified* (valores equivalentes) para gerar nossa ***baseline***, obtemos uma acurácia de **52,44%**. Já com o parâmetro em *most_frequent*(baseado na maior frequência de dados) a acurácia sobe para **58%**.

Sendo assim podemos constatar que nosso algoritmo não está satisfatório, então vamos tentar outra estratégia, com o *SVC* do SKLEARN, escalando os dados com o ***StandardScaler***. O mesmo consegue uma acurácia de **76,44%**.

Mesmo com essa melhora, ainda precisamos exibir como o algoritmo chegou a essas conclusões, porém o *LinearSVC* e o *SVC* são bibliotecas *black box*('caixa preta', difícil de dizer como chegaram a tal conclusão).

Mudando novamente, vamos utilizar a biblioteca *DecisionTreeClassifier*, para exibir nossos resultados em árvore.
Deixaremos como parâmetros a altura da árvore em 3, e teremos uma acurácia de **78,28%**.
Para exibir essa árvore, vamos usar o ***graphviz***, com parâmetros para preencher com cores,bordas arredondadas, features(nomes das colunas) e classes 'Sim' e 'Não'.

![enter image description here](https://github.com/DouglasAugustoJunior/MachineLearningSellingPriceOfCars/blob/master/Images/3.png?raw=true)

Aqui podemos visualizar quais as condições para que o carro seja vendido (True, Azul) ou não (False, Laranja), como por exemplo, o preço <= R$59982,246 para que seja verdadeiro, ou KM por ano <= 24112,741 para ser falso.
