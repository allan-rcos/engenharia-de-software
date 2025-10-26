# FUNDAMENTOS DE INFRAESTRUTURA DA TI: PROTOCOLOS DE APLICAÇÃO, ROTEAMENTO E SEGURANÇA

Esta aula abrange os protocolos de aplicação, que são os "atores principais" da internet, atuando nas camadas superiores para permitir a comunicação de alto nível. O resumo também detalha as estruturas de roteamento, encaminhamento e os mecanismos essenciais de segurança de rede.

## SEÇÃO PRINCIPAL 1 (Protocolos e Camadas)
Os protocolos de aplicação no modelo TCP/IP incluem as funcionalidades das camadas de Sessão, Apresentação e Aplicação do modelo OSI no mesmo bloco.

* **Camada de Sessão:** Organiza a comunicação entre cliente e servidor, controlando o diálogo e gerenciando múltiplos fluxos. Seus controles de sincronização conseguem retomar os fluxos de dados do ponto de interrupção em caso de falha temporária.
* **Camada de Apresentação:** Lida com a representação e conversão do formato de dados (como .JPEG, ASCII, .MPEG-4) e trata das funcionalidades de criptografia.
* **Protocolo de Aplicação:** Executa funções como controle de sessão, criptografia e interface com os processos de usuário.

## SEÇÃO PRINCIPAL 2 (DNS, Acesso Remoto e Gerenciamento)
O foco desta seção está nos protocolos que possibilitam a resolução de nomes, o acesso seguro a terminais e o monitoramento da rede.

* **DNS (Domain Name System):** Sistema distribuído e hierárquico essencial para a internet, que traduz nomes de domínio (URLs) para endereços IP. Utiliza o protocolo **UDP na porta 53** para requisições e respostas.
* **SSH (Secure Shell):** Protocolo criptografado que oferece comunicação segura, utilizando **TCP na porta 22**. Emprega criptografia assimétrica para autenticação e criptografia simétrica para proteger a comunicação de dados.
* **Telnet:** Protocolo de acesso a terminal remoto (modo texto) que utiliza **TCP na porta 23**. Não é recomendado por enviar informações de login e senha em **texto simples**.
* **SNMP (Simple Network Management Protocol):** Protocolo para gerenciamento de rede que permite monitorar e controlar dispositivos IP. Utiliza **UDP na porta 161** para enviar e receber mensagens.

### SUBSEÇÃO (Registros de Recurso do DNS e Gerenciamento)
O DNS armazena suas informações em Registros de Recursos (RR). O SNMP armazena informações de gerenciamento no MIB.

* **A (Address):** Contém o endereço IP (inteiro de 32 bits) de um host.
* **MX (Message Exchange):** Define o nome do dispositivo apto a receber correio eletrônico.
* **CNAME (Canonical Name):** Nome canônico, ou nome alternativo, de um domínio.
* **PTR (Pointer):** Usado em pesquisas reversas, permitindo a busca pelo endereço IP e retornando o nome.
* **OID (Object Identifier):** Identificador único de cada objeto gerenciado dentro do **MIB** (Management Information Base).

## SEÇÃO PRINCIPAL 3 (Dicas/Prática - Protocolos de Correio e Gerenciamento)

### Prática/Regra 1 (Protocolos de Correio)
* **Uso Correto vs. Errado:** Use 'IMAP' (porta 143 ou 993) para o acesso ao e-mail, pois ele **mantém as mensagens no servidor** e sincroniza as alterações entre dispositivos, e não use 'POP3' (porta 110) se a intenção for manter o e-mail acessível em múltiplos dispositivos, pois o POP3 normalmente **baixa as mensagens para o dispositivo** e as exclui do servidor.

### Prática/Regra 2 (Gerenciamento de Rede)
* **Dica Importante:** O SNMP envia mensagens de ocorrência de eventos (*traps*) para o NMS (**Network Management System**) **sem a necessidade de requisição explícita** do NMS.

---

## PRÁTICA (Endereçamento e Roteamento na Rede Corporativa)

### Roteamento e Encaminhamento
* **Roteamento:** Processo de construir e manter a Tabela de Rotas, registrar a topologia da rede e ativar a melhor rota.
* **Encaminhamento:** Processo de analisar um pacote que chega, consultar a Tabela de Rotas e enviar o pacote pela interface associada.

### Estrutura de Endereçamento de Rede
A topologia prática apresentada divide a rede em três blocos de endereçamento distintos para comunicação entre a Matriz e o Datacenter.

* **Rede Privada (Matriz):** Bloco principal de endereçamento interno: `192.168.10.0/24`.
    * **Default gateway:** `192.168.10.1` (Endereço da Matriz).
    * **Impressora:** `192.168.10.2`.
    * **Servidores:** 2 servidores em `192.168.10.3-4`.
    * **Clientes:** 5 computadores endereçados entre `192.168.10.11-15`.
* **Rede Serial WAN (Ponto a Ponto):** Bloco para a conexão serial entre roteadores: `201.10.10.0/30`.
    * **Roteador Matriz:** `201.10.10.1/30`.
    * **Roteador Datacenter Ext.:** `201.10.10.2/30`.
* **Rede Pública (Datacenter):** Bloco para a sub-rede do Datacenter, onde fica o servidor de aplicações: `200.34.34.0/27`.
    * **Roteador Datacenter Int.:** `200.34.34.1/27`.
    * **Servidor HTTP:** `200.34.34.2/27` (Aplicações como `www.sistemas.com` utilizam este bloco).

### Dispositivos de Segurança
* **Firewall (Filtro):** Pode ser de Camada de Rede (L4) ou de Nova Geração (L7). As regras podem ser **restritivas** (nega tudo, exceto exceções permitidas) ou **permissivas** (permite tudo, exceto exceções negadas).
* **IDS (Intrusion Detection System):** Sua função é de **detecção**, realizando análise profunda de tráfego e avaliação de comportamento anormal para gerar alertas.
* **IPS (Intrusion Prevention System):** Sua função é de **prevenção**, sendo capaz de gerar alertas e realizar **bloqueios** de tráfego.
* **VPN (Virtual Private Network):** Cria uma conexão privada e segura sobre uma rede pública, utilizando criptografia.