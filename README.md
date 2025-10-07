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


- Ao calcular o primeiro quartil (Q1) como um valor X, assumir que X é o ponto abaixo do qual se encontram 25% dos dados. Ou seja, Q1 não é o valor máximo dos primeiros 25%, mas sim o valor que demarca esse limite inferior - Exemplo:

      - 70 70 70 70 79 80 82 84 90 90 91 95

  Q1 envolve 70 - 70 - 70

  Q2 envolve Q1 + 70 - 79 - 80

  Q3 envolve Q2 + 82 - 84 - 90

Repare que o fim de Q1 e inicio de Q2 correspondem ao mesmo valor, por tanto é errado afirmar:

- “70 representa 25% dos menores valores.”

O que os quartis (ou percentis) realmente indicam é:

- 25% dos dados são menores ou iguais a 70.