# Histórico e Diagrama de Fluxos de Dados

#### **Conversa Inicial**

**Modelagem de Processos de Negócio**
* Analisar, projetar e desenvolver um *software* é uma atividade complexa, que envolve necessidades dos clientes, regras de negócios e tecnologia.
* Por isso, precisa ser muito bem planejada e estrategicamente pensada para ser o mais eficiente possível na solução do problema pretendido.
* Não basta atender aos requisitos de negócio, é preciso ter um processamento rápido e eficiente.

**Objetivos da Aula**
* Conhecer o que é a análise estruturada, como ela surgiu e como um *software* pode ser projetado seguindo seus preceitos.
* Conhecer o que é um DFD (Diagrama de Fluxo de Dados) e como ele ajuda a analisar o funcionamento de um *software*.

**Organização da Aula**
1.  Análise de sistemas - a história
2.  Análise estruturada
3.  Diagrama de fluxo de dados (DFD)
4.  Níveis de um DFD
5.  Analisando um exemplo de DFD

---

### **1. Análise de Sistemas - A História**

* A análise de sistemas tem como finalidade a realização de estudos a fim de encontrar o melhor caminho lógico para que a informação seja processada.
* Segundo Pressman (2016), a análise de sistemas é uma prática baseada em modelos, com o objetivo de obter um melhor entendimento da entidade real a ser construída.
* A modelagem do *software* precisa mostrar a solução a ser construída em diferentes níveis de abstração.
* É preciso mostrar o *software* do ponto de vista dos clientes e do ponto de vista técnico, de forma a permitir analisar a viabilidade de implementação dos requisitos de negócio.
* A evolução da análise de sistemas propôs três grandes métodos de modelagem de sistemas: modelagem estruturada, modelagem essencial e modelagem orientada a objetos.

**Análise x Projeto**
* O principal objetivo da análise é produzir uma especificação do sistema que defina a estrutura do problema a ser resolvido.
* Isso deve estar de acordo com a visão do usuário e na linguagem que possa ser entendida pela equipe técnica.
* Serve para definir a estrutura do problema com os requisitos do usuário, estruturando a implementação que será dada para a solução.

---

### **2. Análise Estruturada**

* Está fundamentada na **decomposição funcional** do problema, focando nas funcionalidades que o *software* deve entregar.
* O objetivo principal é a construção de um **modelo lógico**, e não de um modelo físico de sistema.
* Busca compreender a lógica por trás de cada funcionalidade que precisa ser desenvolvida no *software*.
* Utiliza técnicas gráficas; os modelos produzidos precisam levar usuários, analistas e projetistas a formarem um quadro claro e geral do sistema.
* Mesmo sendo um método mais antigo, a análise estruturada ainda é encontrada, principalmente, em empresas que possuem sistemas legados e que precisam ser mantidos e evoluídos.
* É preciso manter a documentação quando um *software* evolui, pois a documentação é conhecimento sobre o *software*.

**Benefícios da Análise Estruturada**
* Os usuários conseguem ter uma ideia mais clara do sistema proposto com o uso do DFD, em comparação com narrativa e fluxograma de sistemas físicos.
* As interfaces entre o novo sistema e outros sistemas já existentes são mostradas de modo bem mais claro, facilitando a compreensão da comunicação entre eles.

**Problemas da Análise Estruturada**
* O esforço, a formalidade e o grau de detalhe necessários (especialmente na construção do dicionário de dados) geram resistência dos analistas de sistemas.
* Toda documentação deve ser mantida, evoluindo junto com as modificações nos requisitos do *software*.
* Uma documentação desatualizada pode ser fonte de confusão e desinformação em um projeto.

---

### **3. Diagrama de Fluxo de Dados (DFD)**

* O DFD é uma das ferramentas mais utilizadas na análise estruturada.
* Serve para compreender e analisar o fluxo de dados: dentro do próprio sistema e entre o mundo exterior com o sistema, detalhando dados que entram e que saem.
* Possui uma representação em rede.
* O objetivo principal é mostrar **o que** o sistema vai fazer, e não **como** será feita a solução tecnicamente (pois é o momento de análise, e não de projeto).

**Recomendações para Criação de DFDs:**
* Escolha de nomes significativos para os componentes.
* Numerar os processos para facilitar a referência em documentação escrita.
* Criar e ajustar o diagrama visando a uma boa estética e comunicação adequada.
* Evitar DFDs muito complexos; o visual bem organizado é fundamental à compreensão do todo.

---

### **4. Níveis de um DFD**

* Para evitar um diagrama único e difícil de entender, criam-se DFDs que detalham um processo de um nível mais alto para o mais baixo.
* É mais fácil entender o todo através de partes menores, quebrando o detalhamento em níveis de aprofundamento maiores.
* Os diferentes níveis de entendimento devem ser consistentes internamente e com os demais níveis relacionados.
* A quantidade de níveis depende da complexidade e porte do sistema.

**DFD de Contexto**
* É o DFD de nível mais alto, que dá a visão das principais funções do sistema.
* Representa o sistema como um todo, os principais fluxos de dados e os agentes externos.
* *Exemplo:* O círculo "Sistema de vendas" interage com "Setor de vendas" (recebe "Pedido"), "Setor de logística" (envia "Fatura"), "Sistema financeiro" (envia "Cobrança") e "Setor de pós-vendas" (recebe "Fatura").

**DFD de Nível Zero**
* Após a visão macro, analisa os principais processos do *software*, detalhando fluxos e entidades.
* Encontra detalhes sobre as principais funcionalidades do *software*.

**DFD de Nível Intermediário**
* Mostram a decomposição, detalhamento ou a explosão de cada processo de nível mais alto.
* Cada nível detalha mais o nível imediatamente anterior.
* *Exemplo de decomposição do processo "Processar pedido" em:* "2.1. Gerar cobrança" e "2.2. Gerar fatura".

---

### **5. Analisando um Exemplo de DFD**

**Estudo de Caso**
* **Contexto:** Modelar o processo de vendas *on-line* de livros para uma livraria virtual.
* **Diferenciais:** Possui estoque próprio (entrega rápida) e aceita vários tipos de pagamento (cartão de crédito/débito, boleto bancário).
* **Programa de Fidelidade:** Desconto de 10% aos clientes que comprarem R$ 500,00 ou mais em 1 ano.

**DFD de Nível Zero (Estudo de Caso)**
O diagrama representa o sistema de vendas, mostrando:
* **Agentes Externos (Terminadores):** Consumidor, Setor de logística, Sistema contábil e financeiro.
* **Processos:** 1. Carrinho de compra, 2. Processa pagamento.
* **Armazenamentos de Dados:** D1 - Clientes, D2 - Pedidos, D3 - Fidelidade.
* **Fluxos de Dados:** Pedido, Fatura, Envio, Pagamento não processado.

---

### **Prática**

A prática detalha o processo **1. Carrinho de compra** do DFD de Nível Zero do estudo de caso.

**DFD de Nível 1 (Detalhando o Processo 1: Carrinho de compra)**
* **Agente Externo:** Consumidor.
* **Armazenamentos:** D2 - Pedidos.
* **Processos (e fluxos):**
    * **1.1. Iniciar compra:** Recebe "Pedido" do Consumidor. Envia "Número do pedido" para D2 - Pedidos e "Carrinho" para o processo 1.2.
    * **1.2. Inserir itens no carrinho:** Recebe "Carrinho" de 1.1 e "Item escolhido" do Consumidor. Envia "Carrinho com itens" para o processo 1.3.
    * **1.3. Fechar carrinho:** Recebe "Carrinho com itens" de 1.2. Envia "Status do pedido" para D2 - Pedidos e "Pedido fechado" para o processo 2. Processa pagamento.