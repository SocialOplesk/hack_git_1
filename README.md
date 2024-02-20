# SOCIAL OPLESK
### 🏴‍☠️ HACKS 
<br/>

## ⚡️ Realizar los 8 Hacks ➔ (Ejercicios) ⚡️

📚 docs [comandos git 1](https://gist.github.com/dasdo/9ff71c5c0efa037441b6) | [comandos git 2](https://github.com/joshnh/Git-Commands/blob/master/READMEes.md) | [comandos git 3](https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html) | [config cuenta](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Configurando-Git-por-primera-vez) 
---

```diff
- NOTA HACER LAS PRÁCTICAS MEDIANTE LA CONSOLA DE GIT BASH  
```
|Hacks | Details | 
|----------|---------|
| H-1      | Enviar un commit al repositorio remoto |
| H-2      | Enviar un directorio vacio al repositorio remoto |
| H-3      | Hacer merge en mi master local y luego con master remoto | 
| H-4      | Extraer archivo de stage |
| H-5      | Enviar una rama remota  |
| H-6      | Clonando un repositorio remoto |
| H-7      | Eliminar un archivo en el repositorio remoto | 
| H-8      | Volver a un commit anterior                  |

<br/> 

## 🏆 H-1 (ENVIAR UN COMMIT AL REPOSITORIO REMOTO)

![](https://github.com/SocialOplesk/hack-git-1/blob/main/gifs/hack_git_1_clone_h1.gif)

1. Crear un nuevo repositorio en github nombre: git_h_1

2. Crear un repositorio local
```
git init
```

3. Registrar el repositorio remoto con tú repositorio local
```
git remote add origin (pegar_la_ruta_del_repositorio_local)
```

4. Verificamos la ruta remota
```
git remote -v
``` 

![](https://github.com/SocialOplesk/hack-git-1/blob/main/gifs/hack_git_1_process_h1.gif)
5. Crear un archivo llamado lista_de_usuarios.txt
```
touch lista_de_usuarios.txt
```

6. Examinar la creación del archivo
```
ls -l
```

7. Agregar el archivo lista_de_usuarios.txt al stage(marcarlos para commitear)
```
git add lista_de_usuarios.txt
```

8. Verificamos el status
```
git status
```

9. Se realiza el commit 
```
git commit -m "feat: add lista_de_usuarios.txt"
```

10. Verificamos el commit
```
git log --oneline
```

11. cambiar el nombre del ambiente (rama)
```
git branch -M main
```

12. Hacemos push
```
git push -u origin main
```

12. Verificamos el repositorio remoto en github para ver el push enviado

<br/>

---

## 🏆 H-2 (ENVIAR UN DIRECTORIO VACIO AL REPOSITORIO REMOTO)

![](https://github.com/SocialOplesk/hack-git-1/blob/main/gifs/hack_git_1_clone_h2.gif)

1. Crear un nuevo repositorio en github nombre: git_h_2

2. Crear un repositorio local
```
git init
```

3. Registrar el repositorio remoto con tú repositorio local
```
git remote add origin (pegar_la_ruta_del_repositorio_local)
```

4. Verificamos la ruta remota
```
git remote -v
``` 

5. Crear 1 carpeta ó directorio con el nombre de "usuarios"
```
mkdir usuarios
```

6. Verificar la creación del directorio
```
ls -l
```

7. Ahora si haces un status del stage
```
git status
```

8. La carpeta no aparece en el stage, es decir la vez creada, pero en git es como que no la reconoce,
   esto es debido a que git no hace seguimiento a directorios vacios.
   
   En este momento es necesario elaborar un archivo interno en el directorio "usuarios",
   pero si por los momentos no queremos agregar nada en ella, pero si tenerla en nuestro repositorio
   debemos crear un archivo oculto dentro del directorio.
   
```
cd usuarios
touch .gitkeep
cd ..
ls -l
```

9. Examinamos el stage y debemos ver la carpeta ó directorio usuarios disponible para el tracking
```
git status
```

10. Agregamos el directorio al stage 
```
git add .
```

11. Se realiza el commit 
```
git commit -m "feat: add directory usuarios"
```

12. Verificamos el commit
```
git log --oneline
```

13. Crear el ambiente main
```
git branch -M main
```

14. Hacer push
```
git push -u origin main
```

15. Toca ir al repositorio remoto y ver la carpeta en nuestro repo

<br/>

---

## 🏆 H-3 (HACER MERGE EN MI MASTER LOCAL Y LUEGO CON MASTER REMOTO)


1. Crear un nuevo repositorio en github nombre: git_h_3

2. Crear un repositorio local
```
git init
```

3. Registrar el repositorio remoto con tú repositorio local
```
git remote add origin (pegar_la_ruta_del_repositorio_local)
```

4. Verificamos la ruta remota
```
git remote -v
``` 

5. Se te asigna una tarea de crear una lista de comidas, para tal fin hacemos un archivo llamado "menu_de_comidas.txt"
```
touch menu_de_comidas
```

6. Verificamos que el archivo existe en nuestro equipo y adicional examinamos el estatus en git
```
ls -l
git status
```

7.  Agregamos el archivo, verificamos su status de stage y log, para luego hacer push 
```
git add .
git status
git commit -m "feat: add menu_de_comidas.txt"
git log --oneline
git push -u origin master
```

8. Toca analizar el repositorio remoto en github para ver el commit 

9. Se necesita crear una rama llamada feature/agregarComidas
```
git branch feature/agregarComidas
```

10. Comprobar la creación de la rama
```
git branch 
```

11. Como se trata de agregar comida al archivo "menu_de_comidas.txt" lo ideal 
    que para cada tarea a realizar
    se cree una nueva rama, bien vamos a la rama creada 
```
 git switch feature/agregarComidas
```

12. Ahora agregamos una lista de comidas al archivo "menu_de_comidas.txt",
   esto se hace por medio del comando echo -e "mas el texto"
```
echo -e "arroz, pan, pizza" >> menu_de_comidas.txt
``` 

13. Se necesita observar dentro del archivo "menu_de_comidas.txt" para ver el contenido anexado
```
cat menu_de_comidas.txt
```

14. Viendo que hemos logrado anexar un contenido al archivo, vamos a crear un commit 
```
git status
git add .
git status
git commit -m "feat: add content in menu_de_comidas.txt"
git log --oneline
```

15. Cuando se tiene la tarea lista, se retorna a la rama master
```
git switch master
```

16. Observa que estas en la rama principal (master)
```
git branch 
```

17. Anexamos la tarea que esta en la rama "feature/agregarComidas" al master,
    mediante el comando merge y de esta forma actualizamos el área de trabajo
    llamado master(es decir la rama master)
```
git merge feature/agregarComidas
```

18. Trasladamos la tarea a la rama master del repositorio remoto
```
git push -u origin master
```

19. Miramos el repositorio remoto y ver si todo esta bien.

20. Volvemos a la consola y observamos nuestras ramas
```
git branch 
```

21. Podemos dejar la rama "feature/agregarComidas", como un mecanismo de respaldo
    aunque sino lo deseamos también puedes eliminarla 
```
git branch -D feature/agregarComidas
```

22. Exploramos las ramas
```
git branch
```

<br/>

---


## 🏆 H-4 (EXTRAER ARCHIVO DEL STAGE)


1. Crear un nuevo repositorio en github nombre: git_h_4

2. Crear un repositorio local
```
git init
```

3. Registrar el repositorio remoto con tú repositorio local
```
git remote add origin (pegar_la_ruta_del_repositorio_local)
```

4. Verificamos la ruta remota
```
git remote -v
``` 

5. Crear 3 archivos foo.txt | bar.txt | qux.txt
```
touch foo.txt
touch bar.txt
touch qux.txt
```

6. Comprobar que estan creados en nuestro local
```
ls -l
```

7. Toca ver el stage 
```
git status
```

8. Anexamos los 3 archivos al stage
```
git add .
```

9. Examinamos el stage
```
git status
```

10 Ahora toca extraer a "qux.txt" del stage y dejar los otros 2 archivos
```
git reset -- qux.txt

11. Indagamos que "qux.txt" no esta en el stage
```
git status 
```

12. Resulta que ahora no queremos ninguno de los 2 archivos restante en el stage
```
git reset --
```

13. Volvemos a observar el status del stage
```
git status 
```

14. Adjuntamos un cuarto archivo llamado "octocat.txt" 
```
touch octocat
```

15. Cuando se revisa de nuevo el stage debemos mirar los 4 archivos, que no estan seleccionados
```
git status
```

16. Los adjuntamos al stage para genrar el commit
```
git add .
git status
git commit -m "feat: add 4 files"
```

17. Resulta que se nos olvido agregar un 5 archivo llamado "delta.txt"
```
touch delta.txt
```

18. Bien, debemos agregar el archivo "delta.txt" al commit que se acaba de crear, esto lo podemos verificar 
```
git log --oneline
```

19. Agregamos el archivo al commit
```
git add delta.txt
git commit --amend -m "feat: add 5 files"
```

20. Listo ahora se analiza el commit de vuelta y se hace push 
```diff
git log --oneline
git push -u origin master
```

21. Observar el repositorio remoto


<br/>

---

## 🏆 H-5 (ENVIAR UNA RAMA REMOTA)


1. Crear un nuevo repositorio en github nombre: git_h_5

2. Crear un repositorio local
```
git init
```

3. Registrar el repositorio remoto con tú repositorio local
```
git remote add origin (pegar_la_ruta_del_repositorio_local)
```

4. Verificamos la ruta remota
```
git remote -v
``` 

5. Elaborar un archivo con el nombre de "inicio.txt"
```
touch inicio.txt
```

6. Incorporar "inicio.txt" para un commit
```
git add .
git commit -m "feat: add inicio.txt"
git push -u origin master
```

7. Ahora creamos una rama remota llamada "feature/actividades" y le adjuntamos 2 archivos "foo.txt" y "bar.txt"
```
touch foo.txt
touch bar.txt
```

8. Producimos el commit, aunque antes creamos la rama y nos vamos a ella, para desde ahí hacer el commit 
```
git branch feature/actividades
git switch feature/actividades
git add .
git status
git commit -m "feat: add 2 files foo.txt and bar.txt"
```

9. Aunque nos indican que falta crear otro archivo llamado "qux.txt" al commit
```
touch qux.txt
git add .
git commit --amend -m "feat: add 3 files foo.txt, bar.txt, qux.txt"
```

10. Enviamos la rama remota
```
git push -u origin feature/actividades
```

11. Verificar en el repositorio remoto que se envio la rama.

12. Regresamos a master
```
git switch master
```

13. Creamos una nueva rama llamada "hotfix/registroDeUsuario" por una emergencia, en ella crear un archivo llamado "registro_de_usuarios.txt"
```
git branch hotfix/registroDeUsuario
git switch hotfix/registroDeUsuario

touch registro_de_usuarios.txt
git add . 
git commit -m "hotfix: add registro_de_usuarios.txt"
```

14. Enviamos la rama "hotfix/registroDeUsuario" al repositorio remoto y revisamos el repositorio remoto
```
git push -u origin hotfix/registroDeUsuario
```

15. Retornamos a master y analizamos todas las las ramas locales y remotas 
```
git switch master
git branch -a
```

16. Eliminamos la rama remota "feature/actividades" y revisamos el repositorio
```
git switch master
git push origin --delete feature/actividades
```

17. Hacemos una mirada a las ramas 
```diff
git branch -a
```

<br/>

---

## 🏆 H-6 (CLONAR UN REPOSITORIO REMOTO)

1. Clonar es copiar un repositorio(proyecto) para tal fin, vamos a copiar un proyecto open source, 
   que es una libreria de utilidades creada en javascript llamada [Lodash](https://github.com/lodash/lodash)
   
   En el botón "code de color verde" das click y tomas la ruta del repositorio, sino acá lo tienes (https://github.com/lodash/lodash.git)
   una advertencia cuando copies la ruta del repo, verificar que este en la tab/pestaña https y no en el tab ssh
   
2. Ve a tú local a crear una carpeta "llamada git_h_6"

3. Dentro del directorio "git_h_6" y desde la terminal de "Git Bash" aplicas lo siguiente
```
git clone https://github.com/lodash/lodash.git
```

4. El proyecto se descarga y crea una carpeta con el nombre del proyecto "lodash", ahora entra en la carpeta "lodash"

5. Bien dentro de la carpeta ejecuta la terminal de "Git Bash" y exploramos la cantidad de ramas del proyecto
```diff
git branch -a
```

6. Te invito ir al repositorio de lodash [lodash](https://github.com/lodash/lodash) y observar la cantidad de ramas remotas del proyecto
   observarás que son las mismas ramas listadas de la terminal, cuando se emitio la acción "git branch -a"
   Cuando clonas un proyecto, también clonas sus ramas remotas.

7. Crear un nuevo repositorio en github con el nombre de git_h_6


8. Eliminar el archivo oculto .git en el repositorio local 

 
9. Crear un nuevo repositorio local
```
git init
```

10. Registrar el repo remoto git_h_6 en el repo local
```
git remote add origin mas_la_ruta_del_repo_remoto_git_h_6
```


11. Subir el proyecto clonado en el nuevo repositorio remoto git_h_6
<br/>


---

## 🏆 H-7 (ELIMINAR UN ARCHIVO EN EL REPOSITORIO REMOTO)


1. Crear un nuevo repositorio en github nombre: git_h_7

2. Crear un repositorio local
```
git init
```

3. Registrar el repositorio remoto con tú repositorio local
```
git remote add origin (pegar_la_ruta_del_repositorio_local)
```

4. Verificamos la ruta remota
```
git remote -v
``` 

5. Creamos 3 archivos "foo.txt" "bar.txt" y "qux.txt" y hacemos push, (revisamos el repositorio remoto) 

6. Ahora eliminamos a "foo.txt"
```
git rm --cached foo.txt
```

7. Verificamos el stage
```
git status
```

8. Hacemos un commit y al hacer push damos de baja el archivo "foo.txt" en el repositorio remoto
```diff
git commit -m "feat: remove foo.txt"
git push 
```

<br/>
---


## 🏆 H-8 (VOLVER A UN COMMIT ANTERIOR)


1. Crear un nuevo repositorio en github nombre: git_h_8

2. Crear un repositorio local
```
git init
```

3. Registrar el repositorio remoto con tú repositorio local
```
git remote add origin (pegar_la_ruta_del_repositorio_local)
```

4. Verificamos la ruta remota
```
git remote -v
``` 

5. Crea 5 archivos notas_1.txt, notas_2.txt etc... y por cada archivo emites un commit y su push correspondiente por cada commit
   * nota_1.txt  - commit -m "feat nota 1"
   * nota_2.txt  - commit -m "feat nota 2"
   * nota_3.txt  - commit -m "feat nota 3"
   * nota_4.txt  - commit -m "feat nota 4"
   * nota_5.txt  - commit -m "feat nota 5"

6. Ahora vamos a regresar del actual commit, al commit anterior, al commit pasado, mediante git revert 
```diff
git revert HEAD

+ Otra alternativa al mismo resultado

git revet código_del_commit_pasado
```

7. Luego si existe un conflicto solo seleccionamos lo que necesitamos, teniendo ya todo listo, se continua con el revert 
```
git revert --continue

git commit -m "feat volvimos al commit anterior"

para salir del editor :wq + enter
```

8. Revisamos el proyecto para confirmar y podemos seguir creando cosas en nuestro proyecto.

---
<h3 align="center">SOCIAL OPLESK</h3>

