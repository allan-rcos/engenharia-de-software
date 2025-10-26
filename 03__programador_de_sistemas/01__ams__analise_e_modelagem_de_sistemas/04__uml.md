# AULA 4: UML E DIAGRAMA DE CASO DE USO

### CONVERSA INICIAL: A Importância da Análise de Sistemas

A Análise de Sistemas é fundamental para o profissional que desenvolve *software*, pois permite traduzir as necessidades de negócio do cliente em um projeto técnico.

* **Necessidade:** Projetar e construir um programa de computador exige conhecer o problema e traduzir a solução ideal em código.
* **Base:** A base para todo *software* bem-construído está no **levantamento e na análise adequada e completa dos seus requisitos**.
* **Foco da Aula:** Introdução à **Unified Modelling Language (UML)** e ao **Diagrama de Casos de Uso**.

**Organização do Conteúdo:**
1.  O que é UML.
2.  Modelo Orientado a Objetos.
3.  Técnicas de construção do diagrama de casos de uso.
4.  Componentes de um diagrama de caso de uso.
5.  Analisando um exemplo de diagrama de caso de uso (Estudo de Caso).

---

### 1. O QUE É UML (Unified Modelling Language)

* **Definição:** UML é uma **linguagem ou notação de diagramas** para especificar, visualizar e documentar modelos de *software* desenvolvidos sob a perspectiva da orientação por objetos.
* **Função:** A UML é uma ferramenta de **visualização e comunicação**. Sua padronização facilita o entendimento do modelo por todos os envolvidos no projeto.
* **Natureza:** Não é um método de desenvolvimento, mas uma linguagem de modelagem que padroniza como as estruturas e o comportamento de um sistema devem ser representados.
* **Origem:** A UML nasceu da união dos esforços de Grady Booch, James Rumbaugh e Ivar Jacobson para criar uma notação de modelagem orientada a objetos consistente.

#### Modelos na UML
Um modelo é uma simplificação da realidade, construída para melhor compreender um sistema. Na UML, os modelos são expressos por duas visões:

1.  **Visão Estrutural (Estática):** Captura a estrutura do sistema – quais elementos o compõem e como se relacionam (ex: Diagrama de Classes).
2.  **Visão Comportamental (Dinâmica):** Captura a dinâmica do sistema – como os elementos se comunicam, se comportam e respondem a estímulos (ex: Diagrama de Caso de Uso, Diagrama de Sequência).

---

### 2. MODELO ORIENTADO A OBJETOS (OO)

A UML é fundamentada nos conceitos da Orientação a Objetos.

#### Conceitos Fundamentais
* **Objeto:** Entidade do mundo real (real ou abstrata) com **identidade**, **estado** (atributos) e **comportamento** (operações).
* **Atributos:** As características ou propriedades que definem o estado de um objeto.
* **Operações/Métodos:** As ações que um objeto pode realizar.
* **Classe:** O molde ou a forma que define os atributos e operações comuns de um conjunto de objetos.

#### Pilares da Orientação a Objetos
1.  **Abstração:** Focar nos aspectos essenciais de uma entidade e ignorar os detalhes não relevantes, simplificando conceitos complexos.
2.  **Encapsulamento:** Separação entre os aspectos externos (interface) e os detalhes internos da implementação, restringindo o acesso e promovendo o isolamento das partes do *software*.
3.  **Herança:** Mecanismo que permite o compartilhamento de atributos e operações entre objetos em uma hierarquia, promovendo a reutilização de código.
4.  **Polimorfismo:** Capacidade de objetos diferentes responderem à mesma mensagem ou operação de maneiras específicas.

---

### 3. TÉCNICAS DE CONSTRUÇÃO DO DIAGRAMA DE CASO DE USO

O Diagrama de Caso de Uso é um diagrama comportamental usado para modelar as funcionalidades do sistema e o relacionamento com seus usuários.

* **Propósito:** Modelar os requisitos funcionais do sistema a partir da perspectiva do usuário.
* **Visão:** Oferece uma **visão externa e funcional**, focando no *o quê* o sistema faz, e não no *como* ele faz.
* **Utilidade:** Serve como documento de comunicação simples e intuitivo para clientes e desenvolvedores.

**Passos para a Construção:**
1.  Identificar os **Atores** que interagem com o sistema.
2.  Identificar os **Casos de Uso** (funcionalidades) que o sistema deve fornecer.
3.  Desenhar a **Fronteira do Sistema** (o escopo).
4.  Ligar Atores e Casos de Uso (Associação).
5.  Modelar os Relacionamentos entre Casos de Uso (include, extend, generalização).
6.  Complementar o diagrama com a **Descrição dos Casos de Uso** (fluxos principal, alternativos e de exceção).

---

### 4. COMPONENTES DE UM DIAGRAMA DE CASO DE USO

| Elemento | Representação | Descrição |
| :--- | :--- | :--- |
| **Ator** | Boneco (Stickman) | O papel desempenhado por uma entidade **externa** que interage com o sistema (pessoa, *hardware* ou outro sistema). |
| **Caso de Uso** | Elipse (Oval) | Uma funcionalidade, serviço ou tarefa que o sistema deve executar para um ator. **É uma parte do sistema.** |
| **Fronteira do Sistema** | Retângulo | Delimita o escopo e o limite do sistema a ser modelado. |
| **Associação** | Linha Reta | Representa o relacionamento de **comunicação** entre um Ator e um Caso de Uso. |

#### Relacionamentos entre Casos de Uso
1.  **`<<include>>` (Inclusão):**
    * **Indicação:** O caso de uso incluído é **essencial** e **obrigatoriamente** executado pelo caso de uso base.
    * **Significado:** B é parte de A.
2.  **`<<extend>>` (Extensão):**
    * **Indicação:** O caso de uso de extensão **pode ser acrescentado** ao caso de uso base, mas **não é essencial**. A execução é opcional e condicionada por uma regra de negócio, ocorrendo em um Ponto de Extensão.
3.  **Generalização (Herança):**
    * **Uso:** Representa a herança de comportamento entre Atores ou entre Casos de Uso. Um elemento mais específico herda e complementa o comportamento de um elemento mais geral.

---

### 5. ESTUDO DE CASO: Livraria Virtual

#### Cenário do Problema
Modelar o processo de vendas *on-line* de livros para uma livraria virtual.
* **Diferenciais:** Estoque próprio (entrega rápida) e aceita vários tipos de pagamento (Cartão de Crédito, Cartão de Débito e Boleto Bancário).
* **Programa de Fidelidade:** Desconto de 10% aos clientes que comprarem **R\$ 500,00 ou mais em 1 ano**.

#### Análise e Modelagem
* **Atores Identificados:** Consumidor, Área de Vendas, Sistema Contábil, Sistema Financeiro.
* **Casos de Uso Envolvidos:** `Selecionar itens`, `Efetuar login`, `Efetuar compra`, `Cadastrar Livros`, `Consultar Vendas`, `Enviar Faturamento`, `Validar Pagamento`.
* **Aplicação de Relacionamentos:** O diagrama deve mostrar como as funcionalidades se relacionam (exemplo: `Efetuar Compra` **inclui** `Validar Pagamento`, e `Validar Pagamento` **pode ser estendido** por `Aplicar Desconto Fidelidade` sob a condição de R\$ 500,00 anuais).

**Conclusão da Análise:** O Diagrama de Caso de Uso e a descrição textual dos casos de uso formam a base de análise para a próxima etapa, que é a modelagem da parte física (*design*) do *software* com o Diagrama de Classes.