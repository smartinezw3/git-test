# GIT
## Comandos básicos
### `git clone <url>`
Este comando se usa para clonar un repositorio, puede ser por SSH o HTTP. Hace una copia exacta del repositorio.
### `git status`
Este comando devuelve el estado de los archivos. Muestra todo lo que necesitás saber hacerca de la branch en la que estás trabajando. Muestra lo siguiente:
 - en que branch estás
 - si tu branch está desactualizada
 - si tenés cambios sin agregar
 - si tenés cambios que se agregaron pero que no se commitearon
 - los archivos que se modificaron, se agregaron o se quitaron

Por lo general se utiliza siempre.
### `git diff`
Muestra los cambios que hiciste en los archivos, este muestra la línea que se modificó pero si querés saber sólo la palabra que se modificó podés usar el comando `git diff --color-words`.
### `git checkout -b <branch-name>`
Es la forma de crear una branch nueva y de cambiarla por esa misma.  
Si sólo se quiere cambiar de branch se utiliza `git checkout <branch-name>`.
### `git add <file-name>`
Agrega el archivo para el próximo commit.  
Si se necesita agregar todos los cambios se puede utilizar `git add --all` o su versión simplificada `git add -A`.
#### `git reset HEAD <file-name>`
Si al agregar todos los archivos, accidentalemente te equivocaste, podés revertir que se agreguen utilizando este comando.
### `git commit -m "<message>"`
Este comando sirve para commitear los archivos previamente agregados.
### `git push`
Una vez que se encuentran commiteados los archivos, se procede a subir al repositorio. Digamos que es como subir los archivos a la nube.
#### `git push --set-upstream origin <branch-name>`
Cuando se hace push de una branch nueva se requiere que se suba al repositorio.
## Comandos avanzados
### `git merge <branch-name>`
Sirve para mergear entre branches, digamos que tenemos dos branches: `master` y `development`, e hicimos nuestros cambios en la branch de `development`. Entonces ahora queremos pasar todos esos cambios a `master` y una vez que se haya commiteado todo en `development` ejecutamos lo siguiente:  
 - `git checkout master`
 - `git pull` para asegurarnos de que esté actualizado
 - `git merge development`
 - `git push` para subir los cambios al repositorio

### `git fetch`
Sirve para traer todas las branch que están en el repositorio.
### `git push --delete <remote-name> <branch-name>`
Para borrar la branch del repositorio.
### `git branch -d <branch-name>` o `git branch -D <branch-name>`
Para borrar la branch local. La segunda opción con `-D` es para forzar a que borre sin chequear el estado.
### `git clean -f`
Para borrar los cambios que no se agregaron.
```bash
# Eliminar directorios
git clean -f -d
# Eliminar archivos ignorados
git clean -f -X
# Eliminar archivos ignorados o no ignorados
git clean -f -x
```
## Comandos útiles
### `git checkout -`
Este comando sirve para "altabear" entre branches.
### `git grep <word>`
Este comando sirve para buscar en todo el repositorio una palabra, más que nada utiliza el archivo `.gitignore` para obviar los archivos que no queremos buscar ya que con cualquier IDE se puede hacer lo mismo hoy en día.
### `git branch`
Este comando muestras un listado de las branches locales y la branch en la que estás trabajando.

## Guardado temporal
### `git stash`
Guarda los cambios temporalmente y los remueve del branch actual.
#### `git stash push -m "<message>"`
Guarda los cambios temporalmente y deja un mensaje a modo de referencia.
### `git stash apply`
Aplica el último guardado temporal a la branch actual.
### `git stash list`
Muestra el listado de los guardados temporales con índices ascendente, donde `{0}` es el último guardado.
### `git stash apply <number>`
Aplica el guardado temporal del `<number>`.
### `git stash drop <number>`
Elimina del listado el guardado temporal `<number>`.
### `git stash pop <number>`
Aplica el guardado temporal `<number>` y lo elimina del listado.

---
## Configuración
Para configurar el bash utilizar la siguiente línea:

```
git config --global http.proxy http://<username>:<password>@<proxy-server-url>:<port>
```