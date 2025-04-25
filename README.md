<p align="center">
  <img src="https://openits.co/wp-content/uploads/2020/07/log-peque.png" alt="Open Logo">
</p>

# CO.OPEN.GIT.TEST

## Reto 1
## Repositorio para pruebas con GIT y GitHub 

Este repositorio está destinado a practicar con Git y GitHub como parte de mis retos de programación. El objetivo es mejorar mi flujo de trabajo con estas herramientas, familiarizarme con la gestión de versiones y aprender a integrar GitHub con mis proyectos de manera eficiente. Aunque no contiene código, me sirve para poner en práctica lo aprendido y asegurarme de seguir buenas prácticas desde el inicio de cualquier proyecto.

## Comandos utilizados
```bash
# Inicializar repositorio
git init

# Añadir y hacer commit
git add .
git commit -m "first commit"

# Enlazar con repositorio remoto y subir a main
git remote add origin https://github.com/crixus12cr/co.open.git.test.git
git branch -M main
git push -u origin main
```

## Reto 2

En el repo local crear estos archivos:

./index.html
./test.log
./vendor/autoload.php
./node_modules/index.ts

El objetivo es realizar un commit y push al repo remoto evitando que archivos de tipo .log y las carpetas vendor y node_modules sean agregadas al commit y se envíen al repo remoto.

## Reto 3

El objetivo es inicializar el proyecto de JS con el que vamos a trabajar:

- 1. Eliminar las carpetas node_modules, vendor y los archivos index.html y test.log, prestar atención al estado del stage en el que quedan estos archivos y carpetas
- 3. Inicializar un proyecto de Node.js
- 4. Crear un archivo index.js con el siguiente contenido:
    console.log("¡Retos de GIT!");
- 5. Actualizar el repo remoto con el cambio

## Comandos utilizados
```bash
# Eliminar carpetas y archivos
Elimine manualmente las carpetas de vendor y node_modules, ademas elimine el index.html el cual al eliminar se veia en su cambio con un D en el local y el test.log no cambio.

# Inicializar node
npm init

# Crear archivo index.js
se creo manualmente el archivo y se agrego lo siguiente:
- console.log("¡Retos de GIT!")

# Actualizar repositorio
git add .
git commit -m "Inicializa nodeJS y elimina carpetas y archivos no usados"
git push
```