---
marp: false
---

# MODULO 3
## Git (MOVERME EN EL AREA LOCAL)
![Rta de trabajo](/imagenes/Captura%20desde%202024-01-25%2019-08-12.png)

- Creamos carpeta de trabajo
```
mkdir intro-git
```
- Visualizar configuracion por defecto del GIT.
```
user@root:~/intro-git$ git config --list
```
- Configurar de GIT (2 OPCIONES).
```
nano ~/.gitconfig
git config --global user.name "haderCabrera"
git config --global user.email "hader.cabrera96@gmail.com"
```

- Configurar programa que ejecuta (visualStudio = CODE)
```
user@root:~/intro-git$ git config --global core.editor code --wait
```
- Iniciar git
```
user@root:~/intro-git$ git init
```
- Crear archivo README y ejecutarlos con visual
```
user@root:~/intro-git$ nano README.md
user@root:~/intro-git$ code .
```
- Pasar a **STAGING AREA** (Ver primera imagen)
- Agregar todos los archivos

```
user@root:~/intro-git$ git add README.md
user@root:~/intro-git$ gid add .
```
Consultar status del git
```
git status
```
Crear un git ignore (Archivos que quiero omitir al cargar cambios)
```
nano .gitignore
```
- Eliminar archivos despues de un **add** (STAGING AREA - WORKING DIR)

```
git rm --cached index.html main.js styles.css
```
- Realizar commit
```
user@root:~/libro$ git commit -m "Añadido indice del libro"
```
- Historico de commits
```
git log
git log --oneline
```
Ubicarme en un comit en especifico
```
git checkout 104715b
git checkout master
```

## CLASE 2 GIT (CREAR BRANCH Y REPOSITORIO GITHUB)

- Consultar las ramas actuales
```
git branch
```
- Crear rama nueva
```
git branch ramaEjemplo
```
- Cambiar nombre a la rama
```
git branch -m main
```
- Moverme a otra rama
```
git checkout ramaEjemplo
```
- Combinar ramas, debo estar parado en la rama mas vieja y cargar la rama mas nueva
```
git merge otraRama
```
- Borrar ramas
```
git branch -D ramaEjemplo

```
- Arrastrar cambios desde cualquier rama a la principal, debo hacer el merge desde el master a la rama ultima.

```
git merge diseno-front
```

- Crear un repositorio nuevo
    - origin: Nombre del repositorio local
    - la URL es la que viene de la creacion del repositorio
```
git remote add origin https://github.com/HaderCabrera/repositorio-pruebaa.git
```
Relacionar los push que voy a hacer destino(github- origin) lo que voy a agregar (main). 
```
git push -u origin main
```
## CLASE 3 GIT (TRABAJANDO CON GITHUB)
```
```
Verificar si estamos conectados a un repositorio remoto
```
git remote
remote -v
```
Desconectarme de repositorio demoto
```
git remote rm origin
```
Clonar repositorio en la carpeta donde estoy parado
```
git clone https://github.com/HaderCabrera/repositorio-pruebaa.git
```
Ver primeras lineas y ultimas lineas
```
head -5 README.md
tail -5 README.md 
```
### MOVERME ENTRE COMMITS
- Borrar algo que edite sin haber echo el commit o add (WORKING DIR)
```
git restore README.md
```
Borrar algo que edite despues de hacer un add 
- STAIGIN AREA -> WORKING DIR
-   STAIGIN AREA -> WORKING DIR -> WORKTREE (ELIMINAR TOTAL)
```
git restore --staged README.md
git restore --staged --worktree README.md
```
Devolverme a un commit en especifico con ID del commit (para un archivo en especifico)
```
git restore --source a00d59a README.md
```
**Despues de hacer esto, unicamente estoy visualizando el archivo en ese commit; si me devuelvo con restore el archivo se restaura al ultimo commit; si quiero trabajar sobre ese commit que estoy visualizando debo volver a hacer un commit.**
### Cambios con checkout
Es necesario crear una nueva rama para que queden los archivos en una rama, de lo contrario se eliminaran de forma automatica por el bot.

- Hacer checkout
- Crear nueva rama para ese checkout
- Hacer commit en esa nueva rama
```
git checkout a00d59a
git checkout -b rama-taller
git commit -am "Creando la rama taller"
```
**Se mantiene los cambios de del main ya que cree una nueva rama**
### Cambios con reset
Importante hacer el reset en una rama privada, no en la principal ya eliminaria el commit para todos los colaboradores.
```
git reset 636e8df
git reset HEAD~1
```
**Es necesario hacer restore para actualizar**
### Cambios con revers
Crea una nueva rama y mantiene las otras
```
git revert c227a63
```
**Es necesario hacer restore para actualizar**





