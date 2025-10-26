## TEMA 1: CONCEITOS BÁSICOS DE SISTEMAS COMPUTACIONAIS

Um computador é uma máquina criada para automatizar o tratamento da informação, envolvendo *hardware*, algoritmos e códigos.

### Principais Funções do Computador

As funções centrais de qualquer máquina computacional são:

1.  **Processamento de Dados:** Tratar ou transformar dados (e.g., operações aritméticas).
2.  **Movimentação de Dados:** Transitar dados entre a memória interna, interfaces de E/S ou entre diferentes níveis de memória.
3.  **Armazenamento de Dados:** Armazenamento temporário (Memória Principal) ou definitivo (Memória Secundária).
4.  **Controle de Dados:** Garantir que a movimentação e o armazenamento ocorram de forma precisa para disponibilizar os dados ao processamento.

### Estrutura do Computador

A estrutura básica (visão de alto nível) é composta por:

* **CPU (Unidade Central de Processamento):** Contém a Unidade de Controle (UC) e a Unidade Lógica Aritmética (ULA).
* **Memória Principal:** Armazenamento temporário, de acesso rápido.
* **Entrada/Saída (E/S):** Interfaces de comunicação com o exterior.
* **Barramento do Sistema:** Conexão física entre os blocos funcionais.

**Composição da CPU:**
* **ULA:** Realiza operações aritméticas e lógicas.
* **Unidade de Controle (UC):** Gerencia a movimentação de dados e a sequência de operações.

#### Arquiteturas Modernas (Multi-Core)
Arquiteturas recentes integram múltiplos núcleos (*cores*), onde cada *core* é um processador completo. Esses *cores* compartilham diferentes níveis de memória *cache* (L2, L3) para otimizar o desempenho.

## TEMA 2: EVOLUÇÃO DO COMPUTADOR

A evolução dos computadores é dividida em gerações baseadas na tecnologia de *hardware*:

| Geração | Tecnologia | Período (Exemplo) | Contribuições Chave |
| :--- | :--- | :--- | :--- |
| **Primeira** | Válvulas | Pós-Segunda Guerra (ENIAC) | Primeiro a não usar componentes mecânicos móveis. Problemas com calor e consumo de energia. |
| **Segunda** | Transistores | Uso Industrial | Consumo de energia e dimensões muito reduzidos. Possibilitou a **Multiprogramação** e o desenvolvimento do **Sistema Operacional**. |
| **Terceira** | Circuitos Integrados (CI) | 1964 (IBM System/360) | Concentração de transistores em um único substrato. Introdução do conceito de **FAMÍLIA de computadores**. |
| **Posteriores** | Microprocessadores | 1971 (Intel 4004) | Concentração das funções principais (ULA e controlador) em um único CI. Viabilizou máquinas de baixo custo e o surgimento da Internet. |

**Evolução da Arquitetura x86:** A arquitetura evoluiu principalmente pela ampliação dos barramentos (de 8-bits para 64-bits) e pelo aumento significativo da memória *cache* para acompanhar a velocidade dos processadores.

## TEMA 3: SISTEMAS EMBARCADOS

**Sistemas Embarcados** são processadores e eletrônicos fabricados para fazerem parte (embutidos) de um produto maior ou para interagir com o ambiente externo, muitas vezes sem mediação humana (e.g., IoT).

* **Foco em Eficiência:** As restrições de projeto priorizam a **eficiência** em **consumo de energia, memória, peso, dimensões e custo**.
* **Arquitetura ARM:** É a arquitetura dominante para microcontroladores em sistemas embarcados devido à sua eficiência energética e versatilidade, abrangendo desde baixa (Cortex M0) a alta complexidade (Cortex A78 em *smartphones*).

## TEMA 4: FUNCIONAMENTO BÁSICO DO CICLO DE INSTRUÇÃO

A função básica de uma máquina é executar programas por meio de instruções.

* **Instrução:** Código binário que compele a entrada em operação de componentes lógicos específicos do *hardware*.
* **Ciclo de Instrução:** O processo de execução de uma instrução, dividido em:
    1.  **Busca (*Fetch*):** O processador acessa a instrução na memória.
    2.  **Execução (*Execute*):** A instrução é realizada pela ULA e UC.
* **Interrupções:** Mecanismos para lidar com eventos assíncronos e prioritários (e.g., E/S), permitindo que o processador se engaje em outras tarefas sem interrupção manual constante.

## TEMA 5: QUESTÕES DE DESEMPENHO

O maior desafio atual é otimizar o desempenho do *hardware* existente, superando limitações físicas como calor e consumo de energia. O desempenho depende do balanço de todos os componentes, não apenas da CPU.

### Medidas de Desempenho

* **Velocidade de Clock:** A frequência que sincroniza os acessos às instruções.
* **Taxa FLOPS (Floating-point Operations Per Second):** Mede a capacidade do processador de realizar operações de ponto flutuante por segundo, indicando o poder de cálculo.
    $$\text{FLOPS} = \frac{\text{nº de operações em ponto flutuante}}{\text{Tempo de execução do programa}}$$

### Lei de Amdahl
A lei de Amdahl descreve o ganho de desempenho (*Speedup*) obtido pelo aumento de núcleos de processamento (paralelismo).

* O ganho é limitado pelo **índice de paralelismo ($f$)** do *software*.
* **Implicação:** O *hardware* multi-core só é eficiente se o *software* for desenhado para aproveitar o processamento paralelo. Aplicações com baixo paralelismo (e.g., editores de texto) não se beneficiam tanto do aumento de núcleos.

$$\text{Speedup} = \frac{1}{1 - f + \frac{f}{N}}$$
*Onde $f$ é a fração paralelizada e $N$ é o número de processadores.*