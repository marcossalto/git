## Configuración básica

Configurar nombre que sale en los commits
```ssh
	git config --global user.name "Marcos Salto"
```
Configurar email
```ssh	
	git config --global user.email marcosasalto@gmail.com
```
Marco de colores para los comandos
```ssh
	git config --global color.ui true
```

## Iniciando repositorio

Iniciamos GIT en la carpeta donde está el proyecto
```ssh
	git init
```
Clonamos el repositorio de github o bitbucket
```ssh
	git clone <url>
```
Añadimos todos los archivos para el commit
```ssh
	git add .
```
Hacemos el primer commit
```ssh
	git commit -m "Texto que identifique el propósito del commit"
```
subimos al repositorio
```ssh
	git push origin master
```

## GIT CLONE

Clonamos el repositorio de github o bitbucket
```ssh
	git clone <url>
```
Clonamos el repositorio de github o bitbucket 
```ssh
	git clone <url> git-demo
```

## GIT ADD

Añadimos todos los archivos para el commit
```ssh
	git add .
```
Añadimos el archivo para el commit
```ssh
	git add <archivo>
```
Añadimos todos los archivos para el commit omitiendo los nuevos
```ssh
	git add --all 
```
Añadimos todos los archivos con la extensión especificada
```ssh
	git add *.txt
```
Añadimos todos los archivos dentro de un directorio y de una extensión específica
```ssh
	git add docs/*.txt
```
Añadimos todos los archivos que están dentro de un directorio
```ssh
	git add docs/
```
## GIT COMMIT

Cargar en el HEAD los cambios realizados
```ssh
	git commit -m "Texto que identifique el propósito del commit"
```
Agregar y Cargar en el HEAD los cambios realizados
```ssh
	git commit -a -m "Texto que identifique el propósito del commit"
```
De haber conflictos, los muestra
```ssh
	git commit -a 
```
Agregar al último commit, este no se muestra como un nuevo commit en los logs. Se puede especificar un nuevo mensaje
```ssh
	git commit --amend -m "Texto que identifique el propósito del commit"
```
## GIT PUSH

Subimos al repositorio
```ssh
	git push <origien> <branch>
```
Subimos un tag
```ssh
	git push --tags
```
## GIT LOG

Muestra los logs de los commits
```ssh
	git log
```
Muestras los cambios en los commits
```ssh
	git log --oneline --stat
```
Muestra gráficos de los commits
```ssh
	git log --oneline --graph
```
## GIT DIFF

Muestra los cambios realizados a un archivo
```ssh
	git diff
	git diff --staged
```
## GIT HEAD

Saca un archivo del commit
```ssh
	git reset HEAD <archivo>
```
Devuelve el último commit que se hizo y pone los cambios en staging
```ssh
	git reset --soft HEAD^
```
Devuelve el último commit y todos los cambios
```ssh
	git reset --hard HEAD^
```
Devuelve los 2 últimos commit y todos los cambios
```ssh
	git reset --hard HEAD^^
```
Rollback merge/commit
```ssh
	git log
	git reset --hard <commit_sha>
```
## GIT REMOTE

Agregar repositorio remoto
```ssh
	git remote add origin <url>
```
Cambiar de remote
```ssh
	git remote set-url origin <url>
```
Remover repositorio
```ssh
	git remote rm <name/origin>
```
Muestra lista repositorios
```ssh
	git remote -v
```
Muestra las branches remotas
```ssh	
	git remote show origin
```
Limpiar todas las branches eliminadas
```ssh
	git remote prune origin 
```
## GIT BRANCH

Crea una branch
```ssh
	git branch <nameBranch>
```
Lista las branches
```ssh
	git branch
```
Comando -d elimina la branch y la une a la master
```ssh
	git branch -d <nameBranch>
```
Elimina sin preguntar
```ssh
	git branch -D <nameBranch>
```
## GIT TAG

Muestra una lista de todos los tags
```ssh
	git tag
```
Crea un nuevo tags
```ssh
	git tag -a <verison> - m "esta es la versión x"
```
## GIT REBASE

Los rebase se usan cuando trabajamos con branches. Esto hace que las branches se pongan al día con la master sin afectar a la misma

Une la branch actual con la master. Esto no se puede ver como un merge
```ssh
	git rebase
```
Cuando se produce un conflicto, nos da las siguientes opciones:

cuando resolvemos los conflictos --continue continúa la secuencia del rebase donde se pausó
```ssh	
	git rebase --continue 
```
Omite el conflicto y sigue su camino
```ssh
	git rebase --skip
```
Devuelve todo al principio del rebase
```ssh
	git reabse --abort
```
Para hacer un rebase a una branch especifica
```ssh	
	git rebase <nameBranch>
```
## OTROS COMANDOS

Lista un estado actual del repositorio con lista de archivos modificados o agregados
```ssh
	git status
```
Quita del HEAD un archivo y le pone el estado de no trabajado
```ssh
	git checkout -- <file>
```
Crea una branch en base a una online
```ssh
	git checkout -b newlocalbranchname origin/branch-name
```
Busca los cambios nuevos y actualiza el repositorio
```ssh
	git pull origin <nameBranch>
```
Cambiar de branch
```ssh
	git checkout <nameBranch/tagname>
```
Une la branch actual con la especificada
```ssh
	git merge <nameBranch>
```
Verifica cambios en el repositorio online con el local
```ssh
	git fetch
```
Borrar un archivo del repositorio
```ssh
	git rm <archivo> 
```

## Fork

Descargar remote de un fork
```
	git remote add upstream <url>
```

Merge con master de un fork
```
	git fetch upstream
	git merge upstream/master
```
