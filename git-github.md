## Terminologia

### Stage
  Lugar donde podemos confirmar los archivos y carpetas que conformaran el
  commit.


### ??
  Significa que el archivo no tiene seguimiento


### Master
  Nombre de la rama principal


### Merge
* Tipos:
  * fast-forward: No hay cambios en la rama principal lo que permite que los
  cambios hechos en el branch se integren al master de manera transparente
  * Uniones automaticas: Hubo modificaciones en el master pero que no afectan el
  branch, permitiendo unir ambas
  * Manuales: Hubo modificaciones en el master y en el branch que son incompatibles
  como por ejemplo modifcaciones de los mismos archivos. En este caso se resuelve
  de manera manual.


### Tags
  Son etiquetas , generalmente se usan para resumir toda la historia hasta el
  momento. Es muy usada en releases, lo que nos permite descargar todo el
  proyecto hasta ese punto.


### Stash
  Imaginemos el stash como un baul de los recuerdos donde guardamos el estado actual
  de la rama con los cambios sin seguimiento. Entonces nos queda la rama limpia luego
  del stash (descarta todos los cambios desde el ultimo commit). Esto es usado
  cuando tenemos que hacer cambios de emergencia pero no queremos
  perder los cambios que veniamos haciendo, entonces guardamos en el stash y luego
  recuperamos.
  La pila del stash es LIFO


### Rebasing
  Accion para acomodar commits (ordenarlos, fusionarlos , entre otros).
  Util para actualizar una rama con los commits de otra rama
#### Rebase interactivo uso:
* Ordenar commits
* Corregir mensajes de commits (reword)
* Unir commits (squash)
* Separar commits (edit)


## Buenas practicas

* Hacer fetch y pull antes de hacer push

* Anres de comenzar a trabajar hacer un fetch y un status para comparar con el remoto


## Comandos CLI Git


* Inicializar git

  `git init [directorio]`

* Archivo configuraciones globales

  `git config --global -e`

* Configurar nombre y email

  `git config --global user.name "nombre"`

  `git congig --global user.email "email"`

* Volver al ultimo commit

  `git checkout -- .`

* Volver al ultimo estado de un archivo en particular

  `git checkout -- [archivo]`

* Ver el estado del arbol de trabajo. Los archivos que se encuentra en el stage

  `git status`

  `git status -s` *muestra informacion resumida*

  `git status -sb` *adiciona nombre de branch actual*

* Agregar archivos al stageciencia y tecnica parana

  `git add [archivo] [.]`  *El punto agrega todos los archivos del directorio*

  `git add "*.txt"` *Agrega todo los txt de todo el proyecto*

  `git add -u` *Actualiza todos los archivos que tienen seguimiento*

* Quitar archivos del stage

  `git reset [archivo] o [hash de commit anterior]`

* Relizar un commit (instantanea del stage)

  `git commit -m [mensaje]`

  `git commit --amend -m "[mensaje]"` *actualiza el texto del mensaje*

* Resets

  `git reset --soft [hash]` *vuelve a cierto commit manteniendo los cambios en archivos*

  `git reset --hard [hash]` *vuelve todo hasta el commit especificado eliminando cambios en archivos*

* Agregar al stage y hacer commit

  `git commit -am "[mensaje]"`

* Ver el log (historial de sucesos)

  `git log`

  `git log --oneline` *muestra informacion resumida*

  `git log --oneline --decorate --all --graph`  *muestra la info elegantemente*

  `git reflog` *se ve todo el log incluso los resets*

* Alias

  `git config --global alias.[alias] [comando]`

* Ver los cambios realizados

  `git diff` *responde con un '-' para indicar eliminaciones y un '+' incerciones*

* Eliminar archivo del proyecto

  `git rm [archivo]`

* Listar archivos para que git ignore

  1. Crear /.gitignore
  2. Por linea especificar que archivos se desean ignorar
  3. Si se desear ignorar todo un directorio especificar [nombre_directorio/]

* Branches

  `git branch [nombre de la rama]` *para crear una nueva rama*

  `git checkout [rama]` *para moverse a la rama*

  `git diff [rama1] [rama2]` *para ver las diferencias entre ramas*

  `git merge [rama]` *hace una union entre la rama y el master*

  `git branch -d [rama]` *elimina la rama*

  `git checkout -b [rama]` *crea una rama y se mueve automaticamente a ella*

* Tags

  `git tag -a [nombre_del_tag] -m ["Mensaje"]` *crea un nuevo tag acompañado del msj*

* Stashing

  `git stash save [mensaje]` *crea un nuevo stash con el mensaje*

  `git stash list` *lista todos los stash*

  `git stash pop` *extrae el ultimo stash del stack de stashes*

  `git stash save --kep-index` *guarda todo menos lo que se encuentra en el stage*

  `git stash save --include-untracked` *guarda todo incluso los q no tiene seguimiento*

  `git show stash` *muestra info del ultimo stash*

* Rebase

  `git rebase [nombre_rama]` *Se le adicionan a la rama actual los commits de la rama especificada*

  `git rebase -i` *entra en modo edicion interactiva con varias opciones. Ver usos rebase*


## Comandos CLI GitHub

* Inicialiacion

  `git remote add [nombre_origen] [link_repo]` *agrega nombre_origen como repo remoto al proyecto*

  `git push -u origin master` *sube todo el origen al master remoto. -u deja master por defecto*

  `git push --tags` *sube los tags del origen al remoto*

  `git remote -v` *muestra el origen para hacer push y fetch*

  `git clone [url_origen] <nombre_destino>` *clona un repositorio y renombra el root con nombre_dest*

  `git fetch [origen] [remoto]` *descarga los cambios de remoto sin hacer el merge*

  `git pull [origen] [remoto]` *descarga los cambios de remoto y hace el merge*
