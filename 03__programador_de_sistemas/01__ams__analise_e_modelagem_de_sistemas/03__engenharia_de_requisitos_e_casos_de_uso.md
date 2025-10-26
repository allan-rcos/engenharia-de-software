# Engenharia de Requisitos e Casos de Uso

### 1\. Introdução à Análise de Sistemas e Engenharia de Requisitos

Projetar e construir um programa de computador não é uma tarefa trivial, pois envolve conhecer bem o problema do cliente e definir a solução ideal para atender às suas necessidades.

O objetivo da aula é detalhar a engenharia de requisitos, incluindo o que é e como levantar e gerenciar os requisitos do *software*. O detalhamento claro e direto dos requisitos facilita o entendimento do que o *software* deve fazer.

**Organização da Aula**:

1.  Engenharia de requisitos.
2.  Requisitos funcionais e requisitos não funcionais.
3.  Documentando requisitos funcionais por meio de casos de uso.
4.  Estórias de usuário.
5.  Analisando um exemplo de descrição de caso de uso.

### 2\. Engenharia de Requisitos

A Engenharia de Requisitos é a área essencial para o desenvolvimento de *software*.

  * **Definição (Segundo Pressman, 2016)**: "Entender os requisitos de um problema está entre as tarefas mais difíceis enfrentadas por um engenheiro de *software*".
  * **Função dos Requisitos**: Os requisitos definem o que as partes interessadas necessitam em um novo sistema e o que o sistema deve fazer para satisfazer essas necessidades.

**Ciclo de Vida da Engenharia de *Software* (Fases da Engenharia de Requisitos)**:

1.  **Concepção**: Compreender o problema a ser resolvido, entendendo o cenário de atuação e as necessidades do cliente no nível macro.
2.  **Levantamento**: Momento em que os analistas de requisitos começam a entrevistar os usuários e a compreender, em detalhes, como os requisitos deverão funcionar.
3.  **Elaboração**: As informações obtidas durante a concepção e o levantamento são expandidas e refinadas. O principal objetivo é desenvolver um modelo técnico refinado das funcionalidades.
4.  **Negociação**: Os requisitos levantados e detalhados são revisados e validados ou não pelos usuários.
5.  **Especificação**: Fase em que o projeto de construção de *software* já pode ser desenvolvido, baseado nos requisitos priorizados e detalhados. É a transição da fase de análise dos requisitos para a fase de projeto técnico da solução, que implementará e transformará os requisitos em um *software* usual.
6.  **Validação**: Exame da especificação para garantir que todos os requisitos necessários foram identificados e especificados, estando claros e coerentes entre si.
7.  **Gestão de Requisitos**: Conjunto de atividades que ajudam na identificação, controle, rastreamento e modificação dos requisitos ao longo do tempo.

### 3\. Requisitos Funcionais e Requisitos Não Funcionais

#### Requisitos Funcionais

  * **Definição**: Definem funções e funcionalidades que o sistema de *software* deve executar.
  * **Importância**: São a base de todo o projeto; se um requisito funcional não estiver correto, o funcionamento do *software* estará comprometido.
  * **Representação**: Define uma função particular de um sistema ou de algum de seus componentes, representando **"o que o *software* faz"** em termos de tarefas e serviços (funcionalidades).

#### Requisitos Não Funcionais

  * **Definição**: Referem-se aos critérios que qualificam os requisitos funcionais.
  * **Exemplos**: Critérios de qualidade para o *software*, como *performance*, usabilidade, confiabilidade, robustez etc..

### 4\. Documentando Requisitos Funcionais por meio de Casos de Uso

O **Caso de Uso** (UC) é uma ferramenta para a documentação de requisitos funcionais.

**Componentes do Fluxo do Caso de Uso**:

  * **Fluxo Principal (FP)**: Também conhecido como "caminho feliz". É o passo a passo que documenta o que o caso de uso tem que fazer, de acordo com seu objetivo principal.
  * **Fluxo Alternativo (FA)**: Trata de tudo que não é o caminho normal ou esperado. Descreve o passo a passo para o tratamento de problemas ou situações fora do normal.
  * **Fluxo de Exceção (FE)**: São funções que não fazem parte do fluxo principal, mas estão disponíveis para o usuário executar, caso queira.

#### Exemplo de Caso de Uso (UC01 - Comprar produto)

| Item | Detalhe |
| :--- | :--- |
| **Nome** | UC01 - Comprar produto |
| **Descrição breve** | Possibilitar ao cliente realizar a compra de produtos. |
| **Pré-condições** | O cliente precisa ser um usuário válido e estar logado no sistema. |
| **Fluxo Principal (FP)** | 1. Cliente seleciona itens para comprar. (...) 3. Cliente clica no botão de Finalizar Compra. 4. Sistema verifica se cliente pode efetuar compra, chamando UC03. 5. Crédito liberado, sistema habilita campos para compra. 6. Cliente informa CEP de entrega. 8. Sistema apresenta o preço total, conforme RN01. 9. Cliente seleciona a forma de pagamento, e sistema desvia para o UC02. 10. Compra aprovada, sistema confirma compra enviando a MSG001. 12. Sistema finaliza caso de uso. |
| **Fluxos Alternativos (FA)** | **5.a: Crédito não liberado**: Sistema mostra MSG002 e Retorna para o passo 12 do fluxo principal. **6.a: CEP informado é inválido**: Sistema apresenta a MSG003 e Retorna para o passo 6 do fluxo principal. **10.a: Compra não aprovada**: Sistema apresenta a MSG004 e Retorna para o passo 9 do fluxo principal. |
| **Fluxo de Exceção (FE)** | **FE01**: sistema apresenta informações adicionais sobre o produto, em uma guia separada (*pop-up*). |
| **Regra de Negócio (RN01)** | Com o CEP utilizado, verificar a distância a partir da central de distribuição e calcular o custo, sendo R$ 0,65 por cada quilômetro rodado. Com o valor obtido, acrescentar mais R$ 7,00 se a opção escolhida for Entrega Normal ou acrescentar mais R$ 10,00 se a opção escolhida for Entrega Expressa. |
| **Mensagens (MSG)** | MSG001 - Compra Finalizada com Sucesso. MSG002 - Identificamos um Problema, favor entrar em contato com a Central de Atendimento (...). MSG003 - CEP informado não é válido. MSG004 - Compra não aprovada. |

### 5\. Estórias de Usuário (*User Stories*)

O foco das metodologias ágeis está nos indivíduos. A escrita da estória de usuário utiliza a linguagem do negócio, pois o *software* é feito para um usuário, e deve ser escrita com base na perspectiva do usuário final.

  * **Estória de Usuário**: Uma curta e simples descrição de uma funcionalidade ou parte de uma funcionalidade.
  * **Formato**: Como/Sendo \<quem\>, eu quero/gostaria/devo/posso \<o que\>, para que/de/para \<porque/resultado\>.
  * **Épico**: É uma grande estória, ou um conjunto de estórias. Quando uma funcionalidade é muito extensa, ela necessita ser quebrada em partes menores para que seja melhor compreendida.

**Exemplos de Estórias de Usuário**:

1.  **Como Professor**, preciso informar as notas bimestrais de um aluno **para** controle de aprovação deste aluno na disciplina.
2.  **Como Aluno**, preciso consultar minhas notas bimestrais **para** acompanhar meu desempenho acadêmico.
3.  **Como Diretor**, quero ter um relatório diário com as vendas de cada departamento **para** acompanhar o atingimento da meta mensal.

### 6\. Estudo de Caso de Uso

**Cenário**:

  * O cliente contratou para modelar o processo de vendas *on-line* de livros.
  * O cliente tem uma livraria virtual, que vende produtos diretamente em um *site* próprio.
  * **Diferenciais**:
      * Possui um estoque próprio, o que garante uma entrega mais rápida a seus clientes.
      * Aceita vários tipos de pagamento, como cartão de crédito, cartão de débito e boleto bancário.
      * Programa de fidelidade que permite desconto de 10% aos clientes que comprarem R$ 500,00 ou mais em um ano.