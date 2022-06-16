##### Comandos
git config --global user.email "gnuxdar@gmail.com"
git config --global user.name "Arturo"
git config --global -e  (editor)
git config --global -l  (muestra lol guardado)
git config --list

1. git init

2. git add README.md

3. git commit -m "Mi primer Commit"

4. git add -A

5. git diff    (mestra todas la lineas alteradas)

6. git diff admin/funciones.php    (especifica las lineas que fueron alteradas en el fichero)

7. git remote add origin master httpt://github.com/gnuxdar/example.git

8. git push -u origin master

9. git commit --amend -m "New commit message"  Reescribe el utimo commit

10. git merge developer  (fusiona la rama que le indiquemos a la rama actual)

11. git log --decorate --all --graph --oneline  (muestra de manera mas grafica en la terminal)

12. cat my_proyecto/.git/config   (leer el fichero git para ver repositosio remoto o info)

13. git remote -v   (muestra a que repositorio esta ligado)

14. git log         (muestra los commit que se han hecho)

15. git log -p      (muestra el codigo del commit)

16. git reset --hard HEAD~1  (elimina el ultimo commit)

17. git reset --merge

18. git reset --hard

20. git reset --mixed <hash de commit a regresar>

21. git config --get remote.origin.url 	(muestra la url de nuestro repositorio)

22. git config --local -l 				(muestra la configuracion local)

23. git config --global -l 				(muestra la configuracion global)

24. git tag                             (lista los tag)

25. git tag 1.0.0 -m "version 1.0.0"

26. git checkout tag\_name              (Acceder al codigo asociado a ese tag)

27. git push origin 1.0.0               (hacer push al tag)

28. git config core.fileMode false		(Evita marcar todos los archivos como modificados al cambiar permisos.)


### Gitignore Si ya tienes un archivo registrado y quieres ignorarlo
Git no ignorará el archivo si agregas una norma más tarde. En esos casos, primero debes dejar de seguir el archivo, ejecutando el siguiente comando en tu terminal: En local $git rm --cached FILENAME

En Global $ git config --global core.excludesfile ~/.gitignore_global
También puedes crear un archivo .gitignore global, que consiste en una lista de normas para ignorar archivos en cada repositorio de Git de tu computadora. Por ejemplo, puedes crear el archivo en ~/.gitignore_global y agregarle algunas normas.

### Cambio de usuario en un repo
git config user.name "greboidw"
git config user.email gregorio@idw.com.pe


### Cambiar la url remota
git remote set-url origin https://gnuxdar@bitbucket.org/gnuxdar/cms_restaurant.git

### Ramas
 Cuando clonas un repositorio, toda la información de las sucursales se descarga, pero las sucursales están ocultas. Con el comando

	** $ git branch -a **

puede mostrar todas las ramas del repositorio, y con el comando

	** $ git checkout -b branchname origin/branchname **

 A continuación, puede "descargar" manualmente uno a la vez.

	** $ git checkout -b gnuxdar_agosto remotes/origin/gnuxdar_agosto **


git merge rama

 * branch            master     -> FETCH_HEAD
fatal: refusing to merge unrelated histories
fatal: rehusando fusionar historias no relacionadas

(solucion)
git pull --allow-unrelated-histories origin master  (cuando da el error de arriba, esto lo corrige, forza el pull)
ó
git merge development --allow-unrelated-histories

## Agregar de un repositorio remoto diferente a mi repo local
git remote add gilberto https://github.com/gilberto9312/eqsoft.git
git pull gilberto gnuxdar_github

git push -u gnuxdar_github rame

### Varios Repositorios en un mismo repo OJO git remote add [alias del repo que le pondremos "fork"] https://github.com/gilberto9312/eqsoft.git git checkout -b gnuxdar_github (para crear una rama desde la que ya existe "en caso de existir una") git checkout -t remotes/github/git_gnux_gil (descargar un arama del repo remoto)

los demas procesos iguales que anterior git add route/file.php git commit -m "messaje" git push fork (mi fork)

## Actualizar el fork desde el original git fetch [repo]/[rama]

    branch master -> FETCH_HEAD fatal: refusing to merge unrelated histories

git pull --allow-unrelated-histories origin master (cuando da el error de arriba, esto lo corrige, forza el pull)

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
