# Probabilidade

## Conceitos Fundamentais

* **Experimento Aleatório:** Experimento que, mesmo repetido sob as mesmas condições, pode apresentar resultados diferentes.
    * **Exemplo**: Lançamento de um dado.
* **Espaço Amostral ($\Omega$):** Conjunto de todos os resultados possíveis de um experimento aleatório.
    * **Exemplo**: $\Omega = \{1, 2, 3, 4, 5, 6\}$ para o lançamento de um dado.
* **Evento (E):** Subconjunto do espaço amostral.
    * **Exemplo**: $E = \{2, 4, 6\}$ para o evento "sair número par" no lançamento de um dado.
* **Probabilidade (P):** Medida da chance de um evento ocorrer.
    * **Fórmula**: $P(E) = n(E) / n(\Omega)$, onde $n(E)$ é o número de resultados favoráveis e $n(\Omega)$ é o número total de resultados possíveis.


## Regras:

* **Probabilidade de um Evento**: $0 \le P(E) \le 1$.
* **Probabilidade do Espaço Amostral**: $P(\Omega) = 1$.
* **Probabilidade de um Evento Impossível**: $P(\emptyset) = 0$.
* **Regra da Adição**:
    * **Eventos mutuamente exclusivos**: $P(A \cup B) = P(A) + P(B)$.
    * **Eventos não mutuamente exclusivos**: $P(A \cup B) = P(A) + P(B) - P(A \cap B)$.
* **Regra da Multiplicação**:
    * **Eventos independentes**: $P(A \cap B) = P(A) * P(B)$.
    * **Eventos compostos**: $P(A \cap B) = P(A) * P(B|A)$.
* **Probabilidade Condicional**: $P(A|B) = P(A \cap B) / P(B)$.


## Distribuições:

* **Distribuição Binomial:**
    * Usada para eventos com dois resultados possíveis (sucesso/fracasso).
    * **Fórmula**: $P(X = k) = (n! / (k! * (n-k)!)) * p^k * (1-p)^{n-k}$
        * n: número de tentativas.
        * k: número de sucessos.
        * p: probabilidade de sucesso.
* **Distribuição de Poisson:**
    * Usada para eventos raros que ocorrem em um intervalo de tempo ou espaço.
    * **Fórmula**: $P(X = k) = (e^{-\lambda} * \lambda^k) / k!$.
        * $\lambda$: taxa média de ocorrência.
        * k: número de ocorrências.
        * e: constante ($2.7182818\ldots$)
* **Distribuição Normal:**
    * Distribuição contínua simétrica em forma de sino.
    * Caracterizada pela média ($\mu$) e desvio padrão ($\sigma$).
    * Usada para modelar muitos fenômenos naturais e sociais.
    * Probabilidades calculadas usando a tabela Z ou software estatístico.


## Exemplos

* **Probabilidade de tirar um número par em um dado**: $P(E) = 3/6 = 1/2$.
* **Probabilidade de tirar duas caras em dois lançamentos de moeda**: $P(A \cap B) = (1/2) * (1/2) = 1/4$.
* **Probabilidade de um evento binomial**: $P(X = 2)$ em 5 tentativas com probabilidade de sucesso 0.3.
* **Probabilidade de um evento de Poisson**: $P(X = 3)$ com taxa média de ocorrência 2.
* **Probabilidade de um valor em uma distribuição normal**: $P(X < x)$ usando a tabela Z.
