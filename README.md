# Versionamiento de código con GIT
## Inicialización de un repositorio
1. Crear la estructura de carpetas de nuestro proyecto:
- `mkdir nombre_de_la_carpeta` : Creamos la carpeta principal del proyecto
- `cd nombre_de_la_carpeta` : Nos movemos a la carpeta principal del proyecto
- `code .` : Abrir en el VSC la carpeta del proyecto
- Una vez abierto el VSC nos creamos la estuctura de carpetas y los archivos necesarios para empezar a trabajar.
- Abrir una nueva terminal
- Corremos el comando `git init`: Para inicializar el repositorio
- Corremos el comando `git add .`: Añadir TODOS los nuevos archivos y capetas al espacio de preparación (staged area)
- Corremos el comando `git commit -m "mensaje del commit"`
2. Crear el repositorio remoto en nuestra cuenta GitHub
- Ingresar a nuestra cuenta GitHub
- Creamos un nuevo repositorio
- Nos regresamos a la terminal del proyecto en VSC para ejecutar las tres últimas líneas que nos proporciona GitHub:
    - git remote add origin git@github.com:WhitneySt/test-git.git : Para apuntar al remoto
    - git branch -M main: Para renombrar la rama principal de Master a main
    - git push -u origin main: Se suben todos los archivos al repositorio remoto.

## Subir cambios a un repositorio

1. Tener disponible una terminal en VSC
2. Si queremos comprobar el estados de los archivos de nuestro proyecto: `git status`
3. `git add .`
4. `git commit -m "mensaje del commit"`
5. `git push origin main`
