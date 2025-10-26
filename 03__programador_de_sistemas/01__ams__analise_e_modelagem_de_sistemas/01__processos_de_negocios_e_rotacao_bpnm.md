# Processos de Negócio e Notação BPMN

## 1. Introdução à Análise de Sistemas e Temas da Aula

* **Disciplina:** Análise de Sistemas.
* **Importância:** Esta disciplina é fundamental para todo profissional que deseja desenvolver um *software*, pois permite traduzir as necessidades de negócio do cliente em um projeto técnico de *software*.
* **Ferramentas:** Para isso, são usados modelos e documentação.
* **Foco da Aula:** Entender o que são processos de negócio e como representá-los em formato de fluxo, de forma a simplificar o entendimento do que será automatizado por um *software*.
* **Temas desta aula**:
    1.  Entendendo o que são processos de negócios.
    2.  Mapeando os processos AS IS e elaborando o processo TO BE.
    3.  Conhecendo e aplicando a notação BPM em processos de negócios.
    4.  Aprofundando a notação BPMN.
    5.  Analisando um exemplo de modelagem de processo.

## 2. Entendendo o que são Processos de Negócio

* **Interação TI e Negócio:** Pessoas de TI precisam entender como o negócio funciona para projetar sistemas que atendam às necessidades do processo.
* **Definição de Processo de Negócio**:
    * É um conjunto completo e dinamicamente coordenado de atividades colaborativas e transacionais que entrega valor aos clientes.
    * É uma série de passos que um negócio executa para produzir um produto ou serviço.
* **Importância dos Processos:** Ajudam a implementar a estratégia do negócio (visão, missão, valores), são ativos de grande valor, criam diferencial competitivo, refletem como a empresa funciona e são responsáveis pela criação de valor na perspectiva do cliente.
* **Aspectos Organizacionais:** Papéis e responsabilidades precisam estar definidos e as atividades devem ser objetivas e o fluxo de trabalho eficiente. Toda organização executa atividades para alcançar seus objetivos (ex: atender pedidos, recrutar).

## 3. Mapeamento de Processos: AS IS e TO BE

* **Processos AS IS (Como É)**: É a identificação e documentação dos passos do processo conforme são executados no momento do mapeamento, geralmente representado em um fluxo. Permite identificar problemas, falhas e oportunidades de melhoria.
* **Processos TO BE (Como Será)**: É a técnica utilizada para propor um novo processo de negócio ou melhorias no existente, com discussões e documentação da proposta de situação futura (o processo mais eficiente e ágil).
* **Representação**: Ambos são representados por meio de fluxos que mostram os envolvidos, o início, os passos e o encerramento do processo.

## 4. Notação BPM e BPMN

* **BPM (Business Process Management):** Disciplina de gestão para entender o funcionamento dos processos de negócios.
* **BPMN (Business Process Model and Notation):** Notação utilizada para modelar processos de negócios, seguindo a disciplina do BPM.
* **Tarefas (Tasks):** Ocorrem ao longo do processo, e o ator executante é conhecido. Exemplo: "cadastrar cliente".
* **Eventos (Events):** Ações que acontecem com um estímulo direto do ambiente externo, como o evento de "início" que dispara o fluxo do processo.

### Gateways (Portas ou Acessos) - Detalhamento

Gateways atuam como elementos reguladores de fluxo dentro de um modelo de processo, gerenciando a **divergência (bifurcação)** e a **convergência (união)** dos fluxos de atividades.

* **Função:** Direcionar o fluxo de execução com base em condições ou eventos, mas **não realizam ações nem tomam decisões por si mesmos**. A lógica de decisão deve ser incorporada *antes* de chegar ao gateway.
* **Obrigatoriedade:** É crucial que **todos** os pontos de bifurcação ou união no fluxo sejam gerenciados por gateways para evitar ambiguidades.

**Tipos de Gateways (Fluxos de Atividades)**:

1.  **Gateway Exclusivo (XOR):**
    * *Divisão:* O fluxo segue **apenas um caminho** dentre vários possíveis.
    * *União:* Reúne diferentes caminhos em um único fluxo.
2.  **Gateway Inclusivo (OR):**
    * *Divisão:* Permite que **um ou mais caminhos** sejam seguidos.
    * *União:* Sincroniza a convergência, continuando somente após a conclusão de **todos os caminhos que foram ativados**.
3.  **Gateway Paralelo (AND):**
    * *Divisão:* Divide o processo em **múltiplos fluxos que ocorrem em paralelo**.
    * *União:* Espera a conclusão de **todos os fluxos paralelos** antes de prosseguir.
4.  **Gateway Complexo:**
    * *Divisão e União:* Permite a modelagem de comportamentos mais complexos que não se encaixam nas categorias anteriores, usando expressões condicionais.

**Tipos de Gateways (Fluxos Orientados a Eventos)**:

5.  **Gateway de Evento (Event-based):**
    * *Divisão e União:* A decisão para o caminho a seguir é baseada na **ocorrência de um evento específico**, e não em uma avaliação de condição.
6.  **Gateway de Evento para Iniciar um Processo (Event-based to Start a Process):**
    * *Divisão:* Usado para iniciar um processo com base na ocorrência de **um evento específico** (dentre vários), atuando como um ponto de partida condicional. Não é usado para união.
7.  **Gateway Paralelo Baseado em Eventos para Iniciar um Processo (Parallel Event-Based to Start a Process):**
    * *Divisão:* Requer que **todos os eventos especificados ocorram em paralelo** para que o processo seja iniciado. Não é usado para união.

## 5. Estudo de Caso para Modelagem de Processo

* **Finalidade:** O estudo de caso será utilizado em todas as aulas da disciplina para aplicar a análise de sistemas na construção de um *software*.
* **Cenário:** Modelagem do processo de vendas *online* de livros.
* **Detalhes do Cliente:** Livraria virtual com site próprio. Possui estoque próprio (o que garante entrega rápida) e aceita vários tipos de pagamento (cartão de crédito, débito, boleto). A livraria possui um programa de fidelidade que oferece desconto de 10% para clientes que comprarem R\$ 500,00 ou mais em 1 ano.