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
    - `git remote add origin git@github.com:WhitneySt/test-git.git` : Para apuntar al remoto
    - `git branch -M main`: Para renombrar la rama principal de Master a main
    - `git push -u origin main`: Se suben todos los archivos al repositorio remoto.

## Subir cambios a un repositorio

1. Tener disponible una terminal en VSC
2. Si queremos comprobar el estados de los archivos de nuestro proyecto: `git status`
3. `git add .`
4. `git commit -m "mensaje del commit"`
5. `git push origin main` o `git push origin nombre_de_la_rama_actual`

## Trabajar con estrategias de branching
Existen dos estrategias de branching:
1. Trunk-based: Cuando trabajamos de manera individual
2. Git Flow: Para trabajo colaborativo

## Trabajar con Git Flow
1. Se ejecutan los pasos anteriores de **Inicialización del repositorio**.
2. Va a crear la rama develop: `git checkout -b develop`
3. Agregar unos cambios mínimos en cualquiera de los archivos existentes en la estructura de carpetas del proyecto
4. Desde la rama develop se ejecutan los pasos de Subir cambios a un repositorio.
5. Ir al repositorio remoto en GitHub, dándo click sobre el botón compare & pull Request
6. Generamos el pull Request
7. GitHub nos va a indicar si existen conflictos (si existen, se deben resolver)
8. Una vez resueltos los conflictos realizamos el merge de develop a main y confirmamos el merge (todo esto pasa en la página de GitHub)
9. En la terminal de VSC nos movemos a la rama main `git checkout main`
10. Ejecutamos `git pull` para actualizar nuestro repositorio local.
11. Configurar los colaboradores en el repositorio remoto.
12. Los colaboradores deben aceptar la invitación a trabajar el repositorio (esto puede ser mediante el correo o la notificación enviada directamente a la cuenta de GitHub).
13. Después de aceptar la invitación, cada colaborador o colaboradora debe **clonar el repositorio**:
    - Copiar el enlace https o ssh entregado al dar click sobre el botón code que aparece en el repositorio en GitHub
    - Ubicarse en la carpeta donde deseamos ubicar la carpeta del proyecto a clonar
    - Con click derecho, abrir una consola `git bash here`
    - En la consola correr el comando `git clone enlace_https_o_ssh_copiado`. **ojo que no se peguen caracteres indeseados que puedan ocasionar errores**
14. Moverse a la carpeta clonada corriendo el comando `cd nombre_carpeta_clonada`
15. Abrir el proyecto en VSC corriendo el comando `code .`
16. En VSC abrir una nueva terminal
17. En la rama main, ejecutar el comando `git pull` para actualizar
18. Moverse a la rama `develop` con el comando `git checkout develop`
19. Crear la rama de `feature` propia desde `develop` corriendo el comando `git checkout -b feature-nombreDeLaCaracteristica`
20. Empezar a trabajar en la funcionalidad del código en el editor.
21. Una vez finalizada la funcionalidad ejecutar los pasos de **Subir cambios a un repositorio**
22. Fusionar los cambios subidos desde la rama `feature` a la rama `develop`:
    - Moverse a la rama `develop` con el comando `git checkout develop`
    - Actualizar la rama `develop` con el contenido que puede existe en el repositorio remoto con `git pull origin develop` **Ojo 👀 cuida'o que esto es importante**
    - Moverse a la rama `feature` con `git checkout feature-nombre`
    - Integrar los cambios existentes en la rama `develop` con `git merge develop`
    - Si existen conflictos, estos deben ser resuelto y una vez corregidos en el editor de VSC; se deben ejecutar los pasos de **Subir cambios a un repositorio**
    - Moverse a la rama `develop` con `git checkout develop`
    - Ejecutar `git pull origin develop`
    - Integrar los cambios existentes en la rama `feature-nombre` con `git merge feature-nombre`
    - Si existen conflictos, estos deben ser resuelto y una vez corregidos en el editor de VSC; se deben ejecutar los pasos de **Subir cambios a un repositorio**
 23. Una vez completadas las funcionalidades Fusionar los cambios existentes en la rama `develop` en la rama `main`

*Nota:*
- `git reset`: para deshacer `git add`
- `git push origin --delete nombre_de_la_rama`: Para eliminar una rama (o branch existente en el repositorio remoto)
