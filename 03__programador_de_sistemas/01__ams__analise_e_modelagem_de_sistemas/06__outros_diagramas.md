# Diagramas Importantes da UML (Unified Modeling Language) em Análise de Sistemas

Esta aula aborda diagramas que modelam aspectos específicos e dinâmicos de um software.

### 1. Diagrama de Estado (Máquina de Estados)

* **Propósito:** Representa o **comportamento dinâmico** de um objeto, mostrando a sequência de estados pelos quais ele passa e os eventos que causam a mudança de um estado para outro.
* **Uso:** Recomendado apenas para modelar objetos com um grau de complexidade na transição de seus estados.
* **Elementos Chave:**
    * **Estado:** A condição do objeto em um determinado momento (o tempo entre os eventos).
    * **Evento:** Ocorrência que gera a mudança de estado (pode ser externo, interno ou temporal).
    * **Transição:** Relacionamento entre dois estados que indica a mudança após a ocorrência de um evento.
    * **Objeto:** O elemento que tem seu estado alterado.

### 2. Diagrama de Atividades

* **Propósito:** Descrever a lógica de uma funcionalidade, um processo de negócio ou um fluxo de trabalho, enfatizando o fluxo de controle entre as atividades. É a forma da UML para modelar processos automatizados por software.
* **Conceito:** Para modelar, um processo é decomposto em atividades, identificando se são sequenciais, concorrentes ou paralelas.
* **Elementos Chave:**
    * **Atividades:** As ações a serem executadas.
    * **Transição:** O caminho seguido ao longo do fluxo do processo.
    * **Estado Inicial e Final:** Indicam o ponto de partida e o(s) ponto(s) de término do processo.
    * **Decisões:** Controlam desvios no fluxo por meio de expressões lógicas (losango).
    * **Bifurcação (Fork):** Divide o fluxo para a execução de atividades paralelas/concorrentes.
    * **União (Join):** Sincroniza as atividades paralelas em um único fluxo.
    * **Raias (Swimlanes):** Organização lógica das atividades associadas a objetos, usuários ou atores (por exemplo, "Cliente", "Vendas", "Estoque").

### 3. Diagrama de Sequência

* **Propósito:** Ilustrar a **sequência de mensagens** trocadas entre objetos em uma interação, enfatizando a **ordenação temporal**.
* **Representação:**
    * **Horizontal:** O conjunto de objetos envolvidos.
    * **Vertical:** O tempo de vida dos objetos.
* **Elementos Chave:**
    * **Ator:** O iniciador da interação (usuário, sistema externo, ou funcionalidade).
    * **Linha de Vida (Lifeline):** A instância de um componente que representa seu tempo de existência e por onde as mensagens trafegam.
    * **Mensagem:** O serviço solicitado ou informação trocada, representada por uma seta na direção do fluxo.
    * **Fragmento:** Estrutura utilizada para tratar condições lógicas (`if/else`, `loop`) ou exceções no fluxo de mensagens.

### 4. Diagrama de Componentes

* **Propósito:** Apresentar a **visão física** e arquitetural do software, mostrando os módulos ou pacotes (componentes) que o compõem e as dependências entre eles. Está relacionado à arquitetura de software definida como solução técnica.
* **Componente:** Módulo de classes com identidade e interface bem definidas, representando sistemas ou subsistemas independentes que interagem com o restante do sistema.
* **Conceito:** Baseia-se na abordagem de **Desenvolvimento Baseado em Componentes (CBD)**, atrelado à análise e ao desenvolvimento orientado a objetos.
* **Aplicação:** Modelar a estrutura física em camadas arquiteturais (ex: camada `clients`, camada de `negócios` com `Controllas` e `Model`), conferindo organização e segurança ao código.
* **Exemplo (Estudo de Caso Livraria Virtual):** Baseado nos casos de uso, os componentes principais poderiam ser: **Cliente**, **Fidelidade** e **Pedido**.
