# Hola Mundo en Git

Líneas básicas de comandos en git:
- `git add <file>` empieza a vigilar el archivo dado.
- `git status` muestra el estado actual de la carpeta.
- `git commit -m "Comentario"` hace envío de lo que haya en `add` (*staging*)
- `git show` muestra los cambios con respecto al último `commit`
- `git diff <etiqueta1> <etiqueta2>` realiza la comparación de dos archivos.
- `git rm <file>` elimina un `commit`.
  - `git rm --cached <file>` elimina un archivo cargado en *staging*.
- `git reset <etiqueta> --hard` vuelve a la versión indicada, 
  - `--hard` cambia todo.
  - `--soft` se vuelve a la versión anterior pero se conserva el *staging*. (El entorno de Git nor retrocede)
- `git diff` muestra las diferencias del archivo actual con lo que haya en *staging*.
- `git log --stat` muestra los cambios específicos de *bytes* de los registros en `log`.

Esta suele ser la forma más común de moverse entre versiones del archivo, puesto que `reset` elimina los `log`, a diferencia de `checkout`:
- `git checkout <etiqueta del archivo antiguo que quiero visualizar> <nombre del archivo>` esto me permite visualizar un archivo dado en un estado antiguo. Nótese que esto no cambiará directamente el archivo a menos que se haga un `commit`, pues el propósito es visualizar un estado anterior. Para revertir los cambios podemos hacer uso de:
  - `git checkout master <nombre del archivo>`.

- `git reset HEAD`: Este es el comando para sacar archivos del área de staging. No para borrarlos ni nada de eso, solo para que los últimos cambios de estos archivos no se envíen al último commit, a menos que cambiemos de opinión y los incluyamos de nuevo en staging con git add, por supuesto.
  

## Comandos para trabajo remoto con GIT
- `git clone url_del_servidor_remoto`: Nos permite descargar los archivos de la última versión de la rama principal y todo el historial de cambios en la carpeta .git.
- `git push`: Luego de hacer git add y git commit debemos ejecutar este comando para mandar los cambios al servidor remoto.
- `git fetch`: Lo usamos para traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local (en caso de que hayan, por supuesto).
- `git merge`: También usamos el comando git merge con servidores remotos. Lo necesitamos para combinar los últimos cambios del servidor remoto y nuestro directorio de trabajo.
- `git pull`: Básicamente, git fetch y git merge al mismo tiempo.

Una vez hayamos hecho uso de `git add`, podemos omitir el paso de `git add` y `git commit` haciendo uso de `git commit -am`

- Con `git branch <nombre de la nueva rama>` podemos crear una rama nueva.
- Para movernos de ramas `git checkout <nombre de la rama>`.
- `git merge <nombre de la rama a traer> -m "Descripción"` De esta manera se unen las ramas.

## GitHub
Para añadir un espacio remoto hacemos uso de `git remote add origin <dirección https>`
- con `git remote` vemos los origenes.
- con `git remote -v` vemos los enlaces de los origenes.
- Para hacer los envíos a github `git push origin master`

Note que en la versión actual de GitHub la rama principal es *main* por ende debemos crear dicha rama y desde ahí hacer el push.
Una vez creamos la rama y estamos conectados a `remote` debemos hacer un `pull` (`clone` y `merge`) antes de hacer nuestro `push` puesto que en un inicio son archivos diferentes. 
- `git pull origin main`.
Notese que se puede tratar de "historias diferentes" por lo que hacemos uso de:
- `git pull origin main --allow-unrelated-histories`

Una vez hecho el pull, ya podemos hacer un `push` desde main, y es eso lo que veremos en GitHub