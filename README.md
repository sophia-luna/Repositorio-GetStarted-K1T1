# GIT

## Estados

* Untracked
* Unmodified
* Modified
* Staged

### Criar novo repositório

	git init

### Verificar estado dos arquivos/diretórios

	git status

### Adicionar arquivo/diretório (staged area)

##### Adicionar um arquivo em específico

	git add myfile

##### Adicionar um diretório em específico

	git add mydir

##### Adicionar todos os arquivos/diretórios
	
	git add .
    
### Comitar arquivo/diretório

##### Comitar um arquivo
	
	git commit myfile

##### Comitar vários arquivos

	git commit file1 file2
	
##### Comitar informando mensagem

	git commit file -m "minha mensagem de commit"

### Remover arquivo/diretório

##### Remover arquivo

	git rm myfile

##### Remover diretório

	git rm -r diretorio

### Visualizar Alterações

#### modified file

    git diff file1 file2

### staged file

    git diff --cached or --staged

### Visualizar histórico

##### Exibir histórico
	
	git log
	
##### Exibir histórico com diff das N últimas alterações

	git log -p -N

#### listagem com hash parcial e mensagem apenas

    git log --oneline

### historico com diff dos commits

    git log -p
    
##### Exibir resumo do histórico (hash completa, autor, data, comentário e qtde de alterações (+/-))

	git log --stat
    
### Alterando um commit

#### Mensagem de commit errada

    git commit --amend -m mensagemAtualizada

#### Adicionar arquivo staged que ficou para tras ultimo commit

    git commit --amend --no-edit
    
#### Acessar versao de commit antigo

    git checkout hashCommit
    
#### Voltat para versao de commit mais atual

    git checkout master

#### Remover untreacked file

    git clean -f

### Ingnorando arquivos

#### Criar um gitignore, abrir .gitignore e listar os que devem ser ignorados

    touch .gitignore

### Clonando repository

    git clone repoOriginal repoClone


## Repositório Remoto

### Exibir os repositórios remotos

	git remote
	
	git remote -v

### Vincular repositório local com um repositório remoto

	git remote add origin git@github.com:leocomelli/curso-git.git
	
### Exibir informações dos repositórios remotos

	git remote show origin

### Atualizar repositório local de acordo com o repositório remoto

##### Atualizar os arquivos no branch atual

	git pull
	
##### Buscar as alterações, mas não aplica-las no branch atual

	git fetch
	
### Clonar um repositório remoto já existente

	git clone git@github.com:leocomelli/curso-git.git

### Branch

#### Listagem de branches

    git branch
    git branch --list

#### Criar branch

    git branch nomeBranch

#### Acessar branch

    git checkout nomeBranch
    git switch nomeBranch

#### Criar e acessar branch

    git checkout -b nomeBranch
    git switch -c nomeBranch

#### Primeiro push na branch

    git push --set-upstream origin nomeBranch
    git push -u origin nomeBranch

#### Remover branch local

    git branch -d nomeBranch
    
#### Remover branch remota

    git push --delete origin nomeBranch

#### Renomear branch

    git branch -m nomeBranch novoNome


### Merge

#### importante estar na main

    git switch main
    git merge nomeBranch

	
### Tags

##### Criando uma tag leve

	git tag vs-1.1

##### Criando uma tag anotada

	git tag -a vs-1.1 -m "Minha versão 1.1"

##### Criando tag a partir de um commit (hash)

	git tag -a vs-1.2 9fceb02
	
##### Criando tags no repositório remoto

	git push origin vs-1.2
	
##### Criando todas as tags locais no repositório remoto

	git push origin --tags