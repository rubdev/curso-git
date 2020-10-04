# Control de versiones con GIT

Git se organiza en ramas, como un diagrama de árbol.

Se pueden tener una **estructura dividida en 4 ramas** principalmente:

- **Master** → código en producción.
- **Development** → es donde se integran las funcionalidades y se prueban antes de pasar a master.
- **Features** → ramas que contienen funcionalidades, creadas a partir de delopment.
- **Hotfix** → ramas para corregir errores en producción.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled.png)

## Github

GitHub es un sistema de gestión de proyectos y control de versiones de código, así como una plataforma de red social diseñada para desarrolladores.

## Clonar un repositorio

Podemos hacerlo de 2 formas.

### Por http usando nuestras credenciales.

Copiamos la url y en una terminal ejecutamos el comando `**git clone url-del-repositorio**`

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%201.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%201.png)

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%202.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%202.png)

### Con una clave SSH.

Para configurarla abrimos un terminal, ejecutamos el comando `**keygen-ssh**` y a continuación pulsamos enter, tanto al mensaje de directorio como al de contraseña.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%203.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%203.png)

Una vez generada, visualizamos la clave en el directorio que le hayamos indicado. El fichero que debemos abrir para ver la key es **id_rsa.pub**

La copiamos y nos dirigimos a Github → settings → ssh → new ssh key

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%204.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%204.png)

Indicamos el nombre y pegamos la key para finalizar la configuración.

Si queremos clonar deberemos seleccionar ssh y copiar la url.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%205.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%205.png)

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%206.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%206.png)

## Creación de ramas

Si abrimos git bash y nos movemos hasta nuestra carpeta del repositorio vemos la rama en la que estamos.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%207.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%207.png)

Para crear una rama local debemos ejecutar el comando → **`git checkout -b develop`**

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%208.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%208.png)

Para subir los cambios (en este caso la nueva rama) debemos de ejecutar el comando → `**git push —set-upstream origin develop**`

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%209.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%209.png)

## Ver cambios en el repositorio

Creamos una nueva rama feature.

Ahí **creamos un fichero**, por ejemplo → `**touch index.html**`

Para ver el estado, ejecutamos → `**git status**`

Podemos ver en rojo los archivos que git no está trackeando.

Si hiciesemos `**checkout**` a la rama develop y volviesemos a hacer `**git status**` veríamos que **sigue apareciendo ya que ese archivo aún no ha sido comiteado** en la rama original en el que se ha creado.

Si **modificamos** un archivo veremos como nos lo indica también con el comando `**git status`.**

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2010.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2010.png)

## Descartar cambios

**** Importante **** **Si descartamos un cambio no podremos recuperar estos cambios.**

Vamos a **descartar los cambios** al archivo modificado previamente. Para ello ejecutamos el comando → `**git checkout nombre-del-archivo**`

Si ahora hacemos `**git status**` vemos que ya no nos aparece en la lista de cambios.

Si queremos **descartar todos los cambios** debemos ejecutar → `**git checkout — .**`

## Commit

Para confirmar cambios sobre un archivo en git, **primero debe de estar siendo trackeado**. Para ello habrá que ejecutar el comando → `**git add nombre-del-archivo**` (Esto solo habrá que hacerlo la primera vez).

Si queremos **añadirlos todos** → `**git add**.`

Si ahora hacemos `**git status**` vemos los cambios preparados para ser confirmados.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2011.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2011.png)

**** Importante **** **Si queremos quitar algún archivo añadido a seguimiento (pendientes de commit) usar el comando `git restore —staged nombre-del-archivo`**

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2012.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2012.png)

Finalmente **para commitear los cambios** en los archivos ejecutamos → `**git commit -m "comentarios descriptivo sobre el cambio"**`

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2013.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2013.png)

Si hacemos `**git push origin nombre-rama**` se subirá la rama al repositorio de Github y podremos visualizar los cambios.

Si ahora cambiamos entre ramas vemos que el archivo commiteado ya solo aparece en la rama en la que ha sido confirmado.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2014.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2014.png)

## Archivo .gitignore

Es un archivo en el que podemos **indicar que archivos o tipo de archivos no queremos que sean versionados**, por ejemplo archivos .project, target, etc.

## Actualizar una rama con cambios remotos

**** Importante **** **Siempre deberíamos actualizarnos los últimos cambios antes de realizar un commit o push a la rama.**

Para hacer la prueba podemos subir un archivo directamente al repositorio en Github.

Puede que tengamos cambios en el repositorio remoto que nosotros no tengamos descargados.

Podemos consultar esto usando el comando → `**git fetch**`

Nos indica que hay algo nuevo.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2015.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2015.png)

El comando a ejecutar para **descargar lo cambios** más recientes en la rama remota → **`git pull`** 

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2016.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2016.png)

**** Importante ** Si intentamos hacer push con los cambios y tenemos archivos pendientes de descargar no vamos a poder realizar el commit. Git no sabe hacer el merge.**

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2017.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2017.png)

## Cómo ver las modificaciones de los archivos

Creamos un archivo nuevo y modificamos uno de los que tuviesemos.

Ejecutamos `**git status**` para ver el estado.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2018.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2018.png)

Ahora para **ver las diferencias** ejecutamos el comando → `**git diff nombre-del-archivo**`

En **rojo** veremos líneas **eliminadas**

En **verde** las **añadidas**.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2019.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2019.png)

Si lo hacemos con el archivo nuevo no funcionará, tiene que estar seguido por git.

## Guardar cambios con stash

Stash es increíblemente útil, **si estamos trabajando en nuestro código y necesitamos cambiar a otra rama** por cualquier motivo o quizás **hacer un pull en el repositorio, y no queremos hacer un commit de nuestro trabajo** por que se encuentra en un estado parcial, podemos usar stashing.

Para usarlo debemos ejecutar el comando → `**git stash`** 

Lo que hace es congelar nuestros cambios desde nuestro último commit y almacenarlos de forma temporal dejando nuestro directorio de trabajo completamente limpio.

Ahora podemos cambiar de rama trabajar un rato, hacer un pull y después de realizar nuestro trabajo, podemos volver a recuperar nuestros cambios.

Podemos **listar los stashes** almacenados con → `**git stash list**`

Para aplicar los stash guardados usamos el comando → `**git stash apply**`

## Revisar commits

Podemos revisar los commits (confirmaciones) realizadas sobre una rama o repositorio utilizando el comando → **`git log`**

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2020.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2020.png)

## Mover commits entre ramas

Si hacemos commit de un camio en una rama equivocada, podemos moverlo a otra rama.

Primero necesitamos el código del commit, este podemos obternlo haciendo **`git log`** y viendo el listado de confirmaciones.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2021.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2021.png)

Para mover el commit a otra rama con el código del commit copiado, primero debemos movernos a la rama en la que queremos volcar el commit con **`git checkout nombre-de-rama`** 

A continuación ejecutamos el comando → **`git cherry código-del-commit`**

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2022.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2022.png)

## Como eliminar un commit

**** Importante **** No es una buena práctica.

**** Importante **** Si el commit ya está en el repositorio remoto es preferible hacer otro commit que elimine o remplaze lo que necesitemos.

Está bien hacerlo si por ejemplo hemos realizado un commit y se nos ha olvidado algún archivo, o que hayamos commiteado alguna funcionalidad pendiente de terminar.

Modificamos y commit a un archivo.

Si sólo queremos eliminar el último commit pero no los cambios ejecutamos el comando → `**git reset head~1**`

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2023.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2023.png)

Si queremos eliminar el último commit y los cambios ejecutamos el comando → `**git reset —hard head~1**`

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2024.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2024.png)

## Crear, modificar y eliminar ramas con git branch

Este comando es otra forma de manejar ramas.

Nos movemos de nuevo a develop con `**git checkout develop**`

Para **crear una nueva rama** ejecutamos el comando → **`git branch nombre-de-rama`**

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2025.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2025.png)

Podemos **ver un listado de las ramas** disponibles con → **`git branch -l`**

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2026.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2026.png)

Podemos **renombrar una rama** ejecutando → `**git branch -m nombre-rama-anterior nombre-nueva-rama**`

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2027.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2027.png)

Para **eliminar una rama** usamos el comando → **`git branch -d nombre-rama`**

Debemos estar en una rama distinta a la que queremos borrar

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2028.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2028.png)

**** Importante **** Si teníamos cambios en esa rama confirmados no podremos borrar la rama, a no ser que lo forzemos con el comando `**git branch -D rama-con-cambios**`

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2029.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2029.png)

Solo eliminariamos las ramas en local, para eliminarla también en remoto vamos a crear una nueva y subirla al repositorio.

**Para eliminarla del repositorio remoto** ejecutamos → **`git push origin —delete nombre-rama`**

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2030.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2030.png)

## Como hacer merge

Este comando sirve para **fusionar (integrar) 2 ramas**. Una en la otra.

Esto **suele ocasionar conflictos**, cuando git no es capaz de mezclar ambas ramas.

**Si lo consigue hacer a la primera sin conflictos se le llama fast-forward.**

Para realizar un mergeo, nos vamos a crear una rama nueva y añadir uno nuevo archivo.

Ahora **para realizar el merge** primero **nos posicionamos en la rama destino** y a continuación ejecutamos el comando → **`git merge nombre-rama-a-mergear`**

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2031.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2031.png)

**** Importante **** Ahora vamos a **mergear ramas con conflictos**, es decir con algún archivo modificado (y commiteado) en ambas ramas. En este caso hemos modificado el mismo fichero en 2 ramas distintas.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2032.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2032.png)

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2033.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2033.png)

Para hacer un **merge manual** simplemente tenemos que **quedarnos con el resultado de lo que queramos en el fichero y commitearlo para salir del estado de merging**.

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2034.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2034.png)

![Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2035.png](Control%20de%20versiones%20con%20GIT%2053544d9aaaa74ed6834892647529313f/Untitled%2035.png)