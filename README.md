# apuntes_git_hub
Mis apuntes en clases de Git y Hub

---

# CLASE #2

---

## ¿Para que sirve Git?

Git es un controlador de versiones para poder trabajar en los proyectos, sirve
también para poder trabajar en equipo. Antes habían muchos problemas para 
poder gestionar las versiones de proyectos y en la mayoria daban errores, 
cuando surgió git, fue implementado de inmediatamente. 

---

## Conceptos Generales de Git

1. **Repositorios**: Git se maneja con repositorios, los cuales son la carpeta donde
se aloja el proyecto. Cada desarrollador cuenta con una copia en su maquina local
del repositorio original el cual puede trabajar.

2. **Staging**: Son los archivos que git les hace seguimiento pero que no los guarda
en el área de control de versiones, se pueden comparar, editar, quitar y poner. Es
como un limbo, donde git le hace seguimiento pero que no guarda en las versiones 
definitivas.

3. **Ramas**: Son lineas de desarrollo independiente del cual puedes trabajar y si
deseas unirlas al proyecto original, en caso que no puede surgir un proyecto 
totalmente nuevo. 

4. **Arbol**: Cuando un proyecto es muy amplio, puede tener un arbol de versiones,
donde cada rama es independiente de la otra, al final la mirada general de las ramas
se vuelve un arbol. 

5. **Commits**: Son los cambios guardados de una rama en el proyecto. 

6. **Merge**: Es combinar dos ramas o muchas más en una sola. 

7. **Head / Puntero**: Una etiqueta que apunta al último commit de un proyecto 
o una rama. Puedes cambiar el puntoro con otros comandos, es como la etiqueta
de la versión definitiva. 

---

## Pasos fundamentales para usar Git:

Para poder usar git, tenemos que instalarlo, por defecto en linux ya viene 
instalado. Una vez instalado tenemos que configurar el programa para poder usarlo
de la mejor manera:

1. **Rama**: Antes por defecto se trabajada con el nombre de la rama "master", hoy
en día se trabaja con el nombre "main". Para cambiar por defecto el nombre de la 
rama usa el siguiente comando:

`git config --global init.defaultBranch main`

Puede que no aparezca ningun cambio en la pantalla de la terminal, pero el comando
se ha ejecutado con éxito. 

2. **Nombre**: Cuando se realiza algún cambio en algún proyecto es importante saber
quien lo ha hecho. Para esto configura el nombre de manera global con el siguiente 
comando:

`git config --global user.name "<name>"`

Cambia las `<>` por tu nombre, o nombre de usuario. 

3. **Correo**: Cuando se realiza algún cambio en algún proyecto es importante 
saber quien es y su correo para poder contactar a la persona. Para esto configura el
correo de manera global con el siguiente comando:

`git config --global user.email "<email>"`

Cambia las `<>` por tu correo electronico de trabajo. 

4. **Verificación**: Una vez terminado este proceso, verifica que tus datos se 
encuentran de la manera correcta, en caso que no, vuelve a escribir los comandos
y cambia la información por la correcta. Comando para verificar:

`git config --list`

**NOTA**: si tienes alguna duda sobre un comando, puedes buscar la documentación 
oficial de git, o también, usar este comando que te da una pequeña explicación 
de los comandos:

`git --help`

## ¿Cómo comenzar a usar Git en tu proyecto?

Una vez configurado tu git, puedes ir crear un repositorio y luego iniciar el 
comando:

`git init`

Con ese comando se inicia git y así poder empezar con el control de versiones.

Lo que hace Git, es crear una carpeta oculta llamada .git, para poder ver la 
carpeta, puedes usar el comando en la terminal `ls -a` para poder ver todos
los archivos ocultos del repositorio donde se aloja tu proyecto. 

---

# CLASE #3

---

## Comandos Básicos de Git: add, commit y luego

Para comenzar, tenemos unos cuantos comandos básicos y un concepto fundamental para
trabajar con git. 

1. **Estado del Repositorio**: Para poder saber el estado actual del repositorio y
el estado de los archivos, usa el siguiente comando:

`git status`

Con este comando puedes saber el "Estado Actual" de lo que hace git con cada archivo
del repositorio. Vas a ver que una vez agregado los archivos en el area de Staging,
si se encuentra modificado, si git le hace seguimiento o no, o si ya todo está en
el control de versiones guardado, no verás nada. 

También te muestra si algún archivo ha sido creado o eliminado. 

2. **Area Staging**: Para poder subir un archivo al control de versiones y guardarlo
primero tenemos que subir lo al área de "Staging". Se hace con el siguiente comando:

`git add <file>`
`git add .`

Cuando usas el primer comando, cambia el nombre las `<>` por el nombre del archivo.
Cuando usas el segudon comando agrega todos los archivos que tengas en el 
repositorio, incluídos los que están en otras sub carpetas. 

Bueno y ¿qué es el Area Staging? Esta área es super importante comprender la, pues
es cuando git sube los archivos para hacerles seguimiento pero no los guarda en el 
sistema de versiones. Aquí, puedes subir el archivo, si te encuentras seguro de 
ponerlo como una versión le haces un commit, sino, lo retiras o lo modificas. 

Es como estar en un limbo, están en el área de preparación. Los archivos que no se
han agregado a Staging, git solo los indentifica pero no les hace un seguimiento. 

3. **Eliminar Archivos del Staging Area**: Para eliminar un archivo del Staging area
usa el siguiente comando: 

`git rm --cached <name>`

Cambia el nombre las `<>` por el nombre del archivo. Este comando, lo podemos usar
cuando subimos un archivo con `git add` pero ya no queremos subirlo al sistema de 
versiones. Simplemente lo retira del área de preparación. 

**NOTA**: En todo este proceso puedes usar `git status` para ver el estado de los
archivos y lo que está haciendo git.

4. **Guardar en el Sistema de versiones**:

Cuando ya quieras guardar el o los archivos en el sistema de versiones usar el 
siguiente comando:

`git commit -m "mesaje"`

Cuando ya tengas los archivos listos en el "Staging area", puedes guardar los como
una versión del repositorio, del proyecto, usa este comando, es importante, siempre
cambiar "mensaje" por un texto descriptivo de lo que has hecho en el proyecto. 

Recomiendo escribir detalladamente tus cambios y no hacer commits tan largos, sino
pequeños. 

5. **Historial de Versiones**:

Para saber el historial de versiones de los commits, de tus versiones guardadas usa
el comando: 

`git log`

Te va mostrar todas las veriones, con su respectivo indentificador, fecha, nombre y
correo de la persona y el texto del commit con que fue hecho.

**NOTA**:

1. Recuerda siempre usar `git status` para saber que está pasando con los archivos
en git.
2. Cuando usas `git log` muestra el historial por defecto del último al primer 
commit.

---

# CLASE #4

## Ramas y Funsión de Cambios: Branch, Merge, Switch y Checkout

Las ramas son muy útiles e importantes para el trabajo colaborativo en un 
proyecto por las siguientes razones:

1. Puedes trabajar en tu propia rama sin la necesidad de chocar con el trabajo
de otra persona. 
2. En caso que no te guste tu trabajo puedes hacer un reset y eliminar tu rama
para comenzar desde cero con otra. 
3. Todo lo que hagas en tu rama, ninguna otra persona lo va a ver, en tu rama
puedes hacer lo que sea.
4. Todos los archivos nuevos que creas y las modificaiones que hagas en una rama,
solo se quedan en esa rama y no se van a ver reflejados en otras ramas.  


**NOTA**:

1. Cuando haces merge, es decir combinas tu rama a la rama principal todo el 
historial de commits se va a reflejar en la rama principal. 
2. Cuando ya termines tu trabajo y hagas merge, elimina tu rama, pues esa rama
ya no tiene sentido para existir. 

### RAMAS EN PROYECTOS:

En general, en cada proyecto existen las siguientes ramas:

1. Main: Rama principal donde se aloja el proyecto. 
2. Dev / Exp: La Rama o ramas de los desarrolladores donde trabajan aparte.
Dev --> Development. 
Exp --> Experimental. 
3. HotFix / BugFix: Ramas donde se tienen que arreglar bugs de manera urgente o 
un bug que con el tiempo se va a arreglar. 

Es una visión en general de los proyectos de como usan las ramas para el desarrollo
del mismo. 

### COMANDOS:

1. `git branch`: Comando para identificar la rama actual en la que te encuentras. 
2. `git branch -b <nombre de la rama>`: Comando para crear una rama nueva.
3. `git branch -D`: Comando para eliminar un rama. 
4. `git switch <nombre de la rama>`: Comando para moverte a otra rama.
5. `git switch -c <nombre de la rama>`: Comando para crear una nueva rama y moverte
a ella.
6. `git merge <nombre de la rama>`: Comando para unir ramas, ten en cuenta que 
al usar ese comando, une la rama que estás llamando con la rama actual en la que
te encuentras. 

**NOTA**:

Hay un comando que es como navaja suiza que puede hacer muchas cosas, este comando
es `git checkout` con ese comando puedes cambiar de ramas, crear una nueva rama,
restaurar archivos y un sin fin de cosas más que no tengo el conocimiento por ahora.

Se recomiendo no usar ese comando sino, usar los comandos que tienen una sola 
función o se encargan de una sola cosa. Ya que esto facilita ver el historial para
tus colegas de trabajo, evitar errores en el proyecto, evitar restaurar archivos
que no necesitas... etc.

---

# CLASE #5

## Volviendo en el Tiempo en Git: Reset y Revert

Suele pasar que necesitamos corregir ciertas cosas en el proyecto y para ello
nos tenemos que mover a commits anteriores para poder corregir los errores. 
Podemos usar dos comandos que vamos a ver a continuación pero antes necesitamos
hacer lo siguiente:

1. Usar `git log` para tomar el identificador del commit al que queremos regresar
o desacer los cambios.
2. Tomar la decisión correcta de cual el comando que vamos a usar y hablar lo con
el equipo.

Los comandos son:


1. `git revert <identificador>`: Este comando lo que hace es crear un nuevo commit
borrando todos los cambios hechos en el commit puesto en el identificador, que nos
lleva al commit anterior del indentificador.

**VENTAJAS**:

- Mantiene el historial de manera lineal. 
- Evitamos borrar cosas importantes por error.
- Es un comando menos instrusivo. 

**CONSIDERACIONES**

- Este comando solo sirve para los commits nuevos, para el último commit, ya que
si lo hago en un commit del pasado, lo que borre o haga no se va a ver reflejado 
en el presente ni en futuros commits. 

Esto pasa porque cada commit es independiente y modificar algo en el pasado, no se
va a ver reflejado.

**VISUALIZACION**:

Imaginemos que tenemos los siguientes commits:

A -> B -> C -> D -> E

Si me he equivocado con cosas del commit "E" puedo revertir las cosas, quedando
así:

A -> B -> C -> D -> E -> revert-E 

Luego de hacer los cambios que necesito puedo seguir con mi trabajo normal:

A -> B -> C -> D -> E -> revert-E -> F -> G -> H


2. `git reset <identificador>`: Este comando literalmente borra las cosas del 
historial, borra los archivos y las cosas del Staging area. Lo que hace es hacer
un reinicio de todo. Tiene diferentes modos:

- `git reset --hard <identificador>`: Borra todo, te lleva la punto que has puesto
en el commit del identificador.

- `git reset --soft <identificador>`: Mueve el head o puntero al commit especificado
pero mantiene las cosas en el repositorio y en el Staging area. Esto significa
que puedes un commit con los mismos cambios si lo deseas. 

- `git reset --mixed <identificador>`: Quita las cosas del Staging area, pero 
mantiene las cosas en el repositorio.

**VENTAJAS**

- Te limpia el historial.
- Si las cosas están super mal, te elimina todo.

**CONSIDERACIONES**

- Este comando es muy peligroso, porque literalmente borra todo, puede afectar
el trabajo tuyo y el de tus compañeros, además de tirar te las cosas.
- Este comando si lo vas a aplicar, habla lo con tu equipo primero.
- Nunca uses este comando para quitar las cosas del Staging area, usa el otro
comando. 

**VISUALIZACION**

Imaginemos que tenemos los siguientes commits:

A -> B -> C -> D -> E -> F -> G -> H -> I -> J

Me he equivocado y necesito volver al commit E porque todo ha salido mal.
Al aplicar el comando se va a ver así:

A -> B -> C -> D -> E

literalmente como ves, se borra todo, desde este punto, puedo continuar con
el proyecto normal.

---

# CLASE #6

## Gestion de Versiones con tag y checkout

### Git tag

¿Es bueno tener una lista entera de commits? ¿Cómo se manejan las versiones?
Realmente no es bueno tener una lista interminable de commits, lo que tienes
que hacer es crear versiones de tu proyecto. Es muy facil de hacerlo y Aquí
te explico como.

**COMANDOS**

1. `git tag`: Con este comando puedes tomar el id o el hash de un commit y 
ponerle un tag, una etiqueta, le puedes cualquier nombre y así se llamará
ese commit. Por ejemplo:

`git tag -a <nombre de la version> <id del commit> -m <mensaje>`

Es bueno que al final, le coloques un mensaje al tag para que al futuro recuerde
que has hecho. 

2. `git tag`: Con este comando puedes mirar todos los tag o etiquetas que has 
puesto en tu proyecto. 

3. `git show <nombre de la etiqueta>`: Puede acceder directamente al commit con 
el nombre de la verión que le has puesto. Puedes mirar toda la info como: archivos,
fecha y hora, autor, mensaje, id del commit, etc.

4. `git tad -d <nombre de la etiqueta>`: Con este comando puedes eliminar la 
etiqueta, quizas te has equivocado y lo necesitas cambiar. 

5. `git push origin <tag_name>`: Con este comando envías tu etiqueta a un 
repositorio remoto. Cambia tag_name por el nombre de la etiqueta.

6. `git push origin --tags`: Con este comando envías todas las etiquetas que 
tengas en al repositorio remoto. 

**NOTA**:

1. Es muy bueno usar `git tag` ya que es un separador de commits, como un separador
de libros, muy útil en tu equipo.
2. Si eliminas una etiqueta, no pasa nada, solo se elimina el tag, el commit sigue 
intacto.
3. Todos los commits deberían tener un tag, pero como es mucho trabajo es bueno
ponerse de acuerdo con el equipo de trabajo y plantear cuando nombran una versión
del proyecto.

### Git Checkout

Otro de los usos que tiene el `git checkout` es que puedes cambiar de commits ya
regresar commits atrás. Esto te da una gran ventaja para probrar cosas en el 
repositorio. 

Ten encuenta que al cambiar, git te da un aviso que no estás en el head y que los
cambios que realices no serán guardados, en cambio, si los necesitas guardar, te
recomienda crear una nueva rama y ahí guardar todos los cambios para que a futuro
si lo necesitas hagas merge. 

Para regresar al commit original de tu proyecto usa `git checkout main`

**NOTA**

1. Si no has hecho un commit antes de moverte a otro commit en el pasado, git
te da un error y te dice que primero realices el commit antes de irte a otro.
2. Recuerda que todo lo que hagas no queda guardado a no ser que le hagas a no ser
que lo guardes en otra rama. 

---

# CLASE #7
## COMO RESOLVER CONFLICTOS DE RAMAS EN GIT

Cuando estamos trabajando en una empresa, proyecto o con otras personas, es normal
ver que hay varias personas trabajando en un mismo archivo. Entonces cuando llega
el momento de combinar todo el trabajo, lo que va a pasar son conflictos, choques
con las ramas.

¿Cómo se resuelven esos conflictos? Es muy sencillo:

1. Cuando usas el comando `git merge`, te sale un mensaje de advertencia que 
hay conflictos. 
2. Se te abre tu editor de código y te da las opciones de conservar el cambio
actual y rechazar el cambio que viene, conservar el cambio que viene y rechazar
el cambio actual, conservar ambos cambios o comparar los cambios.

Puedes elegir cualquier opción y si luego deseas, puedes agregar o quitar cosas.

3. En caso que no te salga en tu editor, abre nano o vim en la terminal para 
resolver los conflictos, no te preocupes que git te va a resaltar donde están esos
conflictos.
4. Haces un commit ya con los cambio hechos.
5. Haces un merge para que todo se integre correctamente.
6. Eliminas la rama que ya no tiene razón para existir.

---
# CLASE #8
##  Usando Git desde Visual Studio Code

Todo lo que hemos aprendido se puede usar en Visual Studio Code porque viene 
integrado, tambien en otros de texto para código traen estás mismas opciones. 


Experimenta, prueba y mejora!. 

---
# CLASE #9 
## Git Hub es clave para los desarrolladores

En Resumidas cuentas, en estas clases vimos en general que es Git Hub, y como crear
el perfil en la plataforma. 

También en como crear la llave SSH para la conexión de manera totalemente segura 
en el servidor de Git Hub con los datos encriptados. 

Esos apuntes, no los tomé, pues ya no los tengo hecho desde hace tiempo. 

Nota: Git Hub no tiene nada que ver con Git, solo han tomado el nombre. 
---

# CLASE #10
## Clone, fork, y estrellas a respositorios 

En la plataforma de Git Hub, hay muchas cosas que puedes hacer, entre ellas:

1. **Fork**: Es sacar una copia del código de alguien más a tu cuenta de Git Hub,
una vez que sacas la copia, se queda congelado el código, es decir, que no 
se actualiza del repositorio original. 

Es muy importante que siempre le hagas un fork a los proyectos que quieras copiar
y trabajar, ya que con ello, tienes la copia y puedes trabajar bajo tus propias
condiciones sin la necesidad de dañar o interferir con el proyecto original, además
que las personas del repositorio original, no te puede molestar a ti.

2. **Estrellas**: Marca como favoritos los proyectos que más te parecen interesantes
y que aperecen en el feed. 

---

# CLASE #11
##  Trabajo con repositorios remotos: push, pull, fecth

Comandos esenciales para trabajar con Git Hub:

1. `git pull`: se trae la info del repositoria remoto al local y la actualiza. 
2. `git push`: envía la info del repositorio local al repositorio remoto. 
3. `git fetch`: se trae la info del repositorio remoto, pero no actualiza tu 
repositorio local. 

**NOTA**:

1. Al comando `git push` y `git pull` puedes agregar el parametro `-u` para conectar
las ramas, eso quiere decir que solo con escribir `git push` o `git pull` envía,
o se trae la info sin necesidad de especificar la rama. Puede ser útil, pero si 
uno no es conciente, puede hacer un revuelto con las ramas, así que no recomiendo
usar el parametro `-u`.
