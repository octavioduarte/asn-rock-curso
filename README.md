# 📊 Atalhos Úteis

## 🧮 Fórmula para Cálculo de Percentis

```text
k = (k/100) × (n + 1)
```

**Onde:**  
🔹 **k** = percentil desejado (ex: 25 para o 25º percentil)  
🔹 **n** = número total de observações

### 🔢 Interpolação para Posições Não Inteiras

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

## 📝 Lembretes rápidos

<br />
<br />

**O que compreender ao calcular quartis**: Ao calcular o primeiro quartil (Q1) como um valor X, assumir que X é o ponto abaixo do qual se encontram 25% dos dados. Ou seja, Q1 não é o valor máximo dos primeiros 25%, mas sim o valor que demarca esse limite inferior - Exemplo:

      - 70 70 70 70 79 80 82 84 90 90 91 95

Q1 envolve 70 - 70 - 70

Q2 envolve Q1 + 70 - 79 - 80

Q3 envolve Q2 + 82 - 84 - 90

Repare que o fim de Q1 e inicio de Q2 correspondem ao mesmo valor, por tanto é errado afirmar:

- “70 representa 25% dos menores valores.”

O que os quartis (ou percentis) realmente indicam é:

- 25% dos dados são menores ou iguais a 70.

<br />
<hr />
<br />

**Outliers**: Outliers são valores "discrepantes" em um conjunto de dados. Um método comum para identificá-los (método de Tukey) usa a Amplitude Interquartil (IQR), que é a diferença entre o terceiro quartil (Q3) e o primeiro quartil (Q1):

IQR = Q3 - Q1

Em seguida, calculamos uma margem multiplicando o IQR por 1,5. Esse valor (1.5 \* IQR) define a distância a partir dos quartis para estabelecer os limites.

Um outlier é, portanto, qualquer valor que esteja:

Abaixo do Limite Inferior: Q1 - 1.5 \* IQR

Acima do Limite Superior: Q3 + 1.5 \* IQR

<br />
<hr />
<br />


