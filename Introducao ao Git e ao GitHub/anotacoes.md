[TOC]

# Introdução ao GIT e ao GitHub

O foco do curso é adquirir conhecimentos sobre a ferramenta Git Bash, devemos primeiro conhecer alguns comandos básicos para familiarização com terminal seja no sistema operacional Windows (shell) ou Linux (bash).

|    SHELL    |                          Descrição                           |    BASH     |
| :---------: | :----------------------------------------------------------: | :---------: |
|     dir     | Lista os diretórios dentro da pasta em que se está situado no terminal |     ls      |
|    cd /     | Acessar uma pasta que será informada através da barra ("/")  |    cd /     |
|    cd ..    |                   Voltar um nível na pasta                   |    cd ..    |
|     cls     |                   Limpa a tela do terminal                   |    clear    |
| tecla "tab" |                      Completar comando                       | tecla "tab" |
|    mkdir    |                       Criar uma pasta                        |    mkdir    |
|    echo     |                 Printa um texto no terminal                  |    echo     |
|     del     |         Deleta os arquivos do diretório especificado         |     rm      |
|    rmdir    |               Deleta o diretório especificado                |   rm -rf    |

### Benefícios sobre o uso do Git

- Controle de Versão
- Armazenamento em nuvem
- Trabalho em equipe
- Melhorar seu código
- Reconhecimento

### Download e Instalação do GIT

[Link para download na página oficial](https://git-scm.com/downloads)

### Adicionar Chave SSH no GitHub

Para estabelecer uma comunicação segura com encriptação entre duas máquinas, no caso a nossa máquina local e o servidor do GitHub. Devemos acessar as opções em nosso perfil do GitHub, e selecionar [SSH and GPG keys](https://github.com/settings/keys), feito isso acessar o Git Bash.

Agora, para criar o par de chaves SSH, no terminal Git Bash devemos passar o comando informando o tipo de encriptação e o e-mail da conta GitHub:

`ssh-keygen -t ed25519 -C email@exemplo.com`

Feito isso, serão criadas duas chaves sendo uma privada e outra pública. Podemos usar o comando `cat id_ed25519.pub` para pegar o conteúdo da chave e adicionar em **New SSH Key** na opção [SSH and GPG keys](https://github.com/settings/keys).

#### Inicializar chave no SSH Agent

- O SSH Agent é uma entidade que fica encarregado de pegar as chaves e lidar com elas: `eval $(ssh-agent -s)`
- Para adicionar nossa chave ao SSH Agent, devemos informar o caminho da chave privada para descriptografar o que chegar: `ssh-add id_ed25519`

### Gerar um Token para autenticação no GitHub

Acessamos as configuração em nosso perfil e escolhemos a opção [Developer settings > Personal access tokens](https://github.com/settings/tokens). Definimos a data de expiração do Token e marcamos opção "Repo" e clicamos em "Generate Token", dessa forma será gerado nosso token. Observação para salvar o token, pois ele não será exibido de novo sendo necessário criar outro.

### Comandos do Git

- Para iniciar o repositório no Git e permitir que ele gerencie o repositório, usamos o comando: `git init`.
- Com o comando `ls -a` podemos conferir se foi iniciado corretamente ao verificar a existência da pasta "git" no repositório.
- Se for a primeira vez que estiver usando o Git, será necessário informar o autor com nome e e-mail para identificação no commit: `git config --global user.email "email@examplo"` e `git config --global user.name nome-exemplo`. 
- Para adicionar todos os arquivos do projeto ao commit: `git add *`.
- Para criar o commit e descrever o que foi realizado no projeto: `git commit - m "descrição"`.

### Trabalhando com o GitHub

- Podemos verificar as configurações do Git e comparar com o GitHub: `git config --list`.
- Para remover alguma configuração, como por exemplo o e-mail, usamos o comando: `git config --global --unset user.email`.
- Para apontar nosso repositório local com o servidor GitHub, devemos informar a origem para onde ele será enviado: `git remote add origin https://link-exemplo.git`.
- Com o comando `git status` podemos acompanhar o status do nosso projeto no Git.
- Para enviar nosso repositório local ao GitHub após identificar a origem: `git push origin master`.
- Para clonar um repositório do GitHub para nossa máquina local: `git clone "link https ou chave ssh"`.