# GIT GITHUB

Guia prático para iniciantes - Aula Rocketseat Mayk Brito - [link](https://www.youtube.com/watch?v=2alg7MQ6_sI)

--------------------

* `git init` : 
    - inicia a linha do tempo, repositório

* `git add` 
    - adiciona ou atualiza mudanças para irem para a linha do tempo
    - git add nome_arquivo (altera ou adiciona um arquivo)
    - git add . (altera ou adiciona todos os arquivos)

* `git commit` 
    - adiciona um ponto na linha do tempo
    - git commit -m "mensagem do commit"
    - git commit -am "mensagem do commit" -> faz o git add e o commit

* `git log`
    - visualiza os pontos na linha do tempo e as mudanças feitas no projeto
    - mostra os commits, quem foi o autor e a data do commit 

* `git status` 
    - informa o estado das alterações do nosso projeto

* `git show` 
    - apresenta determinado commit/ponto na história com todos os detalhes do que foi alterado
    - git show (numero_commit) -> mostra o commit informado 
    - git show -> mostra o último commit

* `git branch` 
    - gerenciar novas linhas do tempo
    - git branch nome_branch -> cria nova branch(ramificação)
    - git branch -> mostra todas as branchs(ramificações), precisa estar na principal main/master
    - git branch -D nome_branch -> excluiu a branch infromada 

* `git checkout`
    - manipula as linhas do tempo
    - muda para uma branch
    - git checkout nome_branch
    - git checkout -b nome_branch -> cria e muda para uma branch, comando curto
    - git checkout numero_commit -- arquivo -> volta um arquivo para um determindado momento da linha do tempo ou recupera algo deletado

* `git merge`
    - unir as linhas do tempo/branch
    - git merge nome_branch -> precisa estar na master/main

* `git remote`
    - git remote add origin link_repositorio -> adiciona um repositorio do github na nossa aplicação
    - explicação github -> push an existing repository from the command line
    - git remote -v -> mostra os repositórios remotos

* `git push`
    - envia as alterações para o repositório remoto (github)
    - git push -u origin master -> na primeira vez é preciso criar a branch master no repositório online (github)
    - empurra o repositório local para o repositório online

* `git clone`
    - clonar um projeto, repositório
    - git clone link_repositorio

* `git pull`
    - puxa alterações do repositorio remoto atualizando o repositorio local

