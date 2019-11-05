# Hyperblog 💚
Un blog increíble para el[ curso de Git y Github](https://platzi.com/cursos/git-github/ " curso de Git y Github") de [Platzi](https://platzi.com/ "Platzi")
> El curso de Git y Github de Platzi es lo que me hacía falta para triplicar mi salario y lanzarme a la industria del tejido de lana sintética con Machine Learning
> - niñita

## En este curso vemos de todo
* Todos los comandos de git
* El flujo de trabajo en github
* El verdadero amor por las buenas practicas
* Trucos muy locos del profesor
* Las personalidades multiples de Freddy
* Creado por el increble Platzi Team
* Incluye ejemplo en Windows, Linux y Mac
* Disponible para todas las edades

## git command --help y te mandara a la propia documentación de git con el command respectivo para ver cómo funciona el funcionamiento de este

### Crear un repositorio local con git para rastrear los cambios de los archivos

`git init`

### Rastrear archivos

`git add file`

### Añadir todas las carpetas y archivos en la carpeta actual posicionada

`git add .`

### Para añadir el rastreo a archivos ya rastreados anteriormente y conjunto a un commit podemos usar un commit, cabe destacar que solo funciona si son archivos de los cuales nosotros ya hemos rastreados(tracking)

`git commit -am "mensaje"`

### Estado del repositorio local(Indica que archivos no están siendo rastreados)

`git status`

### Configuraciones de git

`git config --list`

### Ubicación de las configuraciones de git que están creadas y si queremos modificarlas ya podremos por saber su ubicación exacta

`git config --list --show-origin`

### Mostrar los cambios realizados y sus diferencias

`git show file`

### También podemos mostrar todos los cambios realizados a todos los archivos

`git show`

### Mostrar las ramas que existen y sus historias

`git show-branch`

### Mostrar todas las ramas conjunto a mas detalles que el anterior

`git show-branch --all`

### Comparar versiones de acuerdo a la base y otra

`git diff original modificado`

`git diff base Comparación`

> `ej: git diff 683fb35fd52070df689bcd410861c75a10b6d1ec c8cd36cd01360a50b676e6f992f35b58c55a4eed`

## Comparando el original con otra versión
### muestra en verde la versión original por terminal y en rojo los cambios actuales que hicimos en la otra versión

## Comparando otra versión con la original
### muestra en verde los cambios hechos en la versión y en rojo la original

### Otro dato curioso es que si usamos simplemente

`git diff`

### Este nos mostrará todos los cambios creados desde el último rastreo hasta la última modificación o agregación de contenido como en una página web

ej: yo hice una modificación después de añadirlo al rastreo en una instancia de tiempo, uso git diff y me muestra exactamente que cambie de ese archivo o archivos

### Resumiendo, compara lo que tenemos en staging(preparado) y lo que hicimos en el documento después de dejarlo preparado(ya rastreado en una versión con una serie de cosas ya creadas).

### Diferencias en el directorio actual(repo) y stating(preparado para enviar al repositorio)

### Ver que cambios has hecho cuando ya preparaste un commit

`git diff --cached`

### Ver las diferencias mediante un programa,vim,araxis,emerge y etc

`git difftool`

#### Para saber que tienes disponible en tu sistema mediante la herramienta

`git difftool -tool-help`

### Revisar todos los commits creados hasta el dia actual(No todos los cambios)

`git log`

### Revisar los cambios de los archivos de los commits

`git log -p`

### Establecer la cantidad de historial para ver la historia

`git log -x`

> ej: `git log -2` me dara los ultimos 2 commits y registros

### Revisar todos los cambios hechos historicamente por todos en el repositorio

`git log --all`

### Revisar todos pero con grafos visual

`git log --all --graph`

### Revisar todos los cambios con grafos y de manera comprimida

`git log --all --graph --decorate --oneline`

### Crear un alias en terminal linux(windows=gitbash o bash(linux subsystem))

`alias nombre="comando que tu quieras"`

`alias arbolito="git log --all --graph --decorate --oneline"`

### Volver a una versión anterior

### Lo que hace es que nosotros volvemos a un punto de las versiones que tengamos en nuestro repositorio(local o remoto) y empezamos desde el punto en el cual nosotros queramos

`git reset commit(hash)`

### Tiene 2 tipos de reset

1. soft(suave)
2. hard(fuerte)

Lo que tengamos en staging(preparado osea ya con commit y no en el repositorio) se guardará y el directorio de trabajo volverá al estado anterior indicado(commit)

Como se guarda entonces podremos volver al commit hecho después de la versión a regresar por ende tendremos una ayuda en caso lo hayamos hecho por equivocación

### hash Son los números en memoria que tiene asignado git al commit creado ej: 85ff8c0072a564e9 es mas largo en realidad

`git reset --soft hash`

### Borra prácticamente todo lo que se haya hecho anteriormente y queda como la master(principal) con la versión asignada

`git reset --hard hash`

> `ej: git reset 85ff2c0072a564e9cb0eaa6567551e44ca977f87`

### Otro dato curioso es el uso de sacar todos los archivos del area de preparacion(sin commit) sin borrarlos y mantener todo lo que se ha hecho con ellos e no se envien en el próximo commit que haremos.

 en caso nosotros queramos agregarlos nuevamente simplemente usaremos un git add

 `git reset HEAD`

### Nos muestra los cambios específicos en los archivos de acuerdo al commit

`git log --stat`

### Para volver un archivo a un commit específico con los cambios respectivos a ese archivo usamos:

`git checkout commit archivo.extensión`

> `ej: git checkout c8cd36cd01360a50b676e6f992f35b58c55a4eed historia.txt`

>>Por ejemplo si volvemos un archivo a un commit específico y lo modificamos entonces luego de modificarlo lo añadimos al rastreo(tracking).

 >>>hacemos un commit y luego cuando lo subamos al repositorio solo aparecera ese archivo modificado sin afectar a los demás archivos que podamos tendremos

### Estar en una rama distinta al master y obtener todos sus archivos

`git checkout rama`

### Para eliminar archivos de git(Rastreados o Tracking) sin eliminar el historial de cambios hechos en él de tal forma que en cualquier momento podemos volver a recuperar estos archivos desde el último commit hecho antes de borrar el archivo en cuestión.

`git rm file`

### Para eliminar los archivos en el area de preparación(Stagin) y del próximo commit pero manteniéndolos en nuestro disco duro(Osea en memoria de nuestro equipo)

`git rm --cached file`

### Para eliminar los archivos rastreados por git y del disco duro

`git rm --force file`

### Git siempre resguardara todo lo que hagamos por lo cual podremos acceder al registro de existencia de los archivos de git(configuraciones y almacenamiento donde lo guarda) y recuperarlos si es necesario

### Recibir un cambio del repositorio remoto pero no te los copia con los archivos actuales(tu almacenamiento local) y para que obtengas los cambios necesitamos hacer un merge

> git fetch -> Traer los datos nuevos que hay en el repositorio remoto

> `ej: git fetch origin master`

Esto nos traera algo llamado FETCH_HEAD(apunta a la cabeza actual(rama)) y tendremos que hacer un merge a el con:

`git merge FETCH_HEAD`

> git merge -> Traspasar los cambios recibidor por el fetch y añadirlos a tus archivos o en su defecto agregar de los cambios hechos en el repositorio

### Crear una rama

`git branch nombre`

### Ver todas las ramas actuales que posee el repositorio

`git branch -> Nombre de la cabecera actual estará marcada con * y color verde`

### Eliminar una rama

`git branch -D < rama >`

### Migrar los cambios hechos de una rama a la rama actual

Si estoy en la rama master y le hago merge a otra rama distinta a la master entonces yo estaría trayendo a mi rama master los cambios realizado en el

`git merge rama`

NT: Si tenemos algún conflicto éste nos marcará con el lugar llamado head y otro con el nombre de la rama del cual estamos obteniendo el cambio.

luego de resolver los conflictos tenemos que rastrearlos nuevamente y como ya estaban rastreados usamos simplemente un git commit -am "Solucione el conflicto", listo entonces ya estaría la combinación con la rama indicada :).

### Para agregar un servidor remoto el cual almacene nuestros archivos rastreados con git

`git remote add alias url ej: git remote add origin < url >`

### Servidores remotos externos para mantener actualizado el fork que nosotros hagamos(Es como tener su master en otro alias para estar actualizado ya que por defecto no es nuestro repositorio y no nos lo traera e avisara)

`git remote add upstream(Es un estandar pero es opcional ya que solo es un alias) < url >`

### Listado de servidores remotos

`git remote -v`

### Enviar datos rastreados con git nuestros al servidor remoto

`git push origin rama`

### Enviar datos de manera forzada al servidor remoto

`git push --force origin master`

### Traer todos los cambios del servidor remoto a tu repositorio local con fecth y merge

`git pull NombreOrigen Rama`

### Hacer una migración al servidor remoto donde la historia es distinta, por ej: creamos un repositorio en git pero este tiene un commit ya dado por el readme y sin muchos commit como el local que tenemos.

En cuyo caso nos saldrá un error que las historia son distintas cuando nosotros queramos hacer un push al servidor remoto.

#### Solución

`git pull origin master --allow-unrelated-histories`

### Crear una llave privada con ssh

-t -> indicar el algoritmo de encriptado
-b -> Indicar la cantidad de complejidad de la clave
-C -> Correo electronico al que estara conectada esta llave en este caso el de github

`ssh-keygen -t rsa -b 4096 -C "renealejandrosanchezmorales@gmail.com"`

NT:

Se puede agregar un passphrase(una frase adicional con espacios) para asi hacer aun mas segura tu conexion 

En la carpeta alojada de la llave ssh tendremos un archivo sin extension(llave privada) y otro con extension .pub(llave publica)

### Revisar que el servidor de ssh este activado y que tus llaven esten corriendo para establecer conexiones (linux y windows)

`eval $(ssh-agent -s)`

### Agregar tu llave privada para que quede registrada en el sistema para usarla

~ -> Indicar el home(osea a tu usuario) 
.nombre -> Archivo oculto

`ssh-add ~/.shh/llavePrivada`

> `ej: ssh-add ~/.ssh/id_rsa`

### Mac

#### Todo lo anterior pero se debe hacer:

Dentro de la carpeta ssh tendremos otro archivo con known_host

Evaluar si esta corriendo y encender

`eval "$(ssh-agent -s)"`

Si son versiones avanzadas como el 11, debes agregar un config en la carpeta del ssh y guardarlo sin extensión

`Host *
		AddKeysToAgent yes
		UseKeychain yes
		IdentityFile ~/.ssh/id_rsa`

luego :

`ssh-add -K ~/.ssh/id_rsa`


### Cambiar la url de un servidor remoto

`git remote set-url < Alias > < url >`

> `ej: git remote set-url origin < urlRepo >`

### Agregar un tag o mensaje respectivo a la version de nuestro proyecto por ejemplo

a -> Agregar
m -> Mensaje

`command: git tag -a (v0.1 o v1.0 o v2.0 y etc) -m "Mensaje" hash(ej: 103627d)`

`git tag -a v0.1 -m "Resultado de las primeras clases del curso" hash(commit)`

### Lista de todos los tags por su valor osea su nombre dejado

`git tag`

### Listado de todos los tags, quien lo hizo, el commit al que se le asigno

`git show-ref --tags`

### Subir los tags para que se vean en github de manera visual

`git push origin --tags`

### Borrar un tag de manera local

d -> Eliminar

`git tag -d tag`

`git tag -d dormido`

### Borrar un tag en el servidor remoto(GitHub) 

`git push origin :refs/tags/tag(nombre del tag)`

### Abrir una interfaz visual por terminal

`gitk`

### Pull Request(github), push request(bitbucket), merge request(gitlab)

Tiempo de resolver problemas con los proyectos mayormente se crearan ramas para estos tipos de casos ej:

1. git branch fix-typo
2. git checkout fix-typo

#### Luego de solucionar el problema:

1. `git add < files > o si estan ya rastreados todos los archivos y solo modificaste entonces git commit -am "mensaje"`

#### Mandar la rama al servidor remoto

2. `git push origin fix-typo`

Para poder administrar estas soluciones o caracteristicas nuevas en github se debera hacer:

1. Hacer un pull request(Te saldra por defecto cuando se suba la rama en github donde te dira compara o traer el requirimiento)

2. Agregar parte del equipo para que hagas un code review(Revisar el codigo) para poder estar seguros que no tendra ningun error o arreglar algun detalle

3. Parte del equipo puede llegar a exigir algunos cambios en la solucion u caracteristica nueva a ser publicada en produccion

4. Siempre se debe respetar a la persona encargada de hacer el merge en los pull request para tener un control para que no se vaya a subir cualquier cosa

5. Luego del merge, Borrar(opcional) la rama la cual solucio el problema o creada la caracteristica nueva dependiendo como se este implementando este tipo de cosa, cada equipo puede borrar o no borrarlo

### Proximamente cuando use gitlab y bitbucket se integrara la forma de hacerlo aun que probablemente sea muy muy similar a lo que hemos hecho o exactamente lo mismo

### Git Rebase (Pegar historias de otra rama a la propia)
> ej: Yo quiero pegar lo de la rama experimento a la rama master, entonces master tendra toda la historia y en los registros se vera como si master siempre haya tenido estos cambios

`git rebase < rama >`

1. Primero rebase a la rama del cual hemos modificado desde otra rama donde tenemos modificado el contenido ej: de experimento a master(del cual modificamos un archivo)
2. Al final rebase desde esa rama la cual modificamos en otra rama donde agregamos contenido o codigo ej: rebase de experimento a master

1. Dentro de la rama experimento `git rebase master `
2. Dentro de la rama master para pegar lo que hicimos en esperimento `git rebase experimento`

> Tener en mente que el primer paso es hacer un rebase en la rama de la cual quieres pegar a otra ej: experimento es el primero en hacer un rebase a master para pegarle su historia y luego master hara el rebase a experimento

>> Cosas locas que puedes hacer para pegar historias a otra rama sin que en principio se hayan desarrollado en el

>>> ES una pesima practica hacer esto en servidores remotos y solo debe usarse de manera local ya que si se usa en remoto habria un desmadre de la que ni te imaginas

>>>> Otro punto luego usas git branch -D < rama > para eliminar para siempre y dejar a la master con toda la historia sin dejar registros de nada.... terrorifico

[Beneficios sobre el rebase para ciertos aspectos](https://www.atlassian.com/git/tutorials/merging-vs-rebasing "Beneficios sobre el rebase para ciertos aspectos")

> rinaplata
>> Git rebase básicamente lo que hace es recopilar uno a uno los cambios confirmados en una rama, y reaplicarlos sobre otra. Utilizar rebase nos puede ayudar a evitar conflictos siempre que se aplique sobre commits que están en local y no han sido subidos a ningún repositorio remoto. Si no tienen cuidado con esto último y algún compañero utiliza cambios afectados, seguro que tendrá problemas ya que este tipo de conflictos normalmente son difíciles de reparar.

> [Oscar Callisaya](https://platzi.com/@oreynaldocl/ "Oscar Callisaya")
>> Aquí difiero completamente, aunque estoy de acuerdo en:

* Es una mala practica, siempre y cuando se haga rebase de una rama compartida, que mas de 1 developer lo trabaje.

* Es costosa, ya que el developer tiene que resolver conflictos en X commits y depende de los conflictos es tedioso. En caso de merge sin rebase, el conflicto se resuelve una vez.

* Agrega un step extra al proceso.

Ahora doy mis razones de por que me gusta el rebase:

* Primero admito que fue el primer proceso que use en el trabajo, y es un poco sentimental.

* Crea una claridad tremenda de los features. Si trabajamos con feature branching, cada rama mergueada luego de un rebase crea un trazo claro. 

* Ejemplo, el proyecto que dejo como imagen final.

* Se da responsabilidad al developer de actualizar siempre su rama al ultimo cambio, se corre test de integracion (al menos sanity tests).

Aquí mi ejemplo, como ven se ve claramente las ramas y que cambios tiene cada bloque, cosa que en un grafo donde solo se hace mergue es confuso. Los commits de merge, muestran el total de archivos modificados y sus cambios.

![](https://i.ibb.co/9w6rrsn/Rebase-Examples.png)

Es decisión de cada equipo, y al menos en el que yo trabajo, pues es una practica muy util que nos ayuda mucho en el proces.

### Guardar cambios de manera temporal

`git stash`

### Escoger que archivos guardar temporalmente y ver los cambios hechos

`git stash --patch`

### Lista de los cambios guardados en un espacio temporal

`git stash list`

> stash@{0}: WIP on master: 581f390 Se agregan breves ejemplos

### Traer tus cambios guardados de manera temporal

`git stash pop`

> Traera el ultimo stash hecho

### Eliminar los archivos guardados temporales

`git stash drop`

> Borrar uno en espefico `git stash drop stash@{0}`

### Guardar cambios temporales en una nueva rama

`git stash branch < nombre >`

### Aplicar un cambio guardado temporal especifico

`git stash apply stash@{0}`

> el 0 varia de los guardados temporales que estes haciendo

### Reaplicar cambios almacenados

`git stash apply --index`

### Guardar temporalmente archivos exceptuando los rastreados con git add

`git stash --keep-index`

### Ver que cambios se han hecho,creado,modificado,eliminado y el nombre del archivo

`git status -s`

### Guardar temporalmente archivos no rastreados y rastreados

#### Formas

1. `git stash --include-untracked`
2. `git stash -u`

### Guardar temporalmente todo

`git stash --all`

>Git clean no eliminara lo que se haya dejado en .gitignore

### Ver que archivos borraras para limpiar el proyecto de archivos inncesarios(compilados,copias,sin rastrear y etc)

`git clean --dry-run`

### Limpiar todos los archivos y subcarpetas

`git clean -f -d`

### Verificar que eliminara y carpetas

`git clean -d -n`

### Eliminar archivos incluyendo lo que salga del gitignore(cuidado)

`git clean -n -d -x`

### Eliminar de manera interactiva y decidir por cada archivo

`git clean -x -i`

> -i es interactive para poder interactuar con el procedimiento

### Combinar un commit externo a una rama

`git cherry-pick < hash >`

> ej: git cherry-pick da86b3b

### Ver todo el flujo de todo lo que se ha hecho en el repositorio local

`git reflog`

>No se le puede ocultar nada y es el poseedor de la ultima palabra!! 🐱‍👤

### Agregar cambios a un commit anterior que te faltaban cosas por agregar(no enviado aun al servidor remoto)

1. `git add .`
2. `git commit --amend`

### Buscar archivos que contengan un valor

> Es case sensitive, el valor que le dejemos lo buscara tal cual lo hayamos dejado ej: Platzi != platzi

`git grep < valor >`

> ej: `git grep color` y me buscara en todos los archivos que lo tengan

#### Curiosos:
* `git grep -n < color >` nos dira en que linea del archivo aparece la palabra color
* `git grep -c` nos dira cuantas veces se repite esta palabra y en que archivo

> Si queremos saber cuantas veces usamos una etiqueta html usamos: `git grep "<p>"`

### Buscar commits que contengan o estuvo involucrado algo

`git log -S "nombre"`

### Cuantos commits han hechos cada integrante del repositorio

`git shortlog`

#### Mostrar la cantidad de commits han hecho cada uno

`git shortlog -sn`

#### Mostrar cantidad total de todos los commits

`git shortlog -sn --all`

#### Mostrar la cantidad total de commits exceptuando los merge

`git shortlog -sn --all --no-merges`

### Crear un alias de git en la maquina que estes

`git config --global alias.nombre "comando"`

>ej: `git config --global alias.nombre "shortlog -sn --all --no-merges"`

### Quien hizo quien y cada linea de un archivo especifico

`git blame < archivo.extension >`

>ej: `git blame blogpost.html`

#### Identacion un poco mejor

`git blame -c < archivo >`

### Ver los cambios que se hiciero y quien lo hizo desde el archivo x y desde las lineas x

`git blame < ruta del archivo > -L inicio,fin`

>ej: ``git blame css/estilos.css -L 35,53` desde la linea 35 hasta la linea 53

### Ver las ramas remotas

`git branch -r`

### Ver todas las ramas (blancas => local y rojas => remoto)

`git branch -a`