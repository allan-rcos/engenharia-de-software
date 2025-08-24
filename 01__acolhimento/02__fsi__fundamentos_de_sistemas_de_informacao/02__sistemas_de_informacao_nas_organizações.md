# SI’s nas Organizações

##  Introdução

  * Objetivo da aula: Apresentar os principais conceitos e temas sobre a utilização de sistemas de informação em empresas.
  * Tópicos:
      * Organizações, cultura organizacional e departamentalização
      * Importância dos sistemas de informação para as organizações
      * Processo de desenvolvimento de um sistema de informação
      * Dados estruturados, semiestruturados e não estruturados
      * Tipos de software



##  Organizações, Sua Cultura e Departamentalização

  * Organização: Pessoa jurídica formada por um grupo de indivíduos para se engajar e operar um empreendimento comercial ou industrial, também conhecida como empresa.
  * Cultura organizacional: Missão, visão, crenças e valores da empresa.
  * Departamentalização: Processo em que os cargos/equipes são combinados em unidades funcionais chamadas departamentos, com base em sua área de especialização, para atingir os objetivos da organização.

###  Funções básicas de uma empresa:

  * Manufatura/produção
  * Vendas e marketing
  * Finanças e contabilidade
  * Recursos Humanos

####  Exemplos de processos de negócios funcionais:

| Área Funcional          | Processos de Negócios                                                                               |
| :-- | :--- |
| Manufatura e Produção   | Montagem do produto\<br\>Verificação de qualidade\<br\>Produção de listas de materiais                   |
| Vendas e Marketing      | Identificação de clientes\<br\>Conscientização de clientes a respeito do produto\<br\>Venda do produto |
| Finanças e Contabilidade | Pagamento de credores\<br\>Criação de relatórios financeiros\<br\>Gestão de contas bancárias            |
| Recursos Humanos        | Contratação de empregados\<br\>Avaliação de desempenho de empregados\<br\>Inclusão de empregados em plano de benefícios |



##  Importância dos SI’s para as Organizações:

  * Coletar, processar, armazenar e compartilhar dados.
  * Armazenar e analisar informações.
  * Simplificar os processos de negócios.
  * Facilitar a tomada de decisão.
  * Permitir acesso e controle total de dados.

###  Solucionando problemas com sistemas de informação:

Os sistemas de informação são desenvolvidos para enfrentar diversos tipos de problemas de negócios. Auxiliar a tomada de decisão a partir das ferramentas de análise e Business Intelligence (BI) para detalhar os dados:

  * Identificar e remediar ineficiências e problemas da cadeia de suprimentos.
  * Fornecer dados contínuos e oportunos sobre o desempenho da estratégia de marketing.



##  Processo de Desenvolvimento de um SI:

1.  Levantamento do sistema
2.  Análise de necessidades
3.  Projeto
4.  Implementação
5.  Teste
6.  Mudança
7.  Manutenção

####  1. Levantamento do sistema

  * Identificação do sistema: visa identificar os problemas enfrentados pela empresa e o sistema que ela possui.
  * Seleção: esta fase aplicará pontos de avaliação ao projeto de desenvolvimento para garantir que as soluções sejam criadas de acordo com as metas esperadas da empresa.
  * Planejamento do sistema: é a etapa de desenvolvimento de um plano formal para começar a trabalhar e implementar o conceito de desenvolvimento de sistema de informação que foi escolhido.

####  2. Análise de requisitos

  * A análise de requisitos do sistema é uma técnica para resolver problemas decompondo os componentes do sistema.
  * O objetivo é descobrir mais sobre como cada componente funciona e a interação entre um componente com outros componentes.

####  3. Projeto

  * O projeto ou projeto de desenvolvimento do sistema destina-se a fornecer um plano completo como diretriz para a equipe de TI (especialmente programadores) na criação de aplicativos.

####  4. Implementação

  * A etapa de desenvolvimento deste sistema de informação é trabalhar em um desenvolvimento previamente desenhado.

####  5. Teste

  * Um sistema precisa ser testado para garantir que o desenvolvimento realizado seja adequado ou não com os resultados esperados.
  * Os testes aplicados são diversos, como desempenho, eficiência de entrada, sintaxe (lógica do programa), saída, etc.

###  Metodologias de desenvolvimento de software:

  * Ciclo de vida de desenvolvimento de sistemas
  * Desenvolvimento de aplicação rápida
  * Metodologias ágeis
  * Metodologia lean

###  Tipos de armazenamento de dados:

  * Armazenamento de objetos
  * Armazenamento em bloco
  * Armazenamento de arquivos



##  Tipos de Dados:

O objetivo de muitos sistemas de informação é transformar dados em informações para gerar conhecimento que possa ser usado para a tomada de decisão.

###  Dados estruturados

  * São considerados a forma mais tradicional de armazenamento de dados.
  * Modelo de dados predefinido e, portanto, fáceis de analisar.
  * Obedecem a um formato tabular com relação entre as diferentes linhas e colunas.

**Exemplo:**

| Nome  | Endereço     | Telefone  |
| :----: | :----:      | :----:    |
| Maria | Rua A, n 12  | 333-343   |
| José  | Rua G, n 234 | 222-222   |
| João  | Rua D, n 3   | 444-333   |
| Pedro | Rua X, n 54  | 234-444   |

###  Dados semiestruturados:

  * São uma forma de dados estruturados que não estão em conformidade com a estrutura formal dos modelos de dados associados a bancos de dados relacionais ou outras formas de tabelas de dados.
  * Contém tags ou outros marcadores para separar elementos semânticos e impor hierarquias de registros e campos dentro dos dados.
  * Também conhecidos como estrutura autodescritiva.

**Exemplo:**

```json
{
  "Aluno": [
    {
      "nome": "João",
      "nota": [8, 9, 7]
    },
    {
      "nome": "Maria",
      "nota": [8, 10, 71]
    },
    {
      "nome": "Pedro",
      "nota": [10, 10, 9]
    }
  ]
}
```

###  Dados não estruturados

  * São informações que não possuem um modelo de dados predefinido ou não estão organizadas de maneira pré-definida.
  * As informações não estruturadas geralmente contêm muito texto, mas também podem conter dados como datas, números e fatos.
  * Resultam em irregularidades e ambiguidades que dificultam a compreensão do uso de programas tradicionais em comparação com os dados armazenados em bancos de dados estruturados.
  * Exemplos comuns de dados não estruturados incluem arquivos de áudio, vídeo ou bancos de dados No-SQL.

###  Data warehouse e data mart:

  * **Data warehouse**: São grandes armazéns de dados alimentados com dados transacionais oriundos dos diversos bancos de dados da empresa, inclusive dos sistemas ERP. O que o diferencia do conceito de banco de dados é a não volatilidade dos dados, ou seja, o fato de não alterar seu conteúdo com grande periodicidade.
  * **Data mart**: O data mart pode ser considerado um data warehouse departamental.


##  Tipos de Software

O software pode ser dividido em duas categorias: sistemas operacionais e software aplicativo.

###  Sistemas Operacionais

Os sistemas operacionais gerenciam o hardware e criam a interface entre o hardware e o usuário.

####  Funções:

  * Gerenciar os recursos de hardware do computador.
  * Fornecer os componentes da interface do usuário.
  * Fornecer plataforma para desenvolvedores de software escreverem aplicativos.

###  Software Aplicativo

  * **Pacote**: São compostos por variados tipos de softwares. Os de escritórios são compostos geralmente por editores de textos, planilha eletrônica, programa para criação e apresentação de slides, entre outros. O mais famoso pacote de escritório é o Office da Microsoft.
  * **Software-as-a-Service (SaaS)**: Também conhecido como software baseado em nuvem, está bem popular. SaaS é um método de entrega de software que permite que os dados sejam acessados de qualquer dispositivo com conexão à internet e um navegador da web. Exemplo: Google Drive.
  * **User friendly**: O termo "amigável ao usuário" se refere a softwares desenvolvidos com ênfase em serem intuitivos de utilizar. Uma opção não pode ser apenas fácil de usar, ela precisa ser fácil de usar para usuários não técnicos.
  * **Open source**: Significa que o software possui o código-fonte aberto, que pode ser utilizado para diferentes finalidades, porque seu design é acessível publicamente. As licenças de código aberto afetam a maneira como as pessoas podem usar, estudar, modificar e distribuir o software. Exemplo: Android.
  * **Freeware**: São programas gratuitos. Em certos casos, o desenvolvedor não reclama direitos autorais e o programa torna-se software de domínio público, o que significa que qualquer pessoa pode usá-lo sem nenhum custo ou restrição sobre baixar o programa. Exemplo: Internet Explorer.
  * **Shareware**: São softwares distribuídos gratuitamente para serem testados pelo usuário. Exemplos: jogos.
  * **Licença proprietária**: Permite a autorização para utilização do software. Possui a restrição de determinadas ações. Os direitos são do programador/empresa que criou o software. Exemplo: Windows.
  * **Groupware**: Conhecido como software colaborativo, sua especificação está relacionada a um tipo de software que possibilita que um grupo compartilhe ou rastreie informações. Exemplo: Trello.