### **Árvore do Documento (DOM)**

O DOM (Document Object Model) é uma estrutura em forma de árvore que representa a hierarquia e as relações entre os elementos de uma página HTML. Entender o DOM é crucial para a aplicação de CSS, pois algumas propriedades de estilo são herdadas de elementos pais para seus filhos, como a cor da fonte, enquanto outras não, como a largura (`width`).

* **Graus de parentesco:**
    * **Pai e Filho**: Um elemento pai contém um ou mais elementos filhos.
    * **Ancestral e Descendente**: Um ancestral é um elemento que contém outro, que é seu descendente.
    * **Irmãos**: Elementos que compartilham o mesmo elemento pai.

---

### **Seletores CSS Avançados**

O CSS permite a estilização de elementos com base em seu relacionamento na árvore do documento.

* **Descendente (`E F`)**: Seleciona o elemento `F` que está contido em `E`.
* **Filho Direto (`E > F`)**: Seleciona o elemento `F` que é filho direto de `E`.
* **Irmão Adjacente (`E + F`)**: Seleciona o elemento `F` que vem imediatamente após `E`.
* **Irmão Geral (`E ~ F`)**: Seleciona o elemento `F` que vem depois de `E`, não necessariamente de forma imediata.
* **Primeiro Filho (`E:first-child`)**: Seleciona `E` que é o primeiro filho de seu elemento pai.
* **Último Filho (`E:last-child`)**: Seleciona `E` que é o último filho de seu elemento pai.

---

### **Pseudoclasses e Pseudoelementos**

* **Pseudoclasses**: Permitem selecionar elementos com base em um estado ou comportamento, utilizando a sintaxe `seletor:pseudoclasse`.
    * **Links**: Para links, a ordem de estilização correta é `:link` (não visitado), `:visited` (visitado), `:hover` (mouse sobre) e `:active` (clicado).
    * **Formulários**: Existem pseudoclasses como `:focus` (elemento em foco), `:checked` (elemento selecionado), `:enabled` (habilitado) e `:disabled` (desabilitado).

* **Pseudoelementos**: Permitem estilizar partes específicas de um elemento, como a primeira letra ou a primeira linha de um parágrafo.
