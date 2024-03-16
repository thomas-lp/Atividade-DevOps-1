# O que eu fiz para essa atividade:

## 1 - Criei um repositório local
    cd caminho/para/diretorio
    git init

## 2 - Adicionei as branchs seguindo o gitflow
  ### 2.1 - Renomeei a branch master para main
      git branch -m master main
  ### 2.2 - Adicionei a branch develop
      git branch develop 
      git chekout develop
      ou
      git checkout -b develop
  
## 3 - No GitHub, criei o respositório remoto vazio e subi o local
    git remote add origin URL_do_repositório_remoto
    git push -u origin main
    git push -u origin develop

## 4 - Voltando a trabalhar local: criei uma feature chamada Hello world
  ### 4.1 - Criei a branch para trabalhar nela, a partir de develop
      git checkout -b feature/Hello_world develop
  ### 4.2 - Criei o arquivo que representa a feature em si
      echo "Hello World!!!" > hello_world.txt
  ### 4.3 - Preparei a feature para commitar
      git add hello_world.txt
      git commit -m "Add Hello World!!! feature"
  ### 4.4 - Subi (push) a feature (branch)
      git push -u origin feature/Hello_world

## 5 - Fiza o merge para a branch develop
    git checkout develop
    git merge feature/Hello_world

## 6 - Removi a branch Hello word
    git branch -d feature/Hello_world
    git push origin --delete feature/Hello_world

## 7 - Fiz o merge para a branch release 
    git checkout release
    git merge develop

## 8 - Criei uma tag para a release
    git tag -a nome_da_tag -m "Mensagem da tag"

## 9 - Subi para a produção (branch main)
    git checkout main
    git merge release
    git push origin main

## Outros comandos úteis que usei em alguns momentos:
    -- Excluir o repositório (Linux): 
    rm -rf .git

    -- Excluir o repositório (Windows):
    Remove-Item -Recurse -Force .git
