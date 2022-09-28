# GIT
## Configurar usuario
  - git config -global user.name `nombre` :: configurar nombre
  - git config -global user.email `email` :: configurar email 
  - git config -list :: listar usuarios
## Cambios en los archivos de git:
  - git show `archivo` :: muestra los cambios en el archivo
  - git status :: visualizar los estados de archivos y carpetas
  - git log `archivo` :: historico de cambios con detalles
  - git pull :: traer repositorio remoto
  - git checkout `deDonde` `aDonde`:: traer cambios realizados
  - git rm --cached `archivo` :: devolver el archivo en ram
  - git config --list :: configuracion de git
  - git log `archivo` :: historial del archivo
  - git diff `idComit` `idComit` :: compara los commits
  - git reset HEAD (--hard)(--soft)`idComit`:: devuelvo los archivos en staged/unstaged/untracked

## Staging: 
Area en memoria ram donde los archivos pasan para llegar a la repo(.git)
  - git add :: lo agrega al Staging(untracked->unstaged)
  - git rm `--cached(move to untracked)` `--force(remove total)`:: lo elimina del staging
  - git commit :: lo agrega al repositorio(.git/master)(unstaged->tracked)

## Ramas:
version del codigo del proyecto
  - git branch `nombre` :: crear una rama
  - git show-branch --all :: info detallada de las ramas
  - git branch -r : ramas remotas
  - git branch -a :: todas las ramas
  - git checkout `nombre` :: cambiar a la rama
  - git checkout -b `nombre` :: crea la rama y nos mueve a ella
  - git push origin `branchName` :: llevar la rama a la repo
  - git reset `idComit` :: lleva al commit no importa la rama, eliminando los commit posteriores
  - git checkout `idComit` :: lleva al commit sin borrar los commit posteriores
  - :: se puede borrar commits con `git reset` y ramas con `git branch -d`
  - #### Merge: Unir dos ramas recuerda que es un commit
    - git merge --abort :: cancela el merge

## Tags - Versiones:
Permiten asignar versiones a los commits con cambios importantes
  - git tag -a `tagName` `idComit` :: crear tag y asignarlo a un commit
  - git tag -d `tagName` :: borrar tag 
  - git tag | git show-ref --tags :: listar tags
  - git push origin --tags :: publicar tag en la repo
  - git push origin -d :refs/tags/nombre-tag :: borrar tag en la repo

## Remoto:
  - git clone `url` :: download archivos y todo el historial a .git
  - git push :: manda cambiar a el repositorio remoto
  - git fetch :: traer actualizaciones del servidor
  - git merge :: combinar los ultimos cambios del servidor y nuestra carpeta de trabajo
  - git pull :: git fetch y merge al mismo tiempo
  - git remote add origin `url` :: agregar repo url
  - git remote -v :: lista las urls
  - git remote set-url origin `url` :: cambiar repo url
  - #### SSH: 
    - Configurar llaves ssh en local :: ssh-keygen -t rsa -b 4096 -C "email"
    - Encender el servidor de llaves ssh :: eval $(ssh-agen -S)
    - A;adir tu llave ssh a el servidor :: ssh-add ruta-ssh
    - Conectar ssh a github :: crear ssh key en personal settings
    - Cambiar la url a ssh si lo tienes con https 
  - #### Colaboradores:
    - Agregar colaboradores :: Repositorio -> Settings -> Collaborators
    - Mensaje de commit erroneo ::
      - git commit -amend
      - git pull origin master
      - git push --set-upstream origin master

#### Logs
  - git log --oneline:Te muestra el id commit y el título del commit.
  - git log --decorate: Te muestra donde se encuentra el head point en el log.
  - git log --stat: Explica el número de líneas que se cambiaron brevemente.
  - git log -p: Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.
  - git shortlog: Indica que commits ha realizado un usuario, mostrando el usuario y el título de sus commits.
  - git log --graph --oneline --decorate y
  - git log --pretty=format:"%cn hizo un commit %h el dia %cd": Muestra mensajes personalizados de los commits.
  - git log -3: Limitamos el número de commits.
  - git log --after=“2018-1-2”
  - git log --after=“today” y
  - git log --after=“2018-1-2” --before=“today”: Commits para localizar por fechas.
  - git log --author=“Name Author”: Commits hechos por autor que cumplan exactamente con el nombre.
  - git log --grep=“INVIE”: Busca los commits que cumplan tal cual está escrito entre las comillas.
  - git log --grep=“INVIE” –i: Busca los commits que cumplan sin importar mayúsculas o minúsculas.
  - git log – index.html: Busca los commits en un archivo en específico.
  - git log -S “Por contenido”: Buscar los commits con el contenido dentro del archivo.
  - git log > log.txt: guardar los logs en un archivo txt

#### Shortlog:
  - git shortlog -sn: muestra cuantos commit han hecho cada miembro del equipo.
  - git shortlog -sn --all: muestra cuantos commit han hecho cada miembro del equipo, hasta los que han sido eliminados.
  - git shortlog -sn --all --no-merge: muestra cuantos commit ha hecho cada miembro, quitando los eliminados sin los merges.
  - git blame ARCHIVO: muestra quien hizo cada cosa línea por línea.
  - git COMANDO --help:muestra como funciona el comando.
  - git blame ARCHIVO -Llinea_inicial,linea_final: muestra quien hizo cada cosa línea por línea, indicándole desde qué línea ver. Ejemplo -L35,50.

#### Otras opciones:
  - git rebase :: aprende mas sobre esto
  - git stash :: guardar cambios en memoria y luego recuperarlos
    - git stash save `message`
    - git stash list :: lista los stashNumber
    - git stash pop :: recupera los cambios guardados
    - git stash pop stash@{`stashNumber`} :: recuperar de un stash especifico
    - git stash branch `nombreBranch` :: crear una rama y aplicar el stash mas reciente
    - git stash drop :: eliminar lo mas reciente del stash
    - git stash drop stash@{`stashNumber`}
    - git stash clear :: elimina todo el stash
  - git clean :: limpia los archivos no agregados con git add
    - git clean --dry-run ::revisa los archivos no agregados
    - git clean -f :: eliminar los archivos
  -git cherry-pick :: traer commits viejos al head de un branch(evitar)

#### Casos de emergencia:
  - git reflog :: muestra todos los cambios realizados

#### Forks - Bifurcaciones:

#### Ejemplo de ramas:
  - Feature branch:
    - git checkout -b `feature-feXXX` master :: crea un branch local para la nueva feature
    - git push origin `feature-feXXX` :: lleva la feature a remoto
    - git merge master :: trae los cambios de master a la feature
    - git checkout master :: cambiar a rama master
    - git merge --no-ff `feature-feXXX` :: asegura de que se cree el commit durante el merge
    - git push origin master :: sube los cambios del merge
    - git push origin :`feature-feXXX` :: elimina la branch remota
  - Bug branch:
    - git checkout -b `bug-bgXXX` master :: crea un branch local del bug
    - git push origin `bug-bgXXX` :: lleva el bug a remoto
    - git merge master 
    - git checkout master
    - git merge --no-ff `bug-bgXXX`
    - git push origin master
    - git push origin :`bug-bgXXX`
  - Hotfixes branch:
    - git checkout -b `hotfix-hfXXX` stable
    - git push origin `hotfix-hfXXX`
    - git checkout stable
    - git merge --no-ff `hotfix-hfXXX`
    - git tag -a `tag` :: crea un tag del fix
    - git push origin stable --tags :: sube los cambios del tag
    - git checkout master
    - git merge --no-ff `hotfix-hfXXX`
    - git push origin master
    - git push origin :`hotfix-hfXXX`

Copia exacta del estado actual de un repo de github y clonarlo como un proyecto mio
