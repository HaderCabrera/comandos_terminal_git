---
marp: false
---

# MODULO 3
## Git
![Rta de trabajo](/modulo3/imagenes/Captura%20desde%202024-01-25%2019-08-12.png)

Creamos carpeta de trabajo
```
user@root:~$ pwd
/home/user
user@root:~$ mkdir intro-git
user@root:~$ cd intro-git
```

- Visualizar configuracion por defecto del GIT.
```
user@root:~/intro-git$ git config --list
```
- Configurar de GIT.
```
user@root:~/intro-git$ nano ~/.gitconfig
user@root:~/intro-git$ git config --global user.name "haderCabrera"
user@root:~/intro-git$ git config --global user.email "hader.cabrera96@gmail.com"
```

Configurar programa que ejecuta
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
- Agregar al parte de trabajo INDEX (Ver primera imagen)
    - Agregar todos los archivos

```
user@root:~/intro-git$ git add README.md
user@root:~/intro-git$ gid add .
```
Copnsultar status del git
```
user@root:~/intro-git$ git status
```
Crear un git ignore
```
user@root:~/intro-git$ nano .gitignore
```
- ELIMIMNAR ARCHIVOS EN AREA INDEX

```
user@root:~/intro-git$ git rm --cached index.html main.js styles.css
```
Realizar commit
```
user@root:~/libro$ git commit -m "Añadido indice del libro"
```

Historico de commits
```
user@root:~/intro-git$ git log
user@root:~/intro-git$ git log --oneline
```

Ubicarme en un comit en especifico
```
user@root:~/intro-git$ git checkout 104715b
user@root:~/intro-git$ git checkout master
```

## CLASE 2 GIT (CREAR BRANCH Y REPOSITORIO GITHUB)

```
```
Consultar las ramas actuales
```
user@root:~/intro-git$ git branch
```
Crear rama nueva
```
user@root:~/intro-git$ git branch ramaEjemplo
```
Cambiar nombre a la rama
```
user@root:~/intro-git$ git branch -m main

```
Moverme a otra rama
```
user@root:~/intro-git$ git checkout ramaEjemplo
```
Combinar ramas, debo estar parado en la rama mas vieja y cargar la rama mas nueva
```
user@root:~/intro-git$ git merge otraRama
```
Borrar ramas
```
user@root:~/intro-git$ git branch -D ramaEjemplo

```
Arrastrar camvios desde cualquier rama a la principal, debo hacer el merge desde el master a la rama ultima.

```
user@root:~/intro-git$ git merge diseno-front
```

- Crear un repositorio nuevo
    - origin: Nombre del repositorio local
    - la URL es la que viene de la creacion del repositorio
```
user@root:~/intro-git$ git remote add origin https://github.com/HaderCabrera/repositorio-pruebaa.git
```
Relacionar los push que voy a hacer destino(github- origin) lo que voy a agregar (main). 
```
user@root:~/intro-git$ git push -u origin main
```
