## Terminologia

### Stage
  Lugar donde podemos confirmar los archivos y carpetas que conformaran el
  commit.

### ??
  Significa que el archivo no tiene seguimiento

## Comandos CLI


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

* Agregar archivos al stage

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

  ..1. Crear /.gitignore
  ..2. Por linea especificar que archivos se desean ignorar
  ..3. Si se desear ignorar todo un directorio especificar [nombre_directorio/]
