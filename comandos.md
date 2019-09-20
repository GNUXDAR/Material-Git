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
git merge developer  (fusiona la rama que le indiquemos a la rama actual)
git log --decorate --all --graph --oneline  (muestra de manera mas grafica en la terminal)
cat my_proyecto/.git/config   (leer el fichero git para ver repositosio remoto o info)
git remote -v   (muestra a que repositorio esta ligado)
git log         (muestra los commit que se han hecho)
git log -p      (muestra el codigo del commit)
git reset --hard HEAD~1  (elimina el ultimo commit)
git config --get remote.origin.url 	(muestra la url de nuestro repositorio)
git config --local -l 				(muestra la configuracion local)
git config --global -l 				(muestra la configuracion global)

#####Ramas
 Cuando clonas un repositorio, toda la información de las sucursales se descarga, pero las sucursales están ocultas. Con el comando

** $ git branch -a **

puede mostrar todas las ramas del repositorio, y con el comando 

** $ git checkout -b branchname origin/branchname **

 A continuación, puede "descargar" manualmente uno a la vez. 

** $ git checkout -b gnuxdar_agosto remotes/origin/gnuxdar_agosto **


From https://bitbucket.org/kodimrepo1/misahualli

 * branch            master     -> FETCH_HEAD
fatal: refusing to merge unrelated histories

git pull --allow-unrelated-histories origin master  (cuando da el error de arriba, esto lo corrige, forza el pull)

