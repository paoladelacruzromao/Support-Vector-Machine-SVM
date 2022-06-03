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

As funções de kernel são empregadas não somente com SVM. Redes neurais também empregam funções de kernel, e a ideia de um espaço característico de dimensão maior pode ser empregada
![image](https://user-images.githubusercontent.com/87387315/171510113-8f649012-9d80-471d-aa7d-ce986f38335d.png)

O kernel RBF kernel é o mais empregado e popular. É a base das redes neurais RBF e é um aproximador universal de funções (pode aproximar quaisquer valores de entrada e saída de um conjunto de treinamento). Ele corresponde a um espaço característico de dimensão infinita.

![image](https://user-images.githubusercontent.com/87387315/171510248-d0e7ad43-43ad-4b79-b0da-357f4a26d15e.png)

Exemplo SVM: Na figura 1 os dados não som linearmente separaveis ja na figura 2 aplicando a função de kernel, conseguimos separar os dados. A função kernel simplemente eleva a dimensão 

![image](https://user-images.githubusercontent.com/87387315/171511478-af93009c-af48-4a07-ac75-9203d2f80141.png)


### Notas finais do algoritmo SVM
• Treinamento. O treinamento de um SVM pode ser bastante lento devido ao método de otimização quadrática. Embora essa seja uma técnica com algoritmos bastante desenvolvidos, um grande volume de dados e muitos atributos podem consumir um grande tempo e capacidade computacional;

• Solução única. Sendo um problema de otimização quadrática, a solução de um SVM é, diferentemente de uma rede neural, única (a otimização é sobre uma função convexa);

• Classificador binário. Um SVM é essencialmente um classificador binário. Embora o processo possa ser adaptado para classificação múltipla ou mesmo para regressão, o processo é feito da combinação de múltiplas classificações binárias.


### Margens Rigidas e Flexibles
*** Margem Rigida ***
Quando os dados ficam entre as margens rigidas (7 e 8), significa que os dados são quase linearmente separaveis, para esses casos não vale a pena aplicar o trueque do Kernel, esses dados tem uma cosinha a mais como por exemplo outliers que impede que eles sejam totalmente linearmente separaveis, em esse caso não podemos aplicar SVM de margens rígidas. As margens rígidas é só aplicable quando os dados são totalmente linearmente separaveis, osea você tem que gasrantir que seus dados não contem outliers para não classificar de maneira incorreta como o gráfico da direita.

![image](https://user-images.githubusercontent.com/87387315/171882175-b673c696-ad6a-4efa-9ee6-192545e7875d.png)

![image](https://user-images.githubusercontent.com/87387315/171880404-2b03ecdc-a8fe-45fc-b535-43d912a1b416.png)

*** Margem Flexibles ***

Na vida real é muito dificil achar dados linearmente separavéis, para isso precisamos achar uma função possa pular alguns valores discrepantes e poder classificar pontos linearmente separáveis.Para isso veamos a variavel slack, chamada de Xi

![image](https://user-images.githubusercontent.com/87387315/171883486-17dea2af-d262-4a9d-910d-76ba387a8e6d.png)

Podemos ver que a formula de regressaõ tem mais um parámetro que é o slack

![image](https://user-images.githubusercontent.com/87387315/171883702-ff0535b4-6aa6-480d-b400-9b04d575e997.png)

![image](https://user-images.githubusercontent.com/87387315/171883993-64157d78-684f-4bba-af98-6b58db795b4c.png)


### Resumindo
![image](https://user-images.githubusercontent.com/87387315/171884417-decefbdc-0405-43e4-821d-5f86644c78ef.png)

### Parâmetro de Regulizacão C
Esse parâmetro nos ajuda ao treinamento da margem do hiperplano rígida ou flexible 

![image](https://user-images.githubusercontent.com/87387315/171939753-b5ee15ff-b44b-44c5-b1e0-c2c1fba89ff0.png)

