##### Comandos
git init
git add README.md
git commit -m "Mi primer Commit"
git add -A
git diff    (mestra todas la lineas alteradas)
git diff admin/funciones.php    (especifica las lineas que fueron alteradas en el fichero)
git remote add origin master httpt://github.com/gnuxdar/example.git
git push -u origin master
git commit --amend -m "New commit message"  Reescribe el utimo commit
git merge developer  (fusiona la rama que le indiquemos a la rama actual, developer es la que vamosa  fusionar)
git log --decorate --all --graph --oneline  (muestra de manera mas grafica en la terminal los commit de todas las ramas)
git log --decorate --graph --oneline        (muestra de manera grafica pero solo de la ramma actual)
cat my_proyecto/.git/config   (leer el fichero git para ver repositosio remoto o info)
git remote -v   (muestra a que repositorio esta ligado)
git log         (muestra los commit que se han hecho)
git log -p      (muestra el codigo del commit)
git reset --hard HEAD~1  (elimina el ultimo commit)
git config --get remote.origin.url 	(muestra la url de nuestro repositorio)
git config --local -l 				(muestra la configuracion local)
git config --global -l 				(muestra la configuracion global)

#####Gitignore
**Si ya tienes un archivo registrado y quieres ignorarlo, Git no ignorará el archivo si agregas una norma más tarde. En esos casos, primero debes dejar de seguir el archivo, ejecutando el siguiente comando en tu terminal:**
**En local**
$git rm --cached FILENAME

**En Global**
$ git config --global core.excludesfile ~/.gitignore_global
**También puedes crear un archivo .gitignore global, que consiste en una lista de normas para ignorar archivos en cada repositorio de Git de tu computadora. Por ejemplo, puedes crear el archivo en ~/.gitignore_global y agregarle algunas normas.**
#####Ramas
**Cuando clonas un repositorio, toda la información de las sucursales se descarga, pero las sucursales están ocultas. Con el comando**

** $ git branch -a **

puede mostrar todas las ramas del repositorio, y con el comando 

** $ git checkout -b branchname origin/branchname **

 A continuación, puede "descargar" manualmente uno a la vez. 

** $ git checkout -b gnuxdar_agosto(rama actual) remotes/origin/gnuxdar_agosto **

#####Varios Repositorios en un mismo repo OJO
git remote add [alias del repo que le pondremos "fork"] https://github.com/gilberto9312/eqsoft.git
git checkout -b gnuxdar_github  (para crear una rama desde la que ya existe "en caso de existir una")
git checkout -t remotes/github/git_gnux_gil     (desacrgar un arama del repo remoto)

los demas procesos iguales que anterior
    git add route/file.php
    git commit -m "messaje"
    git push fork (mi fork)

#Actualizar el fork desde el original
    git fetch [repo]/[rama]

 * branch            master     -> FETCH_HEAD
fatal: refusing to merge unrelated histories

git pull --allow-unrelated-histories origin master  (cuando da el error de arriba, esto lo corrige, forza el pull)

##############################################################

    1. Creamos una rama basada en otra
    2. Trabajamos en la nueva rama
    3. Guardamos los cambios
    4. Nos ubicamos en la rama que queremos unir los cambios
    5. Fusionamos los cambios

O lo que es lo mismo:

    1. git checkout -b feature
    2. Realizamos los cambios pertinentes
    3. git commit -m “feature realizada”
    4. git checkout master
    5. git merge feature

También podemos hacer un sexto paso que es la eliminación de la rama que fusionamos pues ya no la necesitamos. Esto se hace con: git branch -d rama-a-eliminar, es decir, para nuestro caso: git branch -d feature.