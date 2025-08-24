### **Introdução ao CSS**

O CSS (Cascading Style Sheets) é uma linguagem de estilo utilizada para definir a apresentação e o layout de documentos HTML. Enquanto o HTML cuida da estrutura e do conteúdo, o CSS é responsável por cores, fontes, espaçamentos e posicionamento. A separação entre estrutura (HTML) e estilo (CSS) facilita a manutenção e a reutilização do código, além de melhorar a acessibilidade e o controle sobre a apresentação da página.

---

### **Sintaxe e Regras CSS**

Uma regra CSS é composta por um seletor e um bloco de declaração.
* **Seletor**: Aponta para o elemento HTML que você deseja estilizar. Pode ser um nome de tag, uma classe ou um ID.
* **Bloco de Declaração**: Contém uma ou mais declarações, cada uma composta por uma propriedade e um valor, separados por dois pontos.
    * **Propriedade**: O aspecto do elemento que você deseja mudar (ex: `color`, `font-size`).
    * **Valor**: O valor a ser atribuído à propriedade (ex: `blue`, `12px`).
    * As declarações são separadas por ponto e vírgula.

Exemplo de sintaxe: `seletor { propriedade: valor; propriedade: valor; }`.

---

### **Como Incluir CSS no HTML**

Existem três formas de aplicar estilos CSS a um documento HTML:
* **Estilo Externo**: É a forma mais recomendada. O código CSS é escrito em um arquivo separado (`.css`) e linkado ao HTML através da tag `<link>` no `<head>`. Isso permite que um único arquivo CSS controle a aparência de várias páginas.
* **Estilo Interno**: O código CSS é inserido dentro da tag `<style>` no `<head>` do documento HTML. É útil para estilizar uma única página.
* **Estilo em Linha (Inline)**: O estilo é aplicado diretamente a um elemento HTML usando o atributo `style`. Essa abordagem não é recomendada para a maioria dos casos, pois mistura conteúdo e estilo, dificultando a manutenção.

---

### **Seletores CSS Comuns**

* **Seletor de Tipo**: Seleciona todos os elementos de um tipo específico (ex: `p` seleciona todos os parágrafos).
* **Seletor de Classe**: Seleciona elementos com um atributo `class` específico. É representado por um ponto (`.`) seguido do nome da classe (ex: `.minha-classe`).
* **Seletor de ID**: Seleciona um único elemento com um atributo `id` específico. É representado por um cerquilha (`#`) seguido do nome do ID (ex: `#meu-id`).

---

### **Unidades de Medida**

O CSS utiliza diversas unidades de medida para definir tamanhos e espaçamentos:
* **Pixels (`px`)**: Unidade fixa e absoluta, ideal para elementos que precisam de um tamanho exato.
* **Percentagem (`%`)**: Unidade relativa, que se baseia no tamanho do elemento pai.
* **`em`**: Unidade relativa ao tamanho da fonte do elemento pai.
* **`rem`**: Unidade relativa ao tamanho da fonte do elemento raiz (`<html>`).

---

### **Modelo de Caixa (Box Model)**

O modelo de caixa descreve como os elementos HTML são renderizados na página, considerando que cada elemento é uma caixa retangular. Ele é composto por quatro partes:
* **Conteúdo (Content)**: Onde o texto e as imagens aparecem.
* **Preenchimento (Padding)**: O espaço entre a borda e o conteúdo.
* **Borda (Border)**: A linha que envolve o preenchimento e o conteúdo.
* **Margem (Margin)**: O espaço externo à borda, que separa o elemento dos outros.
