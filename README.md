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
## Reto 4

Realizar las siguientes tareas:

1. A partir de la rama main crear una nueva rama llamada development
2. Regresar a la rama main
3. Modificar el archivo index.js agregando:
console.log('Modificación Reto 3 rama main');
4. Sin perder el cambio de la rama main y sin hacer commit o push de los cambios, cambiar a la rama development y modificar el archivo index.js agregando
console.log('Modificación Reto 3 rama development');
5. Hacer push a la rama development
6. Regresar a la rama main, recuperar los cambios y hacer push a la rama

Se debe dejar el registro de todos los comandos o acciones realizadas para el cumplimiento del reto

## Comandos utilizados
```bash
# Crear una nueva rama llamada development
git checkout -b development

# Regresar a la rama main
git checkout main

# (Modificar el archivo index.js agregando:)
console.log('Modificación Reto 3 rama main');

# Guardar los cambios sin hacer commit
git stash

# Cambiar a la rama development
git checkout development

# Recuperar los cambios sin eliminar el stash
git stash apply

# (Modificar el archivo index.js agregando:)
console.log('Modificación Reto 3 rama development');

# Agregar los cambios, hacer commit y push en development
git add .
git commit -m "modificacion en development"
git push origin development

# Regresar a la rama main
git checkout main

# Recuperar los cambios restantes del stash (y eliminar el stash)
git stash pop

# Agregar los cambios, hacer commit y push en main
git add .
git commit -m "modificacion rama main"
git push origin main
```
## SOLUCION 2

```bash
git checkout -b development
git checkout main
echo -e '\nconsole.log("Modificación Reto 3 rama main");' >> index.js
git stash -u -m "2025-04-25 Modifica index.js en rama main"
git stash show -p stash@{0}
git stash list
git checkout development
echo -e '\nconsole.log("Modificación Reto 3 rama development");' >> index.js
git add -A
git commit -m "Modificación al archivo index.js rama development"
git push origin development
git checkout main
git stash pop stash@{0}
git add -A
git commit -m "Modificación al archivo index.js rama main"
git push origin main
```
## RETO 5

Realizar las siguientes tareas:

1. Ubicarse en la rama main
2. Crear un archivo llamado operaciones.ts agregando una función que permita sumar dos números y retornar el resultado
3. Sin perder el cambio de la rama main y sin hacer commit o push de los cambios, cambiar a la rama development, recuperar las modificaciones hechas en el punto 2 asegurandose que los cambios permanezcan disponibles para ser usados en cualquier otra rama
4. Hacer push a la rama development
5. Regresar a la rama main, recuperar los cambios. NO se debe hacer commit ni push a la rama main
6. Eliminar el archivo package.json del proyecto
7. Recuperar el archivo package.json

Se debe dejar el registro de todos los comandos o acciones realizadas para el cumplimiento del reto

## SOLUCION 

```bash
# UBICARSE EN LA RAMA MAIN
git branch
# creacion de archivo operaciones.ts
cree el archivo manualmente y agrege la funcion para sumar dos numeros
# sin perder los cambios pasarse a la rama development y recuperar los cambios hechos
git stash -u -m "2025-05-02 archivo operaciones.ts rama main"
git stash pop stash@{0}
# Hacer push de la rama development
git add -A
git commit -m "agregando archivo y funcion de suma de numeros"
git push origin development

# regresar a la rama main, recuperar los cambios
git checkout main
git checkout development -- operaciones.ts
git checkout development -- README.md

# eliminar el archivo package.json
se elimino manualmente

# Recuperar el archivo package.json
git checkout HEAD -- package.json
# recomendado
git restore packagae.json
```

## Reto 6
Realizar las siguientes tareas:

1. Ubicarse en la rama main
2. Actualizar el repo remoto en la rama main con los cambios pendientes del reto anterior
3. Cambiar a la rama development
4. Modificar el archivo operaciones.ts para:
    4.1. Agrega en la primera línea del archivo: console.log('Operaciones Matamáticas');
    4.2. Cambia el nombre del método suma por opAdd
    4.3. Agregar un tercer parámetro al método opAdd y que sea tenido en cuenta en la operación
    4.4. Agregar un nuevo método llamado opLess, que reciba dos parámetros y retorne el valor de la operación de restar los dos parámetros
5. Actualizar la rama development en el repo remoto
6. Cambiar a la rama main y modificar el archivo operaciones.ts agregando una operación de división, luego actualizar la rama main con el cambio en el repo remoto 
7. Fusionar los cambios de la rama remota development en la rama local main
8. Actualizar la rama main en el repo remoto

Se debe dejar el registro de todos los comandos o acciones realizadas para el cumplimiento del reto, incluyendo la resolución de conflictos y justificación del comando usado para la fusión de cambios

## SOLUCION 

```bash
# 1. Ubicarse en la rama main.
git branch

# 2. Actualizar el repo remoto en la rama main con los cambios pendientes del reto anterior.
git add -A
git commit -m "Cambios pendientes reto anterior"
git push origin main

# 3. Cambiar a la rama development
git checkout development

# 4. Modificar el archivo operaciones.ts
# 4.1. Agregue el console.log('Operaciones Matamáticas');
# 4.2. Cambie el nombre del método suma por opAdd
# 4.3. Agregue un tercer parámetro al método opAdd y que sea tenido en cuenta en la operación
# 4.4. Agregue un nuevo método llamado opLess, que reciba dos parámetros y retorne el valor de la operación de restar los dos parámetros

# 5. Actualizar la rama development en el repo remoto
git add -A
git commit -m "se agrego el log al inicio, cambios en la funcion de suma por opAdd mas un nuevo parametro y una nueva funcion opLess"
git push origin development

# 6. cambiar a la rama main, y agregar en el operaciones.ts una funcion de division y actualizar el repo.
git checkout main
# se agrega la funcion de division en operaciones.ts
git add -A
git commit -m "se agrega funcion de division en operaciones.ts"
git push origin main

# 7. fusionar los cambios remotos de development en la rama local main.
git pull origin development
# se soluciono los conflictos al traer los cambios de development

# 8. Actualizar la rama main.
git add -A
git commit -m "solucionando conflictos de development a main"
git push origin main
```
## SOLUCION 2

```bash
git checkout main
git add -A && git commit -m "Actualización de cambios del reto 5"
git push origin main
git checkout development

# Ajustes al archivo operaciones.ts:

console.log('Operaciones Matemáticas');

function opAdd(a: number, b: number, c: number): number {
    return a+b+c;
}

function opLess(a: number, b: number): number {
    return a-b;
}

# Actualizar la rama development en el repo remoto

git add -A && git commit -m "Modificaciones a operaciones.ts"
git push origin development

# Cambio a main y ajustes
git checkout main

# Modificaciones a operaciones.ts

function suma(a: number, b: number): number {
    return a+b;
}

function dividir(a: number, b: number) {
    try {
        return a+b;
    } catch (error) {
        console.error(`Error: ${error}`);
    }
}

#Actualización remota de rama main:
git add -A && git commit -m "Modificaciones a operaciones.ts"
git push origin main

# Fusión de cambios remotos de development a rama main y actualización remota de la rama main
git fetch
git merge origin/development // git merge --no-ff origin/development
// TODO: solución de conflictos
git add :/
git add -A && git commit -m "Mezcla cambios desde rama remota development y resolución de conflictos"
git push origin main
```

## RETO 7

```
git tag -a v1.0.0-beta <commit> -m "Prerelease (Beta) de lanzamiento del proyecto"
git push origin v1.0.0-beta
```

En GitHUb:
- En la página principal del proyecto, en la parte derecha, dar click en 'Create a new release'
- Diligenciar el formulario seleccionando la versión 1.0.0-beta y verificar que se marque la casilla 'Set as a pre-release'

Para que sirven las etiquetas:
Principalmente sirven para identificar un punto de desarrollo determinado en un proyecto y son usadas para identificar versiones del desarrollo

Para que sirven los releases:
Permiten identificar una publicación oficial de una versión en la plataforma de administración de repositorios (GitHub, GitLab, etc) y pueden incluir archivos binarios como por ejemplo instaladores, archivos de ayuda o archivos anexos requeridos para el proyecto, y son ideales para compartir versiones de desarrollo entre personas/equipos de desarrollo

Para que sirven los prereleases:
Identifican una publicación aún NO oficial de una versión, por ejemplo versiones alpha, beta o borradores, generalmente los prerelease son usados en ambiente de pruebas (QA), y generalmente incluyen un sufijo indicando el status, por ejemplo -alpha, -beta, -rc1 (rc = release candidate)

| **Elemento**  | **¿Qué marca?**          | **¿Quién lo ve?**      | **¿Para qué sirve?**                |
|---------------|---------------------------|------------------------|-------------------------------------|
| **Tag**       | Punto exacto en Git       | Desarrolladores        | Identificar versiones (ej. `v1.0.0`) |
| **Release**   | Versión oficial en GitHub | Usuarios / Desarrolladores | Publicar cambios y binarios (instaladores, builds, etc.) |
| **Prerelease**| Versión aún no final      | QA / Testers          | Probar antes de lanzar una versión estable (ej. `v1.0.0-beta`, `v2.0.0-rc1`) |

Patrón Versionamiento Semántico (http://semver.org/spec/v2.0.0.html) es el patrón de versionamiento más común

