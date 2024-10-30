# apuntes_git_hub
Mis apuntes en clases de Git y Hub

---

# ¿Para que sirve Git?

Git es un controlador de versiones para poder trabajar en los proyectos, sirve
también para poder trabajar en equipo. Antes habían muchos problemas para 
poder gestionar las versiones de proyectos y en la mayoria daban errores, 
cuando surgió git, fue implementado de inmediatamente. 

---

# Conceptos Generales de Git

1. **Repositorios**: Git se maneja con repositorios, los cuales son la carpeta donde
se aloja el proyecto. Cada desarrollador cuenta con una copia en su maquina local
del repositorio original el cual puede trabajar.

2. **Ramas**: Son lineas de desarrollo independiente del cual puedes trabajar y si
deseas unirlas al proyecto original, en caso que no puede surgir un proyecto 
totalmente nuevo. 

3. **Arbol**: Cuando un proyecto es muy amplio, puede tener un arbol de versiones,
donde cada rama es independiente de la otra, al final la mirada general de las ramas
se vuelve un arbol. 

4. **Commits**: Son los cambios guardados de una rama en el proyecto. 

5. **Merge**: Es combinar dos ramas o muchas más en una sola. 

---

# Pasos fundamentales para usar Git:

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

3. **Correo**: Cuando se realiza algún cambiar en algún proyecto es importante 
saber quien es y su correo para poder contactar a la persona. Para esto configura el
correo de manera global con el siguiente comando:

`git config --global user.email "<email>"`

Cambia las `<>` por tu correo electronico de trabajo. 


# ¿Cómo comenzar a usar Git?

Para poder comenzar a usar a git en un proyecto, es importante primero configurar

Para poder comenzar a usar git en un proyecto, puedes clonar lo desde Git Hub
o en la carpeta donde se encuentra el proyecto usar el comando:

`git init`

Con ese comando se inicia git y así poder empezar con el control de versiones.    

Comando para saber sobre otros comandos:

`git --help`
