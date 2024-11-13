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
5. `git merge <nombre de la rama>`: Comando para unir ramas, ten en cuenta que 
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

##

