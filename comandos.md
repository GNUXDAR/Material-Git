##### Comandos
git config --global user.email "gnuxdar@gmail.com"
git config --global user.name "Arturo"
git config --global -e  (editor)
git config --global -l  (muestra lol guardado)
git config -l ó git config --list


1. git init

2. git add README.md

3. git commit -m "Mi primer Commit"

4. git add -A ó git add .

5. git diff    (mestra todas la lineas alteradas)

6. git diff admin/funciones.php    (especifica las lineas que fueron alteradas en el fichero)
	 
7. git branch -M main

8. git branch -m <nuevo-nombre>      (cambiar el nombre de la rama, desde otra rama)

9. git remote add origin main httpt://github.com/gnuxdar/example.git

10.  git push -u origin main

11. git commit --amend -m "New commit message"  Reescribe el utimo commit

12. git merge developer  (fusiona la rama que le indiquemos a la rama actual)

13. git log --oneline --decorate --all --graph	(se ve la proicedencia de una rama)

14. git log --decorate --all --graph --oneline  (muestra de manera mas grafica en la terminal)

15. cat my_proyecto/.git/config   (leer el fichero git para ver repositosio remoto o info)

16. git remote -v   (muestra a que repositorio esta ligado)

17. git ls-remote origin	(lista todas las ramas remotas)

## log
18. git log         (muestra los commit que se han hecho)

19. git log -p      (muestra el codigo del commit)

20. git log -p <nombre-del-archivo>     (si solo quieres ver los cambios en un archivo específico en cada commit, puedes usar el siguiente comando)

21. git log <fichero>

22. git log --author="Arturo Cabrera"       (con username)

23. git log --author="gnuxdar@gmail.com"    (con email)

24. git log --author="TuNombre" --oneline --decorate --graph

25. git log --author="Arturo Cabrera" --since="2024-04-01" --until="2024-04-30" --format="%h - %s - %ad"

26. git log --merges      (ver el historial de fusiones (merges))

27. git blame <nombre-del-archivo>    (ver los cambios en un fichero especifico en cada commit)

28.	git revert <ID>		(Revertir algunas confirmaciones existentes)

29. git reset --soft HEAD~1  (elimina el ultimo commit)
    
30. git reset --hard HEAD~3 (elimina los ulimos 3)

31. git reset --hard HEAD~1  (elimina el ultimo commit)

32. git reset --merge

33. git reset --hard

34. git reset --mixed <hash de commit a regresar>

35. git config --get remote.origin.url 	(muestra la url de nuestro repositorio)

36. git config --local -l 				(muestra la configuracion local)

37. git config --global -l 				(muestra la configuracion global)

38. git tag                             (lista los tag)

39. git tag 1.0.0 -m "version 1.0.0"

40. git checkout tag\_name              (Acceder al codigo asociado a ese tag)

41. git push origin 1.0.0               (hacer push al tag)

42. git config core.fileMode false		(Evita marcar todos los archivos como modificados al cambiar permisos.)
		
42. git checkout -b nombreDeLaNuevaBranch	(crear un rama a partir de la rama actual)
		
44. git push --set-upstream origin nombreDeLaNuevaBranch		(subir al repo la rama nueva creada)
		
44. git commit -m "[UPD] this comment 				(Co Author del commit)
		
45. git branch -d rama-a-eliminar
		
47. git push origin --delete rc-acabrera      (Informar la eliminacion de la rama al repo)
		
# Rebase
48. git checkout --ours											(para conservar los cambios de tu rama local y descartar los de la rama remota.)
    
49. git checkout --theirs							(para conservar los cambios de la rama remota y descartar los de tu rama local.)
    
50. git rebase --abort 							(para volver al estado anterior al rebase.)
# ##################################################################################################################################
## generar SSH

## Verificar si hay llave privada generada y cargada en SSH
	ssh-add -l -E sha256
		ó 
	ssh-add -l -E sha256

## Verificar que la autenticación SSH funciona correctamente
	ssh -T git@epayco

### bitbucket.org
ssh -T git@bitbucket.org

## Comprobar que la llave se esta usando
	ssh -vT git@github.com

## Generar una nueva ssh (una existente)
	ssh-keygen -t ed25519 -b 4096 -C "username@emaildomain.com" -f ssh-key-name

## Configurar HOST en .ssh/config
Host github.com
	HostName github.com
	User git
	AddKeysToAgent yes
	IdentityFile    /home/gnuxdar/.ssh/epayco
IdentitiesOnly yes

## Configuracion para el Repositorio Especifico
	# Configuración para el repositorio personal
	Host github.com
		HostName github.com
		User git
		IdentityFile ~/.ssh/id_rsa

	# Configuración para el repositorio de trabajo
	Host work-repo
		HostName work.repo.com
		User git
		IdentityFile ~/.ssh/epayco.pub


## Configurar varios repositios con el mismo Host (ejm: Github.com)
user/.ssh/config


<!-- # Epayco
# Host github.com -->
Host epayco
	HostName github.com
	User git
	AddKeysToAgent yes
	IdentityFile    /home/gnuxdar/.ssh/epayco
IdentitiesOnly yes

<!-- # Gnuxdar
# Host github.com -->
Host gnuxdar
	HostName github.com
	User git
	AddKeysToAgent yes
	IdentityFile    /home/gnuxdar/.ssh/gnuxdar
IdentitiesOnly yes

<!-- # Stefanini
# Host bitbucket.org -->
Host stefanini
	HostName altssh.bitbucket.org
	User git
	AddKeysToAgent yes
	IdentityFile    /home/gnuxdar/.ssh/stefanini
	Port  443
IdentitiesOnly yes


### Comprobar las configuraciones SSH
	ssh -i /home/gnuxdar/.ssh/epayco -T git@github.com
	ssh -i /home/gnuxdar/.ssh/gnuxdar -T git@github.com

	ssh -T git@stefanini <!-- bitbucket-->

### Operaciones
<!-- Ahora, cuando quieras clonar o trabajar con el repositorio de Epayco, usarías: -->
git clone git@epayco:usuario/repo.git
<!-- y con el repositorio personal -->
git clone git@gnuxdar:usuario/repo.git
<!-- bitbucket -->
git clone git@stefanini:telefonica-peru/dev-ecommerce-tdp-bkp.git


<!-- Para realizar operaciones como push o pull, también necesitas ajustar tu configuración remota en tus repositorios locales. Puedes hacer esto utilizando los siguientes comandos: -->
<!-- Para un repositorio -->
git remote set-url origin git@epayco:usuario/repo.git
<!-- y par el repositorio personal -->
git remote set-url origin git@gnuxdar:usuario/repo.git
git remote set-url origin git@gnuxdar:GNUXDAR/lv_backend.git
<!-- Esto ajustará la URL remota (origin) para que apunte al host específico según la entrada que has definido en tu archivo ~/.ssh/config. Después de hacer estos cambios, deberías poder hacer push y pull sin problemas. -->

### NOTA
en el config del local el host y en el config del repo, el url deben ser igual. 
ejm: 
config local: Host gnuxdar
config repo: [remote "origin"]
	url = git@gnuxdar:GNUXDAR/lv_backend.git
	donde @gnuxdar es el host

### Gitignore Si ya tienes un archivo registrado y quieres ignorarlo
Git no ignorará el archivo si agregas una norma más tarde. En esos casos, primero debes dejar de seguir el archivo, ejecutando el siguiente comando en tu terminal: En local $git rm --cached FILENAME

Si quieres ignorar un archivo que has confirmado en el pasado, deberás eliminarlo de tu repositorio y, a continuación, añadirle una regla de .gitignore. Al usar la opción --cached con git rm, el archivo se eliminará del repositorio, pero permanecerá en tu directorio de trabajo como archivo ignorado.

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

# Error
### error: falló el empuje de algunas referencias a 'github.com:GNUXDAR/gnuxdar.git'
	git config --global user.email
	{ID}+{username}@users.noreply.github.com   -	git config user.email "6179849+GNUXDAR@users.noreply.github.com"
	git config --global user.email {ID}+{username}@users.noreply.github.com
	git commit --amend --reset-author
	git push

## Error GH007
 Contando objetos: 100% (96/96), listo. Compresión delta usando hasta 8 hilos Comprimiendo objetos: 100% (71/71), listo. Escribiendo objetos: 100% (73/73), 8.48 KiB | 1.70 MiB/s, listo. Total 73 (delta 27), reusados 0 (delta 0), pack-reusados 0 remote: Resolving deltas: 100% (27/27), completed with 14 local objects. remote: error: GH007: Your push would publish a private email address. remote: You can make your email public or disable this protection by visiting: remote: http://github.com/settings/emails To gnuxdar:GNUXDAR/lv_backend.git ! [remote rejected] main -> main (push declined due to email privacy restrictions) error: falló el empuje de algunas referencias a 'gnuxdar:GNUXDAR/lv_backend.git'

## Solucion a Error GH007
	git commit --amend --author="Arturo Cabrera <6179849+GNUXDAR@users.noreply.github.com>"

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



Co-authored-by: Arturo <gnuxdar@gmail.com>
Co-authored-by: Gregorio <grebodeveloper@gmail.com>"

[ssh-key](https://support.atlassian.com/bitbucket-cloud/docs/set-up-personal-ssh-keys-on-linux/#Start-the-SSH-agent)

# Problemas
Cuando inetentaaba hacer un pull mem daba erro o con push.

1. user/.ssh/know_hosts este fichero guarad una especie de log, si se elimina el contenido vuelve a solicitar acceso
2. user/.gitconfig   la configuracion de git
3. user/.ssh/config 