# SISTEMAS OPERACIONAIS II: GERÊNCIA DE PROCESSADOR E MEMÓRIA

O gerenciamento de processos é uma atividade fundamental dos Sistemas Operacionais (SO), responsável por gerenciar a alocação de recursos escassos como CPU e memória, controlar o estado dos processos e garantir a eficiência e estabilidade do sistema em ambientes multiprogramados.

## SEÇÃO PRINCIPAL 1 (Conceitos e Funções de Gerência)
O Sistema Operacional atua como gerente dos recursos de hardware do dispositivo, de modo a garantir o uso otimizado e equilibrado da CPU.

* **Gerência do Processador:** Consiste na escolha do processo que deverá ser executado primeiro, alocando o tempo de execução da CPU de forma eficiente.
* **Escalonador:** É o módulo do SO responsável por fazer a escolha do próximo processo a ser executado, utilizando um algoritmo de escalonamento que segue a política definida.
* **Objetivo Central da Gerência:** Maximizar a eficiência do sistema, garantindo que todos os processos recebam tempo de CPU suficiente e que o SO mantenha um equilíbrio adequado de cargas.

## SEÇÃO PRINCIPAL 2 (ESTADOS E CHAVEAMENTO DE PROCESSOS)
A execução de um programa é controlada por meio do seu ciclo de vida (estados) e pelo mecanismo que permite que a CPU alterne entre eles (chaveamento).

* **Estados do Processo:** O processo passa por cinco estados principais durante sua vida útil:
    * **Novo:** O processo está sendo criado.
    * **Pronto:** O processo está carregado e esperando para ser atribuído à CPU.
    * **Execução:** As instruções do processo estão sendo executadas pela CPU.
    * **Espera (ou Bloqueado):** O processo está aguardando a ocorrência de algum evento (ex: conclusão de uma operação de I/O).
    * **Finalizado:** A execução do processo foi concluída.
* **Chaveamento de Contexto (Context Switch):** É o mecanismo pelo qual a CPU alterna entre a execução de processos. Consiste em salvar o estado (contexto: registradores, contador de programa, estado) do processo atualmente em execução e carregar o estado do próximo processo a ser executado.

### SUBSEÇÃO (Objetivos do Escalonamento)
A política de escalonamento é fundamental para o desempenho do sistema, sendo guiada por objetivos específicos:

* **Justiça:** Dividir o tempo de CPU entre os processos de forma equitativa.
* **Equilíbrio:** Manter todas as partes do sistema (CPU, I/O) ocupadas e otimizadas.
* **Política:** Assegurar que as regras de execução estabelecidas pelo SO (ex: prioridades) sejam cumpridas.
* **Eficiência:** Maximizar o uso da CPU e garantir tempos de resposta satisfatórios para os usuários interativos.

## SEÇÃO PRINCIPAL 3 (ALGORITMOS DE ESCALONAMENTO)
Os algoritmos se dividem em classes e são escolhidos conforme o ambiente (lote, interativo, tempo real) para atingir os objetivos de desempenho.

### Prática/Regra 1 (Algoritmos Não Preemptivos)
* **Uso Correto vs. Errado:** Use **Ordem de Chegada (FIFO)** para processos que devem executar na sequência em que foram criados (simplicidade), e não use **Processo Mais Curto (SJF - Shortest Job First)** quando não se pode estimar o tempo de execução, ou quando processos longos não podem esperar indefinidamente.

### Prática/Regra 2 (Algoritmos Preemptivos)
* **Dica Importante:** Utilize o **Chaveamento Circular (Round-Robin - *quantum*)** para sistemas interativos. Ele dá uma fatia de tempo (*quantum*) para cada processo, garantindo tempos de resposta previsíveis e satisfatórios.
* **SRTF e Prioridade:** O **Shortest Remaining Time First (SRTF)** é a versão preemptiva do SJF, garantindo que o processo com menor tempo restante seja sempre executado. O **Escalonamento por Prioridade** executa primeiro o processo com maior prioridade, podendo ser preemptivo ou não.

---

## PRÁTICA (Gerência de Memória)

### Hierarquia e Abstração de Memória
A gerência de memória lida com a alocação de espaço, a proteção da memória dos processos e a ilusão de que a memória principal é virtualmente ilimitada.

* **Objetivos da Gerência de Memória:** Alocar espaço para os programas e dados, proteger a área de memória de cada processo, garantir o isolamento e fornecer a ilusão de memória virtual.
* **Memória Virtual:** Técnica que combina memória principal e secundária, dando ao usuário a ilusão de uma memória maior que a capacidade física real. O conceito se baseia em não vincular o endereçamento lógico (do programa) aos endereços físicos da memória principal. O mapeamento é feito pela **MMU** (*Memory Management Unit*).

### Estratégias de Alocação e Fragmentação
Em sistemas multiprogramáveis com memória particionada, as estratégias definem como um programa será alocado na área livre disponível.

* **First-Fit:** Seleciona a **primeira** partição livre encontrada que for grande o suficiente.
* **Best-Fit:** Seleciona a **menor** partição livre que acomode o programa, resultando na menor sobra de espaço.
* **Worst-Fit:** Seleciona a **maior** partição livre disponível, na teoria de deixar um fragmento grande o suficiente para futuros processos.

### Paginação e Segmentação
* **Paginação:** O espaço de endereçamento é dividido em blocos de tamanho **fixo** (páginas) e o endereço real é mapeado por uma **Tabela de Páginas**.
    * **Vantagem:** Elimina a **Fragmentação Externa**.
    * **Desvantagem:** Gera **Fragmentação Interna** (espaço desperdiçado dentro da última página alocada).
* **Segmentação:** O espaço de endereçamento é dividido em blocos de tamanho **variável** (segmentos), baseados em divisões lógicas do programa. O mapeamento é feito por uma **Tabela de Segmentos**.
    * **Vantagem:** Facilita a proteção e o compartilhamento lógico de dados.
    * **Desvantagem:** Propenso à **Fragmentação Externa** (total de memória livre é suficiente, mas não contígua).

### Swapping
* **Swapping:** Mecanismo de gerência de memória onde um processo inteiro (ou grande parte dele) é transferido entre a memória principal e o disco (memória secundária) quando há pouca memória principal, permitindo a execução de mais processos simultaneamente.