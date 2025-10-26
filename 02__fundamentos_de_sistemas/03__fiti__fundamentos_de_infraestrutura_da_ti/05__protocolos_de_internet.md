# Protocolos de Internet: IP, TCP, UDP e Arquitetura de Redes

A base da internet, o protocolo IP (Internet Protocol), surgiu da necessidade da DARPA durante a Guerra Fria de criar uma rede de comunicação resiliente e descentralizada, capaz de suportar ataques. Essa iniciativa resultou na ARPANET em 1969, que posteriormente adotou o modelo **TCP/IP** em 1º de janeiro de 1983, tornando-se o padrão único aceito. A internet evoluiu de um ambiente acadêmico para um serviço de utilidade pública com a criação do World Wide Web (WWW).

## SEÇÃO PRINCIPAL 1 (Conceitos, Tipos, etc.)

O protocolo IP (Internet Protocol) opera na camada de rede em um modo descentralizado, sendo o responsável por encaminhar os pacotes de dados (datagramas) da origem ao destino, nó a nó.

* **IPv4 (Internet Protocol versão 4):** Utiliza 32 bits, resultando em aproximadamente $4,3$ bilhões de endereços. A notação é decimal pontuada.
* **IPv6 (Internet Protocol versão 6):** Emprega 128 bits, oferecendo um espaço de endereçamento vastíssimo. Apresenta cabeçalho simplificado e suporta, de forma nativa, mecanismos como **IPSec** (segurança) e **QoS** (qualidade de serviço).

## SEÇÃO PRINCIPAL 2 (Elementos, Variações, Etapas)

Os protocolos de transporte TCP e UDP organizam a troca de dados entre processos que rodam nos dispositivos, sendo endereçados por número de porta.

* **TCP (Transmission Control Protocol):** É **orientado à conexão** e confiável. Exige uma fase de **estabelecimento de chamada** (troca de variáveis de controle para correção de erro e sequenciamento).
* **UDP (User Datagram Protocol):** É **não orientado à conexão** e não confiável. Não possui controles de estado, sequência de segmentos ou congestionamento.

### FRAGMENTAÇÃO E CONTROLE
O Protocolo IP suporta uma carga próxima a 64 kB, mas a fragmentação é necessária para se adequar ao limite do enlace (e.g., Ethernet com 1500 bytes de MTU).

* **Tamanho Máximo IPv4:** 64 kB (65.535 Bytes).
* **MTU (Maximum Transmission Unit):** O tamanho máximo de bloco de dados que um determinado enlace pode transportar.
* **Deslocamento do Fragmento:** Utilizado para marcar a posição do bloco, representado em quantidades de 8 bytes.

## SEÇÃO PRINCIPAL 3 (Dicas/Prática)

### Endereçamento IPv4 e NAT
* **Uso Correto vs. Errado:** A solução para a falta de endereços IPv4 foi o uso de **endereços privados** em redes locais (não roteáveis na internet), sendo traduzidos para um endereço público pelo **NAT (Network Address Translator)** no *gateway* da rede.
    * **Faixas Privadas (Exemplos):** Classe A: `10.x.x.x`, Classe C: `192.168.x.x`.

### Arquitetura de Redes Locais (LAN)
* **Dica Importante:** Redes locais (LAN) usam uma arquitetura hierárquica.
    * **Camada de Acesso:** Onde os usuários e dispositivos são conectados.
    * **Camada de Distribuição:** Agrega o tráfego dos equipamentos de acesso.
    * **Camada de Núcleo (Core):** Nível mais alto que interconecta o tráfego com outras partes da rede local e com redes externas.

---

## PRÁTICA (Tópico de Aplicação, se houver)

### Arquitetura de Redes e Modelo OSI

* **Rede Local Típica (LAN):** Uma rede local comum é composta por dispositivos finais (PCs, Laptops) conectados a **Switches**, que por sua vez se conectam a um **Router**.
* **Dispositivos e Camadas do Modelo OSI:**
    * **Switch:** Dispositivo que opera na camada de **Enlace de Dados** (Camada 2).
    * **Router (Roteador):** Dispositivo que opera na camada de **Rede** (Camada 3).
    * **Camadas Superiores:** Aplicação, Apresentação e Sessão.
    * **Camadas Inferiores:** Transporte, Rede, Enlace de Dados e Física.

### Cenário Prático de Endereçamento IP (Bloco 192.168.10.0/24)

O cenário prático de distribuição de endereços IP utiliza a rede **192.168.10.0** com máscara **/24**, que corresponde a **255.255.255.0**. Esta sub-rede permite um total de 256 endereços.

* **Endereço da Rede:** `192.168.10.0`. Este é o primeiro endereço do bloco.
* **Default Gateway (Router3):** `192.168.10.1`.
* **Servidor 1:** `192.168.10.2`.
* **Servidor 2:** `192.168.10.3`.
* **Último Endereço Disponível:** `192.168.10.254`.
* **Endereço de Broadcast:** `192.168.10.255`. Este é o último endereço do bloco, usado para difusão na rede.