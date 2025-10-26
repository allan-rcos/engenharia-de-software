# BARRAMENTO, MEMÓRIA, E/S E SUPORTE AO SO

O computador é uma máquina composta pela Unidade Central de Processamento (CPU) e eletrônicas de apoio (memórias e interfaces de E/S). Esta aula detalha a interconexão e a gestão desses componentes, mostrando como o Sistema Operacional (SO) atua no interfaceamento e na gestão eficiente dos recursos.

## INTERCONEXÃO: CONCEITOS E TIPOS
Estruturas de interconexão e slots.

* **Barramento (Estrutura de Interconexão):** É composto por linhas, ou trilhas, de interconexão entre os módulos computacionais. O número de trilhas depende dos bits que transitam simultaneamente.
    * **Barramento de Endereço:** Sequencia o endereço binário da localização na memória ou dispositivo.
    * **Barramento de Dados:** Transporta o dado propriamente dito (binário) entre os módulos.
    * **Barramento de Controle:** Transporta os sinais que informam ao módulo a operação a ser realizada (ex: leitura ou escrita) e controlam a seleção do módulo.
* **Interconexão Ponto a Ponto (PTP - *Point to Point*):** Barramentos exclusivos utilizados para módulos de comunicação de alta velocidade, como o QPI (utilizado pela Intel).
* **Slot de Expansão (PCI Express/PCIe):** Padrão de acesso aos barramentos internos que permite expandir ou adicionar características à máquina.

## DISPOSITIVOS DE ENTRADA E SAÍDA (E/S)
Elementos, Variações e Etapas de E/S.

* **Dispositivo de E/S (I/O):** É o componente essencial responsável pelo interfaceamento da máquina com o usuário ou o mundo externo. É composto por um **Módulo de I/O** e, eventualmente, um **Periférico**.
* **Periférico:** Não deve se conectar diretamente ao barramento do processador, pois a diversidade de lógicas e velocidades reduziria o desempenho da CPU.
* **Módulo de E/S:** É o circuito eletrônico de interfaceamento que traduz e controla os dados, tornando o processo de E/S homogêneo para a CPU.
* **Transdutor e Buffer (no Periférico):**
    * **Transdutor:** Converte os dados do ambiente externo para o padrão binário (na leitura).
    * **Buffer:** Compatibiliza a velocidade de operação do periférico com o *clock* do processador.

### HIERARQUIA E FUNÇÕES DA MEMÓRIA
A memória é um circuito eletrônico capaz de armazenar ao menos um dígito binário (*bit*), podendo ser **volátil** ou **perene**.

* **Função de Memória (Segundo Velloso):** Armazenamento das instruções, dos dados iniciais/intermediários e dos resultados finais referentes a um programa em processamento.
* **Métricas de Memória Externa:**
    * **Latência:** Mede o tempo total desde o endereçamento da memória pela CPU até a conclusão da leitura do dado (ex: NVMe possui latência muito baixa).
    * **Taxa de Transferência:** É a velocidade com que os dados podem ser acessados, refletindo o intervalo entre dois acessos sucessivos.

## TÉCNICAS E PRÁTICAS DE ACESSO
Dicas e Práticas na gestão de componentes.

### Prática/Regra 1: Técnicas de Acesso ao Módulo E/S
* **Uso Correto vs. Errado (E/S Programada):** Use 'Errado' para indicar a **E/S Programada**. O processador **fica esperando** pela prontidão do dispositivo, reduzindo o desempenho para periféricos lentos.
* **Uso Correto vs. Errado (E/S Controlada por Interrupção):** Use 'Correto' para indicar a **E/S Controlada por Interrupção**. A CPU segue a execução e só é notificada por um sinal de interrupção quando o módulo estiver pronto, aumentando a eficiência do processador.
* **Uso Correto vs. Errado (DMA):** Use 'Correto' para indicar o **Acesso Direto à Memória (DMA)**. O DMAC assume o controle da memória, desocupando a CPU durante todo o processo de acesso e gravação.

### Prática/Regra 2: Hierarquia de Memória
* **Dica Importante (Compromisso):** A escolha do tipo de memória é um compromisso entre três variáveis que define sua posição na hierarquia: **Custo por bit**, **Capacidade de armazenamento** e **Taxa de transferência de dados**.
* **Exemplo de uso (Hierarquia):** Memórias de alto desempenho (Registradores e Cache) devem ser reservadas para as tarefas mais nobres e de acesso recorrente, enquanto dados de uso eventual ficam em memórias de baixo desempenho e maior capacidade (Externa/Secundária).

---

## TÓPICOS DE APLICAÇÃO PRÁTICA

### Suporte do Sistema Operacional (SO)
O SO é um programa especial que é carregado após as instruções iniciais de *setup* (*POST*) do hardware.

* **Objetivos:** Os dois principais objetivos do SO são **Conveniência** (tornar a máquina amigável) e **Eficiência** (otimizar algoritmos e maximizar resultados).
* **SO como Gerenciador de Recursos (Otimização de Memória):**
    * **Carga de Segmentos:** Restringe a carga na memória principal (RAM) apenas à parte imprescindível do SO para a operação em dado momento.
    * **Memória Virtual:** Quando a memória principal é insuficiente, o SO reserva uma área da memória externa (ex: disco SSD) para ser utilizada como **extensão da memória principal**, o que resulta em redução do desempenho geral da máquina.

### Cálculo Corrigido do Tempo Médio de Acesso (TMA)
O cálculo do TMA deve considerar a probabilidade de falha (Miss Rate) em cada nível da hierarquia de memória.

* **Fórmula (Corrigida):** $TMA = T_{Acesso\_L1} \times R_{Acesso\_L1} + T_{Acesso\_L2} \times R_{Acesso\_L2} + T_{Acesso\_MP} \times R_{Acesso\_MP}$.

* **Cenário 2 (TMA Corrigido/Melhoria):** Com Razão de Falha L1 = 10% (0,1) e L2 = 5% (0,05). A Razão de Acesso à Memória Principal é $0,1 \times 0,05 = 0,005$.

$$TMA = 5ns(1,0) + 15ns(0,1) + 100ns(0,005) = 7ns$$

* **Conclusão:** O Tempo de Acesso Médio Corrigido é de **7ns**, resultando em um ganho de desempenho de **30%** em relação ao cenário original.

### Técnica RAID (Redundant Array of Independent Disks)
RAID é uma técnica para melhorar a segurança e o desempenho do armazenamento de dados, sendo mandatório para servidores.

* **RAID 0 (Striping):**
    * **Item A:** Aumenta a Taxa de Transferência.
    * **Item B:** Deixa o sistema susceptível a falhas (não há redundância).
* **RAID 1 (Mirroring):**
    * **Item A:** Aumenta a Robustez (espelhamento completo).
    * **Item B:** Custa o dobro do que sem RAID (50% de uso de capacidade).
* **RAID 5 (Parity):**
    * **Item A:** Obtém redundância de dados usando apenas uma unidade de paridade distribuída.
    * **Item B:** Implementação complexa e mais lenta do que sem RAID.
* **RAID 10 (Striping + Mirroring):**
    * **Item A:** Combina o que há de melhor da RAID 0 e RAID 1.
    * **Item B:** Custa o dobro do que sem RAID e aumenta a complexidade no sistema.

#### Exemplo de Custo em Diferentes Configurações RAID (Armazenar 10 TB)

| Configuração | Modelo A – HDD 1 TB (Custo R$ 200,00) | Modelo B – HDD 5 TB (Custo R$ 800,00) |
| :--- | :--- | :--- |
| **Sem RAID (10 TB)** | 10 und. (R$ 2.000,00) | 2 und. (R$ 1.600,00) |
| **RAID 0 (Striping)** | 10 und. (R$ 2.000,00) | 2 und. (R$ 1.600,00) |
| **RAID 1 (Mirroring)** | 20 und. (R$ 4.000,00) | 4 und. (R$ 3.200,00) |
| **RAID 5 (Paridade)** | 11 und. (R$ 2.200,00) | 3 und. (R$ 2.400,00) |
| **RAID 10 (Striping + Mirroring)**| 20 und. (R$ 4.000,00) | 4 und. (R$ 3.200,00) |