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