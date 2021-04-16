# GIT GITHUB
## Guia prático para iniciantes, baseados nos vídeos:

- Aula [Como usar Git e Github na prática: Guia para iniciantes](https://www.youtube.com/watch?v=2alg7MQ6_sI) do canal [Rocketseat](https://www.youtube.com/channel/UCSfwM5u0Kce6Cce8_S72olg) com Mayk Brito 
- playlist [Git e Github para Iniciantes](https://www.youtube.com/playlist?list=PLlAbYrWSYTiPA2iEiQ2PF_A9j__C4hi0A) do canal no youtube do [Willian Justen Cursos](https://www.youtube.com/channel/UCa12brLWzCqnxN0KOyjfmJQ) - 
- playlist [Git](https://www.youtube.com/playlist?list=PLQCmSnNFVYnRdgxOC_ufH58NxlmM6VYd1) do canal [Rodrigo Branas](https://www.youtube.com/channel/UCkqOofjb7nl6V8vXrIbGtiQ)

--------------------
## Pincipais comandos

```bash
# todos os comandos em seguida vem explicação
git init
git add .
git commit -m "mensagem"
git status
git log
git show
git branch
git checkout
git merge
git rebase
git remote
git push
git clone
git pull
git diff
git reset
git config
git cherry-pick
```

* ### `git init` : 
    - inicia a linha do tempo, repositório

* ### `git add` 
    - adiciona ou atualiza mudanças para irem para a linha do tempo
    - git add nome_arquivo (altera ou adiciona um arquivo)
    - git add . (altera ou adiciona todos os arquivos)

* ### `git commit` 
    - adiciona um ponto na linha do tempo
    - git commit -m "mensagem do commit"
    - git commit -am "mensagem do commit" -> faz o git add e o commit
    - git commit --amend -m "mensagem reescrita" -> altera a mensagem do commit anterior

* ### `git log`
    - visualiza os pontos na linha do tempo e as mudanças feitas no projeto
    - mostra histórico dos commits, quem foi o autor e a data do commit 
    - git log --oneline -> mostra em uma linha com menos detalhes
    - git log --graph -> mostra como um gráfico

* ### `git status` 
    - informa o estado das alterações do nosso projeto

* ### `git show` 
    - apresenta determinado commit/ponto na história com todos os detalhes do que foi alterado
    - git show (numero_commit) -> mostra o commit informado 
    - git show -> mostra o último commit

* ### `git branch` 
    - gerenciar novas linhas do tempo
    - git branch nome_branch -> cria nova branch(ramificação)
    - git branch -> mostra todas as branchs(ramificações) e qual é a branch que está no momento
    - git branch -D nome_branch -> exclui a branch infromada 

* ### `git checkout`
    - manipula as linhas do tempo
    - git checkout nome_branch -> muda para uma branch
    - git checkout -b nome_branch -> cria e muda para uma branch, comando curto
    - git checkout numero_commit -- arquivo -> volta um arquivo para um determindado momento da linha do tempo ou recupera algo deletado
    - git checkout nome_arquivo -> retorna o arquivo antes de uma edição. Antes de fazer um commit, exemplo alterou o readme, não fez add nem commit, e quer voltar para como ele era antes da alteração

* ### `git merge`
    - unir as linhas do tempo/branch
    - git merge nome_branch 

* ### `git rebase`
    - unir as linhas do tempo/branch
    - git rebase nome_branch 

* ### `git merge x git rebase`
    - merge gera um novo commit, o que pode complicar o histórico, mas nunca o reescreve
        - merge basicamente cria um novo commit na branch onde o merge é realizado. Este commit puxa consigo a última referência da branch a partir da qual o merge é realizado. Este commit “especial” é chamado de merge commit
    - rebase deixa o histórico linear e mais simples, mas alguns commits são reescritos
        - rebase literalmente unifica os branches envolvidos, puxando os commits para frente da branch de destino. É como se ele estivesse “refazendo” a base do branch onde o comando é executado.
        - regra -> não fazer rebase em branch pública

* ### `git remote`
    - git remote add origin link_repositorio -> adiciona um repositorio do github na nossa aplicação
    - explicação github -> push an existing repository from the command line
    - git remote -v -> mostra os repositórios remotos

* ### `git push`
    - envia as alterações para o repositório remoto (github)
    - git push -u origin master -> na primeira vez é preciso criar a branch master no repositório online (github)
    - empurra o repositório local para o repositório online

* ### `git clone`
    - clonar um projeto, repositório
    - git clone link_repositorio

* ### `git pull`
    - puxa alterações do repositorio remoto atualizando o repositorio local

* ### `git diff`
    - mostra as alterações entre versões quando o arquivo está untracked (antes de fazer o git add)
    - git diff --name-only -> Mostra os arquivos que foram alterados

* ### `git reset`
    - reseta o repositório para o estado do commit informado 
    - git reset HEAD nome_arquivo -> após um arquivo ser adicionado, porém não commitado, esse comando faz com que o arquivo volte a ser untracked, ou seja, ele remove da staging area
    - git reset --tipo num_commit
    - existem 3 tipos soft, mixed(default) e hard 
    - git reset --soft num_commit -> somente altera a referência da branch principal, exemplo, em um commit foi criado um arquivo se fizermos reset soft para outro commit esse arquivo ainda vai estar na staging area, fica unmodified (existe no git porém não foi alterado, se alterar fica modified)
    - git reset --mixed num_commit (padrao não precisa informar --mixed) -> além de alterar a referência o mixed, diferentimente do soft, remove da staging area, ou seja, os arquivos ficam untracked
    - git reset --hard num_commit -> limpa o working directory, por exemplo no soft depois de fazer o reset os arquivos criados ficam unmodified(depois de fazer o git add), no mixed ficam untracked(precisa fazer git add) e no hard os arquivos não existem mais pois o working directory foi limpado

* ### `git config --global` : 
    - altera as configurações
    - git config --global --list -> mostra todas as configurações
    - git config --global user.name "usuario" -> define o nome do usuário
    - git config --global user.email "email@email.com" -> altera o email
    - git config --global --unset user.name -> apaga o nome do usuário
    - git config --global --unset user.email -> apaga o email
    - git config --global --edit -> edita o arquivo de configuração


* ### `git cherry-pick`
    - git cherry-pick numCommit -> transfere o commit de um branch para outra
    - Exemplo fiz um commit na branch master/main e não devia, então faço um checkout para a branch certa por exemplo branch develop e dentro da branch executo o comando 
    - para pegar o has do commit executar o git log e copiar o hash

