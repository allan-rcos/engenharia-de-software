### **Conceitos Iniciais e HTML**

A internet é uma rede global de computadores que se comunicam através de protocolos. A World Wide Web (WWW) é um dos serviços mais populares da internet, utilizando hipertexto para conectar documentos e recursos. O HTML (HyperText Markup Language) é a linguagem de marcação padrão para criar páginas web, definindo a estrutura e o conteúdo, mas não a aparência.

---

### **Estrutura de um Documento HTML**

Um documento HTML básico possui uma estrutura com as seguintes tags:
* `<!DOCTYPE html>`: Declaração que define o tipo de documento.
* `<html>`: O elemento raiz de toda a página.
* `<head>`: Contém metadados sobre o documento, como o título da página e links para arquivos CSS.
    * `<meta>`: Fornece metadados, como a codificação de caracteres (`charset="UTF-8"`).
    * `<title>`: Define o título que aparece na barra do navegador.
* `<body>`: Contém o conteúdo visível da página, como títulos, parágrafos e imagens.

---

### **Principais Tags e Elementos**

* **Títulos**: O HTML possui seis níveis de títulos, de `<h1>` (o mais importante) a `<h6>` (o menos importante).
* **Parágrafos**: A tag `<p>` é usada para criar parágrafos de texto.
* **Listas**:
    * `<ol>`: Cria uma lista ordenada, onde os itens são numerados.
    * `<ul>`: Cria uma lista não ordenada, onde os itens são marcados com pontos.
    * `<li>`: Define um item dentro de uma lista ordenada ou não ordenada.
* **Links**: A tag `<a>` (âncora) cria um hiperlink, com o atributo `href` especificando o destino.
* **Imagens**: A tag `<img>` é usada para incorporar imagens, com o atributo `src` especificando o caminho do arquivo e `alt` fornecendo um texto alternativo para acessibilidade.
* **Formatação de Texto**:
    * `<strong>` ou `<b>`: Deixa o texto em negrito, indicando maior importância.
    * `<em>` ou `<i>`: Deixa o texto em itálico, enfatizando-o.
    * `<u>`: Sublinha o texto.
* **Divisões e Agrupamentos**:
    * `<div>`: Um contêiner genérico de nível de bloco para agrupar elementos.
    * `<span>`: Um contêiner genérico de nível de linha para agrupar elementos.

---

### **Desenvolvimento Web e Ferramentas**

O desenvolvimento web abrange a criação, manutenção e otimização de websites. O HTML é a base, mas é complementado por:
* **CSS (Cascading Style Sheets)**: Usado para estilizar a aparência dos elementos HTML.
* **JavaScript**: Linguagem de programação para adicionar interatividade e dinamismo às páginas.
* **Ferramentas de Desenvolvimento**:
    * **Navegadores**: São usados para renderizar as páginas web.
    * **Editores de Código**: Ferramentas como VS Code, Sublime Text, etc., facilitam a escrita do código.

---

### **Acessibilidade Web**

A acessibilidade é a prática de garantir que os websites possam ser usados por todas as pessoas, independentemente de suas habilidades ou deficiências. É importante incluir:
* **Texto Alternativo em Imagens**: O atributo `alt` na tag `<img>` é fundamental para que leitores de tela descrevam o conteúdo das imagens.
* **Hierarquia Correta de Títulos**: Usar `<h1>` a `<h6>` de forma lógica e hierárquica facilita a navegação.
* **Contraste de Cores**: Garantir que o texto seja legível em relação ao fundo.
* 