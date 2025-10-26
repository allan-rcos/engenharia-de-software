# SISTEMAS OPERACIONAIS: FUNDAMENTOS, CLASSIFICAÇÃO E GERENCIAMENTO

O Sistema Operacional (SO) é um software indispensável e fundamental nos sistemas computacionais atuais. Ele atua como o principal software que controla e gerencia as operações de um computador, sendo responsável por integrar o *hardware* do equipamento com os *softwares* de usuários.

## VISÕES E FUNÇÕES DO SISTEMA OPERACIONAL (SO)
O SO é uma camada de abstração entre o *hardware* e os aplicativos, garantindo que o acesso e o controle dos recursos de *hardware* ocorram de forma eficiente, segura e organizada.

* **Visão do Usuário Final:** O SO é visto como uma interface amigável que permite acessar, de forma intuitiva e fácil, aplicativos, arquivos e configurações do sistema para realizar tarefas cotidianas.
* **Visão do Engenheiro de Software:** O SO é a plataforma complexa que fornece os recursos básicos para a construção e execução de aplicativos, exigindo foco em escalabilidade, segurança, desempenho e gestão de recursos.

## FUNÇÕES ESSENCIAIS E TIPOS DE INTERFACE
As funções do SO são cruciais para o funcionamento de qualquer sistema computacional.

* **Gerenciamento de Recursos:** Gerencia e aloca recursos vitais como CPU, memória, armazenamento e periféricos entre os aplicativos em execução.
* **Gerenciamento de Processos:** Gerencia a execução de processos, alocando recursos de *hardware* de forma justa e prevenindo conflitos ou condições de corrida.
* **Gerenciamento de Memória:** Aloca espaço na memória RAM para os aplicativos em execução e garante o uso eficiente, gerenciando a memória virtual e física.
* **Segurança:** Fornece medidas de segurança essenciais para proteger o computador contra ameaças, controlando o acesso de programas e usuários aos recursos e dados.
* **Interface de Usuário (IU):** Fornece o meio pelo qual os usuários interagem com o computador e os aplicativos instalados.

### TIPOS DE INTERFACE
* **Interface Gráfica (GUI):** Interface mais amigável e intuitiva, com a qual o usuário interage por meio de elementos visuais (janelas, ícones, menus).
* **Interface por Linha de Comando (CLI):** Interface em que o usuário interage através da digitação de comandos de texto.

## CLASSIFICAÇÃO DOS SISTEMAS OPERACIONAIS
Os SOs são classificados de acordo com diversos critérios, como o tempo de resposta e sua estrutura interna.

### Classificação quanto ao Tempo de Resposta e Entrada de Dados
* **Sistemas Operacionais em Lote (*Batch*):** Processam dados em lotes pré-definidos e não fornecem interação direta com o usuário durante o processamento (ex: sistemas bancários de grande volume).
* **Sistemas Operacionais Interativos:** Exigem interação do usuário e oferecem uma resposta imediata a cada entrada ou comando (ex: SOs para computadores pessoais).
* **Sistemas Operacionais de Tempo Real (*Real-time*):** Respondem a eventos e estímulos externos com limites de tempo rígidos e previsíveis, essenciais para sistemas críticos (ex: automação industrial, sistemas de radar).

### Classificação quanto à Estrutura do Núcleo (*Kernel*)
* **Sistemas Operacionais Monolíticos:** Possuem um núcleo único e integrado, onde todos os componentes essenciais (gerenciadores de memória, processos, E/S) residem no mesmo espaço de memória do *kernel*.
* **Sistemas Operacionais Micronúcleos:** Possuem um núcleo pequeno e modular, que contém apenas as funções mínimas (gerenciamento de memória e comunicação interprocessos), enquanto outros serviços (drivers) são executados em espaços de usuário.

---

## CONCORRÊNCIA, PROCESSOS E THREADS

Concorrência é a capacidade de múltiplos processos compartilharem os recursos de um equipamento de forma organizada e eficiente. Um **processo** é a instância de um programa em execução.

### Principais Técnicas de Concorrência e Gerenciamento
Esses mecanismos são usados pelo SO para coordenar e otimizar a utilização do *hardware*.

* **Interrupção:** Sinal de comunicação assíncrona do *hardware* para a CPU (via SO) que notifica sobre um evento importante, permitindo que o *software* reaja rapidamente (ex: conclusão de E/S).
* **Exceção:** Interrupção síncrona gerada pela própria execução de um programa, indicando uma condição anormal ou erro (ex: divisão por zero, acesso a memória inválida).
* **Buffering:** Técnica que armazena dados temporariamente em uma área de memória (*buffer*) para suavizar a transferência de dados entre componentes com diferentes taxas de velocidade.
* **Spooling:** Técnica que utiliza uma área em disco como um grande *buffer*, aplicada para gerenciar e enfileirar tarefas de saída de dados, como a impressão.

### Estados de um Processo
O ciclo de vida de um processo é caracterizado pelas seguintes fases:

* **Novo:** O processo foi criado e está sendo inicializado, mas ainda não está pronto para ser executado.
* **Pronto:** O processo está carregado na memória e aguardando para ser alocado na CPU pelo escalonador.
* **Execução:** O processo está utilizando a CPU (suas instruções estão sendo executadas).
* **Espera:** O processo está temporariamente bloqueado, aguardando por algum evento ou recurso externo (ex: entrada de dados, acesso a disco).
* **Terminado:** O processo finalizou sua execução e está aguardando o SO liberar seus recursos.

## PRÁTICA: O Conceito de Threads

### Documento/Processo: Thread (*Fio de Execução*)
Uma *thread* é a unidade de execução independente mais leve dentro de um processo.

* **Item A: Processo *vs* Thread:** O **Processo** é a unidade básica, possui seu próprio espaço de endereçamento de memória e é independente. A **Thread** é uma unidade de execução dentro de um processo, compartilhando o mesmo espaço de memória e recursos, mas possuindo sua própria pilha de execução e registradores.
* **Item B: Benefícios:** Permite que o SO aloque múltiplos fluxos de execução (tarefas) para a CPU de forma mais granular e eficiente, o que melhora o desempenho geral em sistemas multiprocessados, otimizando o uso do tempo de processador.