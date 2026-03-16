# 📊 Atalhos Úteis


- [Fórmula para Cálculo de Percentis](#-fórmula-para-cálculo-de-percentis)
- [Compreendendo quartis e seu uso no boxplot](#compreendendo-quartis-e-seu-uso-no-boxplot)
- [O que são outliers?](#o-que-são-outliers)
- [Variância e Desvio Padrão](#variância-e-desvio-padrão)
- [Coeficiente de variação](#coeficiente-de-variação)


<br />
<hr />
<br />



## 🧮 Fórmula para Cálculo de Percentis

```text
k = (k/100) × (n + 1)
```

**Onde:**  
🔹 **k** = percentil desejado (ex: 25 para o 25º percentil)  
🔹 **n** = número total de observações

#### 🔢 Interpolação para Posições Não Inteiras

Quando o resultado **não é um número inteiro**, fazemos uma **média ponderada** entre os dois valores mais próximos.

**Exemplo:** Se resultado = 8.25  
📌 Significa que está entre as posições 8 e 9  
📌 Fazemos média ponderada com pesos 0.75 e 0.25

### 🧪 Exemplo Prático

**Conjunto de dados:**  
`10, 15, 20, 25, 30, 35, 40`

**Calculando o P₃₅:**

P₃₅ = (35/100) × (7 + 1)
P₃₅ = 0.35 × 8 = 2.8

**📈 Resultado 2.8 indica:**

- Está entre posição 2 (valor 15) e posição 3 (valor 20)
- Mais próximo da posição 3 → peso maior para valor 20

**🎯 Cálculo da interpolação:**
P₃₅ = (15 × 0.2) + (20 × 0.8)
P₃₅ = 3 + 16 = 19

**💡 Interpretação:**  
35% dos valores são **iguais ou menores** que 19 no conjunto ordenado.

<br />
<br />
<br />


## Compreendendo quartis e seu uso no boxplot

O calculo dos quartis nos ajuda a entender como nossos dados estão distribuídos. Podemos por exemplo comparar:

> Q2 - Q1 

com

> Q3 - Q2


Se os valores foram próximos, podemos entender que a dispersão é semelhante acima e abaixo da mediana, mas se a diferença for maior de um dos lados significa que existe uma maior dispersão nele.

Logo:

~~~
Q2 − Q1 ≈ Q3 − Q2 -->  A dispersão é semelhante nos dois lados da mediana.

Q2 − Q1 > Q3 − Q2 -->  A dispersão é maior na parte inferior do conjunto (valores menores que a mediana)

Q2 − Q1 < Q3 − Q2 -->  A dispersão é maior na parte superior do conjunto (valores maiores que a mediana)
~~~

No boxplot isso pode ser lido de uma maneira rápida - Valores distantes da caixa (representados pelos bigodes ou pelos outliers) podem **(não necessariamente)**  ser eliminados em uma análise, isso porque alguns modelos como os de Regressão Linear por exemplo, são sensíveis a outliers.


Alguns pequenos exemplos de cenários do "mundo real" em que a análise de boxplots pode ajudar:


- Definição de metas de alta performance --> "Queremos que nossa loja esteja acima de Q3, ou seja, no grupos das 25% melhores lojas em vendas".

- Segmentação de clientes --> "Separar clientes em grupos como (clientes de baixo, médio e alto custo)".

- Análise de desempenho --> "Queremos identificar se a nota atribuída a um funcionário é ou não um destaque em relação aos demais".

<br />
<br />
<br />

## O que são outliers?

Outliers são valores "discrepantes" em um conjunto de dados. Um método comum para identificá-los (método de Tukey) usa a Amplitude Interquartil (IQR), que é a diferença entre o terceiro quartil (Q3) e o primeiro quartil (Q1):


IQR = Q3 - Q1

Em seguida, calculamos uma margem multiplicando o IQR por 1,5. Esse valor (1.5 \* IQR) define a distância a partir dos quartis para estabelecer os limites.

Um outlier é, portanto, qualquer valor que esteja:

Abaixo do Limite Inferior: Q1 - 1.5 \* IQR

Acima do Limite Superior: Q3 + 1.5 \* IQR

<br />
<br />
<br />


## Variância e Desvio Padrão

Variância e Desvio Padrão são medidas de dispersão que por sua vez serve para nos ajudar a entender o quão dispersos estão nossos dados em relação a média.

A **variância** é o resultado da média dos quadrados das diferenças (subtração) entre cada valor e a média aritmética do conjunto. 

O passo a passo para chegar nesse valor seria:

- Tira a média aritmética
- Faz a subtração de cada um desses valores em relação a essa média aritmética
- Para cada valor do passo anterior deve-se elevar ao quadrado
- Fazemos a soma de todos os valores do passo anterior e tiramos a média dele.

**Importante**: Neste último passo onde tira-se a média dos valores do conjunto existe a fórmula populacional:

$$
\sigma^2 = \frac{\sum_{i=1}^{N} (x_i - \mu)^2}{N}
$$

E a fórmula amostral:

$$
\sigma^2 = \frac{\sum_{i=1}^{N} (x_i - \mu)^2}{N - 1}
$$


A diferença entre as fórmulas está no denominador: na variância populacional divide-se por N, enquanto na variância amostral divide-se por N – 1 (onde N é o número de observações). Usamos N - 1 para chegarmos em um resultado mais conservador na hora de determinar a variância (dado que será um valor maior já que estamos dividindo por um valor menor). É como dar um desconto pela incerteza extra de não conhecer todos os dados.


Resumindo variância em uma linha: É a média dos quadrados da diferença (subtração) entre meus valores e a média aritmética.

O **desvio padrão** é a raiz quadrada da variância para que tenhamos um valor na mesma escala dos dados analisados.


$$
\sigma = \sqrt{\frac{\sum_{i=1}^{N} (x_i - \mu)^2}{N}}
$$


<br />
<br />
<br />


## Coeficiente de variação

Nos diz em forma percentual o quanto os dados variam em relação a média - Tem 2 grandes propósitos:

- Nos dizer o quanto o desvio padrão varia em relação a média (de forma percentual)
- Comparar a variação de 2 conjuntos que estejam em escalas numéricas distintas.

$$
CV = \frac{\sigma}{\mu} \times 100\%
$$