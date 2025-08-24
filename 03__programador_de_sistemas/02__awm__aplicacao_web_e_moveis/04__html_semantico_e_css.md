## HTML Semântico e CSS

### HTML Semântico

* **O que é?** O HTML semântico utiliza tags para descrever o significado do conteúdo, em vez de apenas sua aparência. Isso proporciona um significado claro para a página, beneficiando desenvolvedores, navegadores e ferramentas de busca.
* **Elementos Semânticos Mais Comuns**: A HTML5 introduziu tags para estruturar o conteúdo de forma mais significativa, incluindo:
    * `<header>`: Define o cabeçalho de uma seção ou página.
    * `<nav>`: Define um conjunto de links de navegação.
    * `<main>`: Define o conteúdo principal e único de um documento.
    * `<section>`: Define uma seção de um documento.
    * `<article>`: Define um conteúdo autossuficiente, como um post de blog ou uma notícia.
    * `<aside>`: Define um conteúdo relacionado, mas separado do conteúdo principal, como uma barra lateral.
    * `<footer>`: Define o rodapé de uma seção ou página.
* **Benefícios**: O uso de HTML semântico melhora a acessibilidade, o SEO e torna o código mais fácil de ler e manter.

### CSS - Folhas de Estilo em Cascata

* **O que é?** O CSS é uma linguagem de estilo usada para descrever a apresentação de documentos HTML. Ele separa o conteúdo da sua apresentação, facilitando o gerenciamento do design de várias páginas.
* **Sintaxe**: Uma regra CSS é composta por um seletor e um bloco de declaração. O seletor aponta para o elemento HTML, e o bloco de declaração contém propriedades e seus valores.

### Box Model

* **O que é?** O Box Model é o modelo de caixa que representa todo elemento HTML. É composto por quatro partes:
    * **Conteúdo (Content)**: Onde o texto e as imagens aparecem.
    * **Preenchimento (Padding)**: A área transparente ao redor do conteúdo, dentro da borda.
    * **Borda (Border)**: A borda que envolve o preenchimento e o conteúdo.
    * **Margem (Margin)**: A área externa à borda, que separa o elemento dos outros.

### Seletores CSS

* **Tipos de Seletores**:
    * **Elemento**: Seleciona elementos pelo nome da tag (ex: `p`, `h1`).
    * **ID**: Seleciona um único elemento com um `id` específico (ex: `#exemplo`).
    * **Classe**: Seleciona todos os elementos com a mesma `class` (ex: `.exemplo`).
    * **Universal**: Seleciona todos os elementos na página (ex: `*`).
    * **Agrupamento**: Permite aplicar o mesmo estilo a múltiplos seletores, separando-os por vírgula (ex: `h1, h2, p`).
* **Seletores de Combinadores**:
    * **Descendente**: Seleciona elementos que são descendentes de outro seletor (ex: `div p`).
    * **Filho Direto**: Seleciona elementos que são filhos diretos de um seletor (ex: `div > p`).
    * **Irmão Adjacente**: Seleciona um elemento que é imediatamente precedido por outro (ex: `div + p`).
    * **Irmão Geral**: Seleciona todos os elementos que são irmãos de um elemento específico (ex: `div ~ p`).

### CSS Avançado

* **Herança**: Propriedades CSS são herdadas de elementos pais para seus filhos.
* **Cascata**: É o processo que determina qual regra de estilo será aplicada, com uma ordem de prioridade que vai de `!important` a seletores de elemento.
* **Unidades de Medida**:
    * **Relativas**: Medidas baseadas em outros elementos ou na viewport, como `em`, `rem`, `vw`, `vh`.
    * **Absolutas**: Medidas fixas que não mudam, como `px`, `pt`, `cm`. É preferível o uso de unidades relativas para layouts responsivos.

### Grid Layout

* **O que é?** Uma técnica para criar layouts em duas dimensões, utilizando linhas e colunas. É ideal para layouts complexos de página inteira, oferecendo controle preciso sobre a posição e alinhamento dos elementos.
* **Componentes**:
    * **Grid Container**: O elemento pai que define o layout de grade.
    * **Grid Items**: Os elementos filhos diretos dentro do container.
* **Propriedades do Grid Container**: `display: grid`, `grid-template-columns`, `grid-template-rows` e `gap` são usadas para definir a estrutura da grade.
* **Propriedades do Grid Item**: `grid-column-start`, `grid-column-end`, `grid-row-start` e `grid-row-end` são usadas para posicionar os itens. A função `repeat()` pode ser usada para definir repetições de um valor.

### Flexbox

* **O que é?** Uma técnica para criar layouts em uma dimensão, seja em linhas ou colunas. É ideal para distribuir e alinhar itens em um contêiner, como em uma barra de navegação.

### Media Queries

* **O que são?** Uma técnica CSS que aplica estilos somente se uma condição específica for verdadeira, sendo essencial para o design responsivo.
* **O que verificam**: Largura e altura da viewport, orientação do dispositivo e resolução.

### Imagens Responsivas

* **Técnicas**:
    * **CSS**: Usar `max-width: 100%` para que a imagem se adapte à largura do seu contêiner.
    * **HTML**: Utilizar o elemento `<picture>` e o atributo `srcset` para fornecer diferentes imagens para diferentes tamanhos de tela ou densidades de pixel.