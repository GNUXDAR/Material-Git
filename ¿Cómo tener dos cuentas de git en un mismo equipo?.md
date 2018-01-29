##Para firmar los commits como distintos usuarios

Cuando uno empieza a trabajar con git, en algún momento fija su configuración global de nombre y correo
```
git config --global user.name "Santiago Muñoz"
git config --global user.email santiago@email.com
```

La implicancia que tiene esto es que todos los commits que hagas en el equipo quedarán asociados a ese email, a quien se atribuye la autoría del commit. 
Es posible configurar un email y nombre distinto para cada repositorio. Si tú te paras en la raíz de tu copia local y pones
```
git config user.name "Santiago M."
git config user.email sm@email.com
```

Esa configuración pisa la configuración global para ese repositorio en particular.
Todo lo que he indicado hasta ahora guarda relación con el email al cual se atribuye la autoría del commit, que no tiene ninguna relación con la cuenta de github que se utilice para interactuar con el remoto via pull/push.

###Para identificarse como distintos usuarios al interactuar con el remoto

Para esto último, si el remoto de un repositorio está apuntando a la url https, por ejemplo

```
https://github.com/jquery/jquery.git
```

Entonces cualquier push o pull pedirá ingresar usuario y contraseña, por lo cual es trivial identificarse con una cuenta u otra.

Si el repositorio está apuntando a la dirección ssh del repo, por ejemplo
```
git@github.com:jquery/jquery.git
```

Entonces espera que te autentifiques con una llave. El comportamiento por defecto al conectarse a git@github.com es probar todas las llaves cargadas en tu sesión hasta que una funcione, pero la manera correcta de hacerlo es definir tú mismo qué llave usar en tu archivo ```~/.ssh/config ```al estilo

```
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/santiago
```

Y aquí viene el problema. Si ambos repos están en el mismo hostname (todos, mal que mal, empiezan con github.com) no hay cómo especificar más llaves.

Peeeero, [hay un truco para usar llaves distintas.](https://stackoverflow.com/questions/3225862/multiple-github-accounts-ssh-config)  Se basa en que todos los subdominios de github en realidad apuntan al mismo dominio, por lo que tú podrías definir tu remoto como

```
git@subdominio.github.com:jquery/jquery.git
```

Y funcionaría igual. Hecho ese cambio en todos tus repositorios que quisieras asociar a esta segunda llave, añadirías a tu ``` ~/.ssh/config```

```
Host subdominio.github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/santiago2
    ```

Y con eso las interacciones con los repos cuyo remoto empiece con subdominio.github.com usarían la segunda llave.

Estracto sacado de [stackoverflow](https://es.stackoverflow.com/questions/59293/c%C3%B3mo-tener-dos-cuentas-de-git-en-un-mismo-equipo)

:alien: Probado y funciona  :+1:

Comentame como te fue [Twitter](https://twitter.com/Gnuxdar/)
 