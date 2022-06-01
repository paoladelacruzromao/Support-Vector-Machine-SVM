# Support-Vector-Machine-SVM (aprendizado supervisionado)

A ideia básica do SVM é prover um separador, ou classificador,linear. SVMs são um modelo de aprendizado supervisionado.O conjunto de treinamento é, por exemplo, um conjunto de pontos xa = { (xa,1 , xa,2) } de classe 1 e xb = { (xb,1 , xb,2) } declasse -1 e queremos achar uma função que classifique de forma suficientemente correta esses pontos do conjunto de treinamento e possa ser empregada para classificar novas instâncias.
Para isso o algoritmo SVM busca uma função linear Wx + b (sendo x de uma dimensão >1, W e b são vetores e precisamos empregar WT), um hiperplano (em 2D uma reta) que separa linearmente os dois conjuntos de dados.
Note que existem infinitas retas (hiperplanos) que podem igualmente separar o conjunto de dados. A escolha da SVM recai sobre a reta (ou hiperplano) que maximiza a distância entre os pontos xa e xb, os pontos da classe 1 e da classe -1.

![image](https://user-images.githubusercontent.com/87387315/171508498-534f10bc-e132-4f67-bfb8-bd3626657ec6.png)

Essa distância cria uma margem entre os pontos classificados como 1 e -1. Os valores de W e b que a SVM quer buscar são aqueles que maximizam essa margem e dependerão dos pontos que se encontram na fronteira dessa margem, chamados de vetores de suporte.
Essa intuição geométrica da SVM é o fundamento de todas SVM. Mesmo nessa forma simples, entretanto, a formulação matemática da margem, sua maximização e identificação dos vetores desuporte requerem um razoável ferramental matemático. Conceitos e ferramentas ainda mais sofisticados são requeridos quando queremos estender essa ideia para a classificação múltipla (não binária), para separadores não lineares ou para situações ondenão existe uma margem (soft margin, quando teremos que aceitar
um certo número de elementos dentro da margem).

### Kernel trick
A seguir você vai entender o papel da função de kernel, que tem grande importância na solução de problemas lineares para não lineares.O truque então é empregar uma função de Kernel, levando o conjunto de dados a um espaço de dimensão maior (espaço característico ou feature space) em que seja linearmente separável.Sim, você vai colocar os dados em uma dimensão maior de forma que Os pontos se tornam linearmente separáveis nesse espaço de dimensão maior

![image](https://user-images.githubusercontent.com/87387315/171509149-118891a2-416d-4902-9593-48cde21318ad.png)


