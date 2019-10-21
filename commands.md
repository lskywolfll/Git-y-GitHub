
## git command --help y te mandara a la propia documentacion de git con el command respectivo para ver como funciona el funcionamiento de este

### Rastrear archivos
git add <file>

### Añadir todas las carpetas y archivos en la carpeta actual posiconada

git add .

### Para añadir el rastreo a archivos ya rastreados anteriormente y conjunto a un commit podemos usar, cabe destacar que solo funciona si son archivos de los cuales nosotros ya hemos rastreados(tracking)

git commit -am "mensaje"

### Estado del repositorio local(Indica que archivos no estan siendo rastreados)

git status

### Configuraciones de git

git config --list

### Ubicacion de las configuraciones de git que estan creadas y si queremos modificarlas ya podremos por saber su ubicacion exacta

git config --list --show-origin

### Mostrar los cambios realizados y sus diferencias

git show file

### Tambien podemos mostrar todos los cambios realizados a todos los archivos

git show

### Comparar versiones de acuerdo a la base y otra

git diff original modificado

git diff base Comparacion

ej: git diff 683fb35fd52070df689bcd410861c75a10b6d1ec c8cd36cd01360a50b676e6f992f35b58c55a4eed

## Comparando el origina con otra version
### muestra en verde la version original por terminal y en rojo los cambios actuales que hicimos en la otra version

## Comparando otra version con la original
### muestra en verde los cambios hechos en la version y en rojo la original

### Otro dato curioso es que si usamos simplemente

git diff

### Este nos motrara todos los cambios creados desde el ultimo rastreo hasta la ultima modificacion o agregacion de contenido como en una pagina web

ej: yo hice una modificacion despues de añadirlo al rastreo en una instancia de tiempo, uso git diff y me muestra exactamente que cambie de ese archivo o archivos

### Resumiendo, compara lo que tenemos en staging(preaprado) y lo que hicimos en el documento despues de dejarlo preparado(ya rastreado en una version con una serie de cosas ya creadas).

### Diferencias en el directorio actual(repo) y stating(preparado para enviar al repositorio)

### Revisar todos los commits creados hasta el dia actual

git log

### Volver a una version anterior

### Lo que hace es que nosotros volvemos a un punto de las versiones que tengamos en nuestro repositorio(local o remoto) y empezamos desde el punto en el cual nosotros queramos

git reset commit(hash)

### Tiene 2 tipos de reset

1- soft(suave)
2- hard(fuerte)

Lo que tengamos en stagin(preparado osea ya con commit y no en el repositorio) se guardara y el directorio de trabajo volvera al estado anterior indicado(commit)

Como se guarda entonces podremos volver al commit hecho despues de la version a regresar por ende tendremos una ayuda en caso lo hayamos hecho por equivocacion

<hash> Son los numeros en memoria que tiene asignado git al commit creado ej: 85ff8c0072a564e9 es mas largo en realidad

git reset --soft <hash>

Borra practicamente todo lo que se haya hecho anteriormente y queda como la master(principal) con la version asignada

git reset --hard <hash>

ej: git reset 85ff2c0072a564e9cb0eaa6567551e44ca977f87

### Otro dato curioso es el uso de sacar todos los archivos del area de preparacion(sin commit) sin borrarlos y mantener todo lo que se ha hecho con ellos e no se envien en el proximo commit que haremos.

 en caso nosotros queramos agregarlos nuevamente simplemente usaremos un git add

 git reset HEAD

### Nos muestra los cambios especificos en cuales archivos de acuerdo al commit

git log --stat

### Para volver un archivo a un commit especifico con los cambios respectivos a ese archivo usamos:

git checkout commit archivo.extencion

ej: git checkout c8cd36cd01360a50b676e6f992f35b58c55a4eed historia.txt

Por ejemplo si volvemos un archivo a un commit especifico y lo modificamos entonces luego de modificarlo lo añadimos al rastreo(tracking).

 hacemos un commit y luego cuando lo subamos al repositorio solo aparecera ese archivo modificado sin afectar a los demas archivos que podamos tendremos

### Para eliminar archivos de git(Rastreados o Tracking) sin eliminar el historial de cambios hechos en el de tal forma que en cualquier momento podemos volver a recuperar estos archivos desde el ultimo commit hecho antes de borrar el archivo en cuestion.

git rm <file>

### Para eliminar los archivos en el area de preparacion(Stagin) y del proximo commit pero manteniendolos en nuestro disco duro(Osea en memoria de nuestro equipo)

git rm --cached <file>

### Para eliminar los archivos rastreados por git y del disco duro

git rm --force <file>

### Git siempre resguardara todo lo que hagamos por lo cual podremos acceder al registro de existencia de los archivos de git(configuraciones y almacenamiento donde lo guarda) y recuperarlos si es necesario

### Recibir un cambio del repositorio remoto pero no te los copia con los archivos actuales(tu almacenamiento local) y para que obtengas los cambios necesitamos hacer un merge

git fetch -> Traer los datos nuevos que hay en el repositorio remoto

git merge -> Traspasar los cambios recibidor por el fetch y añadirlos a tus archivos o en su defecto agregar de los cambios hechos en el repositorio

### Crear una rama

git branch <nombre>

### Ver todas las ramas actuales que posee el repositorio

git branch -> Nombre de la cabecera actual estara marcada con * y color verde

### Migrar los cambios hechos de una rama a la rama actual

Si estoy en la rama master y le hago merge a otra rama distinta a la master estonces yo estaria trayendo a mi rama master los cambios realizado en el

git merge <rama>

NT: Si tenemos algun conflicto este nos marcara con el lugar llamado head y otro con el nombre de la ramma del cual estamos obteniendo el cambio.

luego de resolver los conflictos tenemos que rastrearlos nuevamente y como ya estaban rastreados usamos simplemente un git commit -am "Solucione el conflicto", listo entonces ya estaria la combinacion con la rama indicada :).

### Para agregar un servidor remoto el cual almacene nuestros archivos rastreados con git

git remote add <alias> <url> ej: git remote add origin <url>

### Enviar datos rastreados con git nuestros al servidor remoto

git push origin <rama>

Traer todos los cambios del servidor remoto a tu repositorio local con fecth y merge

git pull <NombreOrigen> <Rama>

Hacer una migracion al servidor remoto donde la historia es distinta, por ej: creamos un repositorio en git pero este tiene un commit ya dado por el readme y sin muchos commit como el local que tenemos.

En cuyo caso nos saldra un error que las historia son distintan cuando nosotros queramos hacer un push al servidor remoto.

Solucion

git pull <origin> <master> --allow-unrelated-histories
