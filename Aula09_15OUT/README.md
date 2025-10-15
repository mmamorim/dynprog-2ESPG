<img src="/assets/teste.svg" width="100%">

# Aula 09 - 15/10 

---


# ✨💰 O Desafio do Moedas 

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
