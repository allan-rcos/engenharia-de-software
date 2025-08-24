# Controle de Versionamento (GIT)

## O que é Git e versionamento

### Git:

Ferramenta de **controle de versionamento** que rastreia alterações em arquivos e diretórios ao longo do tempo.

### Versionamento:

Prática de gerenciar e controlar diferentes versões de documentos e projetos, especialmente software.

### Motivação:

Resolver problemas de múltiplas versões de arquivos, facilitar a colaboração, permitir a restauração de versões antigas e manter um histórico de alterações.

### Benefícios:

* **Rastreabilidade completa** das alterações.
* **Colaboração eficiente** entre múltiplos desenvolvedores.
* **Backup e recuperação** de versões anteriores.
* Compatibilidade com ferramentas de **integração contínua**.
* Comunidade ativa e suporte contínuo.


## Repositórios

### Repositório:

Local onde os arquivos do projeto são armazenados e controlados pelo Git.

### Função:

Manter o histórico completo de todas as alterações, permitindo reverter, comparar e analisar a evolução do código.

### Estrutura:

Cada repositório é único e contém uma pasta oculta `.git` que armazena os metadados e o histórico do projeto.


## Terminologia

* **Branch (Ramificação):** Linha de desenvolvimento separada que permite trabalhar em diferentes funcionalidades ou correções de bugs simultaneamente sem afetar o código principal (`master`).
* **Master:** Branch padrão criado ao inicializar um repositório.
* **Merge (Mesclar):** Ação de combinar as alterações de um branch de volta ao branch principal.
* **HEAD:** Referência ao último commit no branch atual.
* **Index (Área de Staging):** Área temporária onde as alterações são preparadas antes de serem confirmadas (`commit`).
* **Commit:** Registro de um conjunto de alterações no repositório, acompanhado de uma mensagem descritiva.
* **Origin:** Nome padrão dado ao repositório remoto.


## Comandos

* **`git config`:** Configura opções do Git, como nome de usuário, e-mail e editor.
    * `git config --global user.name "Seu Nome"`
    * `git config --global user.email "seu.email@exemplo.com"`
    * `git config --list` (Lista todas as configurações)
* **`git init`:** Inicializa um novo repositório Git em um diretório existente.
    * `git init`
* **`git add`:** Adiciona alterações do diretório de trabalho para a área de preparação (index).
    * `git add *` (Adiciona todos os arquivos)
    * `git add file.txt` (Adiciona um arquivo específico)
    * `git add folder/` (Adiciona uma pasta específica)
* **`git commit`:** Registra as alterações preparadas no repositório local.
    * `git commit` (Com mensagem padrão)
    * `git commit -m "Mensagem personalizada"`
* **`git push`:** Envia as alterações do repositório local para um repositório remoto.
    * `git push origin all` (Envia todos os branches)
    * `git push origin nome-do-branch` (Envia um branch específico)
* **`git log`:** Exibe o histórico de commits.
    * `git log` (Histórico completo)
    * `git log <file>` (Histórico de um arquivo)
    * `git log --since=<YYYY-MM-DD> --until=<YYYY-MM-DD>` (Histórico em um período)
* **`git status`:** Exibe o estado atual do repositório.
    * `git status` (Estado geral)
    * `git status <branch>` (Estado de um branch)
* **`git reset`:** Desfaz ações no repositório.
    * `git reset --soft HEAD^` (Desfaz o último commit, mantendo as alterações)
    * `git reset <nome-do-arquivo>` (Remove arquivo do índice)
    * `git reset --hard HEAD^` (Desfaz o último commit e remove as alterações)
* **`git diff`:** Compara diferenças entre versões de arquivos.
    * `git diff <hash-do-commit> <nome-do-arquivo>` (Compara versões de um arquivo)
    * `git diff <hash-do-commit1> <hash-do-commit2>` (Compara commits)
    * `git diff origin/master` (Compara com a versão remota)
* **`git branch`:** Gerencia branches.
    * `git branch` (Lista branches)
    * `git branch <nome-da-branch>` (Cria um novo branch)
    * `git branch -d <nome-da-branch>` (Exclui um branch)
* **`git checkout`:** Alterna entre branches ou restaura versões de arquivos.
    * `git checkout <nome-da-branch>` (Muda para um branch)
    * `git checkout -b <nome-da-branch>` (Cria e muda para um branch)
    * `git checkout <hash-do-commit> <nome-do-arquivo>` (Recupera versão antiga de um arquivo)
    * `git checkout -- <nome-do-arquivo>` (Desfaz alterações em um arquivo)


## Fluxo de trabalho do Git

* **Add (Adicionar):** Preparar as alterações para o próximo commit.
* **Commit (Confirmar):** Registrar as alterações no repositório local.
* **Push (Enviar):** Enviar as alterações para um repositório remoto.


## Branches (Ramificações)

* Permitem trabalhar em várias funcionalidades ou correções de bugs simultaneamente.
* O branch `master` é o branch principal.
* `Merge` é o processo de combinar as alterações de um branch de volta ao `master`.
* Facilitam a experimentação e o desenvolvimento paralelo sem afetar a estabilidade do código principal.