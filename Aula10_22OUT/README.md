<img src="/assets/teste.svg" width="100%">

# Aula 10 - 22/10 

---


# ✨💰 O Desafio das Moedas 

Você irá programar um **caixa eletrônico**. Esse caixa trabalha com apenas alguns tipos de notas. Como entregar a quantia correta para um saque contendo a menor quantidade de notas?   

**Enunciado**

Dado um valor **N** e um conjunto de moedas de valores **[c₁, c₂, …, cₖ]**, determine o **mínimo número de moedas** necessário para representar exatamente **N** (supondo disponibilidade ilimitada de cada tipo de moeda).

- **Entrada:** inteiro não negativo `N` e lista de inteiros positivos `moedas = [c1, c2, ..., ck]`.  
- **Saída:** inteiro — menor quantidade de moedas cuja soma é `N`, ou indicação que `N` não pode ser formado (ex.: `-1`).

**Exemplo:** `N = 6`, `moedas = [1, 3, 4]` → resposta: `2` (3 + 3).

---

## ❓ Pergunta
> #### ⚡ Qual a **melhor maneira** de entregar esse troco usando a menor quantidade de moedas?  

---

# 🗣️ Complicando...

#### - 🔄 **E para entregar sempre a solução ótima? 

### Como seria essa solução em python?

---

## Abordagem Recursiva (Força Bruta)

A ideia aqui é **tentar todas as combinações possíveis** de moedas para formar o valor `N`.  
Para cada moeda, fazemos uma chamada recursiva tentando resolver o subproblema `N - moeda`.  

Esse método garante encontrar a **solução ótima**, mas pode ser extremamente ineficiente, pois recalcula subproblemas várias vezes.  

### Vantagens
- Sempre encontra a solução ótima.  
- Conceito simples de entender: quebrar o problema em subproblemas menores.  

### Desvantagens
- Muito lento (complexidade exponencial).  
- Não é viável para valores grandes de `N` sem otimização.  

### Exemplo
Para `N = 6` e moedas `[1, 3, 4]`:  
O algoritmo vai testar todas as combinações possíveis de moedas até encontrar a solução mínima (neste caso: 2 moedas → `3 + 3`).  


---


# 🗣️ Complicando...

#### - 🔄 Existe uma forma de melhor a "performance" (complexidade de tempo)  ? 

--- 

## Recursivo com Memoização (Top-Down)

A memoização é uma técnica que **armazena resultados já calculados** para evitar recomputar subproblemas.  
No problema das moedas, isso significa guardar o mínimo número de moedas necessário para cada valor `N` já processado.  

Isso mantém a estrutura recursiva, mas reduz drasticamente a quantidade de cálculos repetidos, transformando um algoritmo exponencial em um de complexidade **O(N·K)**, onde K é o número de moedas.  

### Vantagens
- Mantém o raciocínio simples da recursão.  
- Evita recalcular subproblemas repetidos.  
- Muito mais rápido que a recursão pura.  

### Desvantagens
- Ainda depende da pilha de chamadas recursivas.  
- Usa memória extra para armazenar os resultados.  

### Exemplo
Para `N = 6` e moedas `[1, 3, 4]`, o algoritmo resolve cada subproblema apenas uma vez.  


# 🗣️ Complicando...

#### - 🔄 Existe uma forma de melhor a "performance" (complexidade de tempo)  ? 

--- 

## Programação Dinâmica (Bottom-Up)

Na abordagem Bottom-Up, resolvemos o problema **do menor subproblema até o maior**, preenchendo uma tabela (array) com as soluções parciais.  
Diferente da recursão com memoização, aqui **não usamos chamadas recursivas**, apenas iteração.  

Isso evita sobrecarga de chamadas recursivas e garante que todos os subproblemas sejam resolvidos **uma única vez**.  
Complexidade: **O(N·K)**, onde N é o valor alvo e K é o número de moedas.  

### Vantagens
- Alta eficiência.  
- Evita o uso de pilha de chamadas recursivas.  
- Simples de implementar.  

### Desvantagens
- Calcula todos os subproblemas mesmo que alguns não sejam necessários.  
- Usa memória extra proporcional a N.  

### Exemplo
Para `N = 6` e moedas `[1, 3, 4]`, o algoritmo preenche um array `dp` onde `dp[i]` é o mínimo número de moedas para formar `i`.  
