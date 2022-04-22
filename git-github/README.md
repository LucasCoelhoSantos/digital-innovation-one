# Git e GitHub

Git é um sistema de controle de versão e o GitHub é uma das plataformas para gerenciar o projeto de forma distribuída, possibilitando hospedar um repositório e ter o controle de acesso dos usuários.

> O Bitbucket e o Gitlab são as duas principais alternativas de serviço Git além do Github.

## Importância

- Controle de versão
- Armazenamento em nuvem
- Trabalho em equipe
- Melhorar seu código
- Reconhecimento

## Comandos básicos

|Comandos          |Windows  |Linux
|:-----------------|:-------:|:---:
|Mudar de diretório|cd       |cd
|Listar diretórios |dir      |ls
|Criar diterórios  |mkdir    |mkdir
|Deletar diretórios|del/rmdir|rm/rf
|Move um diretório |mv       |mv

## Instalando Git

[Download Git](https://git-scm.com/downloads).

Realizar a instalação padrão com Git Bash Here e Git GUI Here.

> A partir da versão 2.30 a branch principal "master" passa a ser chamada de main.

## Entendendo o Git

A sigla SHA (Algoritmo de Hash Seguro) é um conjunto de funçõpes hash criptográficas projetadas pela NSA (Agência de Segurança Nacional dos Estados Unidos).
A encriptação gera um conjunto de caracteres identificador de 40 dígitos.

```bash
openssl sha1 arquivo.txt
```

## Objetos internos do Git

- Blobs: Bloco básico de composição, onde ficam os arquivos.
- Trees: Armazenam Blobs, responsável por montar a estrutura de onde está os arquivos.
- Commits: Aponta para uma tree, parente, autor, mensagem e timestamp.

Se mudar um arquivo Blob, consequentemente altera uma Tree e um Commit, tornando cada Commit único.

![Modelo de objetos](https://git-scm.com/book/en/v2/images/data-model-1.png)

![Exemplo Commit](https://git-scm.com/book/en/v2/images/commit-and-tree.png)

## Chave SSH e Token (GitHub)

Fornecem mais segurança para plataforma.

### Chave SSH
Forma de estabelecer uma conexão segura e encriptada entre duas máquinas.
- Chave pública (enviada ao GitHub)
- Chave privada (usada para desencriptar)

Gerar uma nova chave SSH e adicioná-la ao ssh-agent:[Documentação SSH GitHub](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

Passo a passo:
1. Gerar par de chave publica e privada: `ssh-keygen -t ed25519 -C seu_email_github@gmail.com`
2. Visualizar o conteúdo de uma chave: `cat id_ed25519.pub`
3. Copiar a chave pública e inserir no GitHub
4. Inicializar SSH-agent: `eval $(ssh-agent -s)`
5. Adicionar chave privada ao ssh-agent: `ssh-add id_ed25519`

#### Clonando um repositório do GitHub com SSH

- Copiar o SSH do repositório
- Clonar com o comando: `git clone ssh.do.repositorio.github`

### Token de acesso pessoal

Gerar um token
- Settings > Developer Settings > Personal Access Tokens
	- Definir um nome, data de expiração e o escopo (opção repo: padrão git).
	- Salvar o token de forma segura.

#### Clonando um repositório do GitHub com Token

- Copiar link HTTPS
- Clonar com o comando: `git clone https://link-do-repositorio`
- Inserir o token

## Iniciando o Git e criando um commit

|Função                                     |Comando
|:------------------------------------------|:------------
|Inicia um repositório Git                  |git init
|Insere uma configuração                    |git config
|Adiciona o conteúdo dos arquivos informados|git add
|Cria um commit                             |git commit
|Verifica o status dos arquivos             |git status
|Lista os repositórios remotos cadastrados  |git remote -v

> Em `git add *` e `git add .` o asterisco ou ponto adiciona todos os arquivos do diretório (incluindo os que foram excluídos).
> Em `git commit -m "mensagem"` -m é uma flag que permite passar uma mensagem.

## Passo a passo no ciclo de vida

![Ciclo de vida do status](https://blog.4linux.com.br/wp-content/uploads/2017/07/Git_ciclo.vida_.png)

![Push e Pull](http://learnstemlabs.com/articles/gitcheatsheet/flow.png)

## Trabalhando com GitHub

Após criar um repositório no GitHub, basta utilizar o seguinte comando para apontar o repositório local (origin) para o repositório remoto (master):

```bash
git remote add origin https://github.com/LucasCoelhoSantos/digital-innovation-one.git
```

E o seguinte comando para empurrar as alterações do repositório local (origin) para o repositório remoto (master):

```bash
git push origin master
```

## Conflitos no GitHub e como resolvê-los

![Merge](https://wac-cdn.atlassian.com/dam/jcr:c6db91c1-1343-4d45-8c93-bdba910b9506/02%20Branch-1%20kopiera.png?cdnVersion=309)

Os conflitos são alterações no repositório remoto em relação ao repositório local que precisam ser sincronizadas (merge). Eles acontecem na hora de empurrar ou puxar o(s) arquivo(s) para o repositório remoto.

Para resolver basta fazer um pull realizar as correções necessárias e realizar o push.