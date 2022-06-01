# Support-Vector-Machine-SVM (aprendizado supervisionado)

A ideia básica do SVM é prover um separador, ou classificador,linear. SVMs são um modelo de aprendizado supervisionado.O conjunto de treinamento é, por exemplo, um conjunto de
pontos xa = { (xa,1 , xa,2) } de classe 1 e xb = { (xb,1 , xb,2) } declasse -1 e queremos achar uma função que classifique de forma suficientemente correta esses pontos do conjunto de treinamento e possa ser empregada para classificar novas instâncias.
Para isso o algoritmo SVM busca uma função linear Wx + b (sendo x de uma dimensão >1, W e b são vetores e precisamos empregar WT), um hiperplano (em 2D uma reta) que separa linearmente os dois conjuntos de dados.
Note que existem infinitas retas (hiperplanos) que podem igualmente separar o conjunto de dados. A escolha da SVM recai sobre a reta (ou hiperplano) que maximiza a distância entre os
pontos xa e xb, os pontos da classe 1 e da classe -1.
