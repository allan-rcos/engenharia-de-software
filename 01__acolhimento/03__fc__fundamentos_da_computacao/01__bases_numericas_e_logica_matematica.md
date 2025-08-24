# Bases Numéricas

## Breve Histórico

* **Ábaco:** Calculadora para operações algébricas elementares (Mesopotâmia, 2400 a.C.).
* **Calculadoras Mecânicas:**
    * Soma e subtração (Pascal, século XVII).
    * Multiplicação e divisão (Leibnitz, século XVII).
    * Cálculos náuticos (Charles Babbage, século XIX).
* **Mark I (Howard Aiken, 1944):**
    * Computador eletromecânico.
    * Memória, entrada e saída em fita de papel.
* **ENIAC (1946/1947):**
    * Origem do computador moderno.
    * Pesava 30 toneladas e possuía 18.000 válvulas e 70.000 resistores.
* **Bits (binary digit):**
    * Dois estados: desligado (0) ou ligado (1).
* **Sistema Binário (base 2):**
    * Exemplos de conversão decimal para binário (0 a 5).
    * Transformação de binário para decimal (exemplo: 110101 para 53).
    * Transformação de decimal para binário (exemplos: 25 e 32).

## Proposições

### Definição

* Conjunto de palavras ou símbolos que retratam um pensamento de sentido completo e podem ser classificados como verdadeiro (V ou 1) ou falso (F ou 0).
* São objetos fundamentais do estudo da lógica.
* Exemplos: "2 é par", "Tóquio é a capital do Japão", "2 + 3 = 9".

### Princípios Fundamentais

* **Princípio da não contradição:** Uma proposição não pode ser verdadeira e falsa simultaneamente.
* **Princípio do terceiro excluído:** Uma proposição é verdadeira ou falsa, sem um terceiro caso possível.

### Tipos de Proposições

* **Simples:** Uma única afirmação.
    * Exemplo: "Júlia é engenheira."
* **Compostas:** Formadas pela união de proposições simples com conectivos.
    * Exemplos: "Não é verdade que 2 é maior do que 4", "Júlia é engenheira ou professora".

### Conectivos

* Palavras usadas para formar proposições compostas.
* Conectivos comuns: "Não", "e", "ou", "se... então...", "...se, e somente se...".

### Negação (Não: ')

* Inverte o valor lógico da proposição.
* Tabela-verdade da negação.
* Representação com interruptor (fechado/aberto).
* Diagrama de Venn para negação.
* Porta lógica da negação.
* Exemplos: negação de "5 + 1 = 6" e "6 > 7".
* Exercício resolvido: Negação de "Recife é a capital de Pernambuco".

## Conjunção e Disjunção

### Conjunção (e: .)

* Verdadeira somente se ambas as proposições são verdadeiras.
* Tabela-verdade da conjunção.
* Representação com interruptores em série.
* Diagrama de Venn para conjunção.
* Porta lógica da conjunção.
* Exemplos: "2 + 2 = 4 e 5 + 1 = 6", "3 + 2 = 5 e 6 < 2".
* Aplicação: Aprovação com média e frequência.
* Exercício resolvido: Tradução da proposição "p.q" para linguagem corrente.

### Disjunção (ou: +)

* Verdadeira se pelo menos uma das proposições é verdadeira.
* Tabela-verdade da disjunção.
* Representação com interruptores em paralelo.
* Diagrama de Venn para disjunção.
* Porta lógica da disjunção.
* Exemplos: "2 + 2 = 4 ou 5 + 1 = 6", "3 + 2 = 5 ou 6 < 2", "2 + 1 = 10 ou 4 + 4 = 1".
* Exercício resolvido: Valor lógico de "(p + q)'".

### Disjunção Exclusiva (ou exclusivo: ⊕)

* Verdadeira apenas se as proposições têm valores lógicos diferentes.
* Tabela-verdade da disjunção exclusiva.
* Diagrama de Venn para disjunção exclusiva.
* Porta lógica da disjunção exclusiva.
* Exemplos: "João é gaúcho ou pernambucano", "Andressa nasceu de dia ou de noite".
* Exercício resolvido: Valor lógico de "p ⊕ q" quando V(p) = 1 e V(q) = 1.

## Condicional e Bicondicional

### Condicional (se... então...: →)

* Falsa apenas se a primeira proposição é verdadeira e a segunda é falsa.
* Tabela-verdade da condicional.
* Exemplo: "Se cortar a grama, então receberá R$ 50,00".
* Análise das possibilidades e valores lógicos.
* Exercício resolvido: Valor lógico de "Se o pagamento for aprovado, então entregue a mercadoria".

### Bicondicional (...se, e somente se...: ↔)

* Verdadeira se ambas as proposições têm o mesmo valor lógico.
* Tabela-verdade da bicondicional.
* Exemplo: "Ganhará R$ 500.000,00 se, e somente se, receber um prêmio".
* Análise das possibilidades.
* Exercício resolvido: Valor lógico de "p ↔ q" quando p: n é par, q: n² é par e n = 4.

## Circuitos e Portas Lógicas

### Representação de Funções Lógicas

* Uso de operações lógicas para processar informações.
* Representação algébrica, por circuitos e por portas lógicas.

### Exemplos

* Circuito e portas lógicas para "p.(q + r)".
* Portas lógicas para "p + (q.r)".
* Circuito para "p + (p'.(q + r))".
* Expressão associada a um circuito dado: "(a + b).(a + c).(b + d)".