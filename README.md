<h1 align="center">Comandos de Git</h1>

![portada](https://raw.github.com/davidorellana98/aprende-git/main/images/portada.png)

- **Comando para saber la versión de git instalada**

```markdown
git version
```
Este comando te permite saber la versión actual que tienes instalada en tu ordenador.

- **Comandos de ayuda**

```markdown
git help <nombre del comando>

// Ejemplo

git help status
```
Este comando abrirá una página en el navegador indicando la información de ayuda que existe en un comando en especifico.

```markdown
git <nombre del comando> -h

// Ejemplo

git add -h
```
Este comando te permite ver las opciones de ayuda que existe acerca de un comando en especifico (la información se representara desde la terminal).

- **Comando para abrir un software de gestión del proyecto**

```markdown
gitk
```
Este comando te muestra un software con todos los procesos que se han hecho en el proyecto y tiene una representación más visual del seguimiento de cada archivo, tiene el estilo de las plataforma como Github Desktop, GitKraken, entre otras, con ciertas limitaciones.

- **Comandos para configurar Git**

```markdown
git config -l
- o -
git config --list
```
Estos comandos te permite ver la lista de configuración actual de git.

```markdown
git config --global user.name "<Tu nombre y apellido>"

// Ejemplo

git config --global user.name "David Orellana"
```
Este comando te permite colocar un nombre de usuario a git para tener presente quien trabaja en dicho proyecto.

```markdown
git config --global user.email <dirección de correo electrónico>

// Ejemplo

git config --global user.email ejemplo@gmail.com
```
Este comando te permite asignar un correo electrónico a la configuración de git, es recomendable utilizar el email que tiene por defecto en su cuenta de Github, Gitlab o Bitbucket.

```markdown
git config --global init.defaultBranch <nombre de la rama principal>

// Ejemplo

git config --global init.defaultBranch main
```
Este comando te permite establecer la rama predeterminada al inicializar un nuevo repositorio (no cambia la rama predeterminada en repositorios ya existentes).

- **Comando para inicializar un proyecto**

```markdown
git init
```
Este comando inicializa la carpeta de su proyecto como un repositorio de Git generando una capeta oculta **.git** dentro del directorio de su proyecto. La carpeta **.git** contiene todos los elementos esenciales necesarios para controlar la versión de su nuevo proyecto (este comando se debe ejecutar solamente una vez en el proyecto actual).

- **Comando para saber el estado de tus archivos**

```markdown
git status
```
Este comando te permite saber en que estado están tus archivos, es decir si esta limpio, eliminado, modificado, agregado al staging area o se encuentra en el working directory o espacio de trabajo.

```markdown
git status -s
```
Este comando te permite saber en que estado están tus archivos (modificado, agregado o eliminado) de una forma más corta y fácil de leer (solo código y nombre del archivo). Además, posee unos código para mejor entendimiento como: **A** (archivo agregado al Staging Area), **M** (archivo modificado en el Working Directory), **D** (archivo eliminado) y **??** (archivo no agregado o no esta en seguimiento).

- **Comandos para guardar información temporal en el Stash, sin hacer confirmaciones al repositorio local**

```markdown
git stash

- o -

git stash save "<mensaje opcional de recordatorio>"
```
Este comando guarda los cambios que se han modificado en un archivo existente o reasteado por git de manera local y restaura el directorio de trabajo al estado del último commit, sin perder la información modificada. Además, es opcional guardar un nombre al Stash.

```markdown
git stash list
```
Este comando permite visualizar todos los stashes disponibles.

```markdown
git stash pop <nombre del stash>

// Ejemplo

git stash pop stash@{1}
```
Este comando permite recuperar los cambios guardados y borrarlo del almacenamiento del stash a la vez. 

```markdown
git stash apply <nombre del stash>

// Ejemplo

git stash apply stash@{1}
```
Este comando permite recuperar los cambios guardados y tener una copia en el almacenamiento del stash.

```markdown
git stash drop <nombre del stash>

// Ejemplo

git stash drop stash@{1}
```
Este comando permite borrar un stash en especifico, con toda la información almacenada ({n} entre llaves puedes indicar el indice del stash a eliminar).

```markdown
git stash clear
```
Este comando permite eliminar de manera permanente todos los stashes guardados en un repositorio git.

- **Comandos para añadir archivos al Staging area**

```markdown
git add <nombre del archivo>

// Ejemplo

git add test.js
```
Este comando te permite añadir un archivo especifico que estaba en el working directory (espacio de trabajo) al staging area (área de preparación).

```markdown
git add .
- o -
git add -A
```
Este comando te permite añadir de una manera super rápida todos los archivos que estaban en el working directory y llevarlos al staging area.

- **Comandos para confirmar los cambios de uno o varios archivos**

```markdown
git commit
```
Este comando te abrirá un editor de texto (vim) para poder asignarle un mensaje y confirmar los cambios que estaban en el staging area y enviarlo al repositorio local. Para poder escribir y salir del editor, siga los siguientes pasos:
1. Presione (**i**) para comenzar a escribir en el editor.
2. Presione (**esc**) para dejar de escribir.
3. Inserte (**:wq**) para guardar lo escrito y poder salir.

```markdown
git commit -m "<comentario de los cambios>"

// Ejemplo

git commit -m "primer commit"
```
Este comando te permite asignar un mensaje de confirmación a los cambios realizados, sin la necesidad de abrir un editor de texto.

```markdown
git commit -am "<comentario de los cambios>"

// Ejemplo

git commit -am "Actualización README.md"
```
Este comando te permite agregar (utilizando en su interior el comando git add) y asignar un mensaje de confirmación a los cambios realizados, todo desde este único comando. Hay que tener en cuenta que este comando solo esta permitido para archivos modificados, no para archivos nuevos.

```markdown
git commit --amend
```
Este comando te abrirá un editor de texto para modificar el mensaje de confirmación más reciente, el cual sobrescribirá el mensaje anterior para crear un nuevo mensaje de confirmación. Si la confirmación solo existe en tu repositorio local y no ha sido subido a un repositorio remoto puedes modificar el mensaje de confirmación.

```markdown
git commit --amend -m "<nuevo comentario de los cambios>"

// Ejemplo

git commit --amend -m "adición de nueva fecha"
```
Este comando te permite modificar el mensaje de confirmación más reciente para sobrescribirlo y hacer un nuevo mensaje de confirmación, sin necesidad de abrir un editor de texto.

```markdown
git commit --amend --no-edit
```
Este comando te ayuda a no instanciar un nuevo commit si haz modificado un archivo, ya que considera el mismo mensaje del commit anterior.

- **Comandos para crear, borrar y moverse entre ramas**

```markdown
git branch
```
Este comando te permite visualizar el listado de ramas creadas.

```markdown
git branch <nombre de la nueva rama>

// Ejemplo

git branch develop
```
Este comando te permite crear una nueva rama de trabajo, pero no te direcciona a dicha rama creada.

```markdown
git branch -m <antiguo nombre de la rama> <nuevo nombre de la rama>

// Ejemplo

git branch -m develop release
```
Este comando te permite cambiar el nombre de una rama existente.

```markdown
git checkout -b <nombre de la rama>
- o -
git switch -c <nombre de la rama>

// Ejemplo

git checkout -b test
- o -
git switch -c test
```
Estos comandos te permiten crear una nueva rama y direccionarte a dicha rama de manera automática.

```markdown
git checkout <nombre de la rama>
- o -
git switch <nombre de la rama>

// Ejemplo

git checkout test
- o -
git switch test
```
Estos comandos te permiten cambiar a una rama especifica, pero si la rama no existe, no la crea ni te cambia a dicha rama.

```markdown
git checkout -
```
Este comando te permite regresar a la ultima rama utilizada anteriormente.

```markdown
git branch -D <nombre de la rama>

// Ejemplo

git branch -D develop
```
Este comando te permite eliminar una rama existente de manera local de forma forzosa ignorando cualquier advertencia.

```markdown
git branch -d <nombre de la rama>

// Ejemplo

git branch -d hotfix
```
Este comando te permite eliminar una rama existente de manera local, una vez que se haya mergeado (fusionado) con otra rama o eliminar una rama sin contenido de información.

```markdown
git branch --merged
```
Este comando te muestra la lista de ramas que se han fusionado o mergeado.

```markdown
git branch -a
```
Este comando te permite ver las ramas tanto locales como las subidas al repositorio remoto.

- **Comandos para ver el historial de confirmaciones**

```markdown
git log
```
Este comando te permite ver todo el historial de commits realizados con su respectivo hash, además de su autor y fecha de creación.

```markdown
git log --author "<nombre del autor>"

// Ejemplo

git log --author "David Orellana"
```
Este comando te permite saber quien esta realizando los cambios en dicha actividad del proyecto.

```markdown
git log --grep "<cadena de texto>"

// Ejemplo

git log --grep "Primer commit"
```
Este comando te permite averiguar si en dichos commits realizados se encuentra dicha cadena de texto.

```markdown
git log --oneline
```
Este comando te permite visualizar la información de una manera más resumida (solo hash y mensaje del commit).

```markdown
git log --oneline --all --graph --decorate
```
Este comando te permite visualizar de una manera más estructurada como están conectadas las ramas, confirmación de commits y su hash especifico.

```markdown
git log -n <número>
- o -
git log -<número>

// Ejemplo

git log -n 3
- o -
git log -3
```
Este comando te permite visualizar un determinado número de commit realizados recientemente, comenzando desde el Head o cabecera.

```markdown
git reflog
```
Este comando te permite visualizar todo el registro de acciones que se han hecho en tu repositorio, como por ejemplo inserciones, cambios, eliminaciones, fusiones entre ramas, etc.

- **Comandos para analizar el contenido de archivos**

```markdown
git show <nombre del archivo>

// Ejemplo

git show index.html
```
Este comando te muestra la información del archivo y lo que se añadio recientemente, además incluye el mensaje del commit y metadatos como el autor y la fecha.

```markdown
git diff <nombre del archivo>

// Ejemplo

git diff index.html
```
Este comando te muestra la información del archivo y sus cambios realizados antes de añadirlos al staging area, es útil para hacer comparaciones. Sí añadio el archivo al staging area el comando no podrá visualizar su contenido.

```markdown
git diff <hast de commit 1> <hast de commit 2>

// Ejemplo

git diff 6c69d583f81fe58fa86ce453272163187779ffb6 a49adc92b1e360d1673d9df077587ed02c66e6b7
```
Este comando te permite comparar la información que hay entre dos commits añadidos al repositorio local.

```markdown
git checkout <hash del commit>

// Ejemplo

git checkout a49adc92b1e360d1673d9df077587ed02c66e6b7
```
Este comando te permite ver la información del contenido que tiene cierto commit en particular (hay que tener en cuenta el hash del commit para poder interactuar).

- **Comandos para ignorar cambios en un archivo**

```markdown
git restore --staged <nombre del archivo>

// Ejemplo

git restore --staged test.txt
```
Este comando te permite regresar un archivo que estaba añadido al staging area al working directorio o area de trabajo, sin perder la información.

```markdown
git restore <nombre del archivo>

// Ejemplo

git restore test.txt
```
Este comando te permite descartar los cambios que se realizo en el archivo, antes de añadirlo al staging area (no esta permitido para archivos nuevos). Además permite restaurar un archivo que fue elimando, antes de añadir y hacer commit a dicho archivo, ya que si se lo realizada está especificando que a eliminado dicho archivo.

```markdown
git reset <hash del commit>

// Ejemplo

git reset 6c69d583f81fe58fa86ce453272163187779ffb6
```
Este comando te permite regresar a un hash de commit especifico, teniendo en cuenta que los archivos que estuvieron antes, vuelven al working directory para ser añadidos y comitiados nuevamente, sin perder la información.

```markdown
git reset --soft <hash del commit>

// Ejemplo

git reset --soft 6c69d583f81fe58fa86ce453272163187779ffb6
```
Este comando te permite regresar a un hash de commit especifico, teniendo en cuenta que los archivos que estuvieron antes vuelven al staging area, para ser comitiados nuevamente (no se pierde la información, que fue añadida en los archivos anteriormente).

```markdown
git reset --hard <hash del commit>

// Ejemplo

git reset --hard bc7bd7cdd3540cee368b2fa8595066ce096322fe
```
Este comando te permite regresar a un de hash de commit especifico, teniendo en cuenta que los archivos que fueron añadidos al repositorio local, se eliminaran permanente (hay que utilizar este comando con mucha precaución).

```markdown
git reset --hard HEAD~1
```
Este comando te permite eliminar toda la información del commit reciente y regresar a la información del contenido del commit anterior, convirtiéndola nuevamente en el HEAD.

```markdown
git reset --mixed
```
Este comando te permite regresar al working directory, si haz agregado archivos al staging area, hay que tener en cuenta que si haz hecho commit este comando no te ayudará a regresar al working directory ni al staged.

```markdown
git checkout -- <nombre del archivo>

// Ejemplo

git checkout -- index.html
```
Este comando te permite resetear o simplemente devolver a la versión que estaba antes de utilizar dicho archivo, la información que tenia de elimina de forma permanente.

- **Comandos para eliminar archivos y directorios**

```markdown
git rm <nombre del archivo>

// Ejemplo

git rm index.html
```
Este comando te permite eliminar archivos del repositorio local de git, teniendo en cuenta que necesitas realizar un commit, para confirmar la eliminación del archivo en su totalidad.

```markdown
git rm --cached <nombre del archivo>

// Ejemplo

git rm --cached index.html
```
Este comando te permite regresar tu archivo al working directory, si ha estado rasteado por git (staging area).

```markdown
git rm -f <nombre del archivo>

// Ejemplo

git rm -f index.html
```
Este comando te permite eliminar archivos de forma forzosa y permanente sin preguntar por confirmación, incluso si el archivo tiene cambios no confirmados. Es útil cuando deseas eliminar un archivo sin preocuparte por los cambios locales no confirmados.

```markdown
git rm -r <nombre del directorio>

// Ejemplo

git rm -r carpeta_git
```
Este comando te permite eliminar directorios con toda su información incluida, teniendo en cuenta que se necesita realizar un commit, para confirmar la eliminación del directorio en su totalidad.

```markdown
git rm -rf <nombre del directorio>

// Ejemplo

git rm -rf carpeta_git
```
Este comando te permite eliminar directorio de forma forzosa y permanente sin preguntar por confirmación, incluso si en el directorio tiene cambios no confirmados. Es útil cuando deseas eliminar directorios sin preocuparte por su información.

- **Comandos para fusionar ramas**

```markdown
git merge <nombre de la rama a fusionar>

// Ejemplo

git merge develop
```
Este comando te permite fusionar dos ramas y obtener la información del contenido completo en una sola rama, pero si existe conflictos de contenido se tendrán que resolver para poder fusionar y luego añadirlo al staged y realizar un mensaje de confirmación de dichas ramas fusionadas. Al momento de fusionar la rama, tener en cuenta la rama en la que deseas que esten los cambios añadidos y luego colocar el comando con la rama a fusionar.

```markdown
git merge --abort
```
Este comando te permite abortar un proceso de fusión que esta en proceso y regresar al estado anterior antes de realizar un merge entre ramas.

- **Comandos para conectar e interactuar con un repositorio remoto**

```markdown
git clone <Url del repositorio remoto>

// Ejemplo

git clone https://github.com/davidorellana98/aprende-git.git
```
Este comando te permitirá clonar un repositorio completo alojado en un servidor y traerlo a tu máquina local.

```markdown
git remote add <nombre del repositorio remoto> <Url del repositorio remoto>

// Ejemplo

git remote add origin https://github.com/davidorellana98/aprende-git.git
```
Este comando te permite vincularte o conectarte con un repositorio remoto.

```markdown
git remote -v
```
Este comando te ayuda a saber los orígenes remotos conectados con el repositorio.

```markdown
git push -u <nombre del repositorio remoto> <nombre de la rama>
- o -
git push --set-upstream <nombre del repositorio remoto> <nombre de la rama>

// Ejemplo

git push -u origin main
- o -
git push --set-upstream origin main
```
Este comando te permite subir la rama con tu código a un repositorio remoto conectado anteriormente. Si deseas subir un nuevo contenido a tu repositorio remoto, solo ejecutas el comando **git push** sin las demás especificaciones, teniendo en cuenta a la rama que se subió en el remoto.

```markdown
git push --force <nombre del repositorio remoto> <nombre de la rama>

// Ejemplo

git push --force origin main
```
Este comando te permite subir tu repositorio local al servidor remoto, de manera forzosa, es decir que va a ignorar cualquier conflicto que pueda ocurrir.

```markdown
git push <nombre del repositorio remoto> --delete <nombre de la rama remota>

// Ejemplo

git push origin --delete develop-remote
```
Este comando te permite borrar una rama que se encuentra en el repositorio remoto.

```markdown
git pull <nombre del repositorio remoto> <nombre de la rama>

// Ejemplo

git pull origin main
```
Este comando te permite recuperar cambios desde un repositorio remoto y fusionar esos cambios a tu repositorio local.

## Comandos de Linux

Para aprender los comandos de Linux puedes visitar este repositorio de [GITHUB.](https://github.com/davidorellana98/aprende-linux)

## Contribuye con un comando 🤝

Sabemos que el trabajo en equipo, es mucho más eficaz y tiene un mayor número de resultados, por eso te animo a que puedas contribuir con algunas correcciones del repositorio o algún comando adicional de Git, haciendo un **pull request** a este repositorio de Github.

Cada pull request que realices te ayudara a crecer como programador o programadora y además poder ayudar a miles de personas a saber más de los comandos de Git ❤️

Si te ha parecido útil este repositorio apóyalo con una estrellita ⭐

## Licencia

Consulte el archivo [LICENSE](https://github.com/davidorellana98/aprende-git/blob/main/LICENSE.md) para conocer los derechos y limitaciones de la licencia (Creative Commons).
