> # Inicialización y Uso de Git / GitHub


### Introducir usuario
```git config --global user.name "pepito"```

### Introducir @mail
```git config --global user.email pepito@gmail.com```

### Configura editor por default
```git config --global core.editor "code --wait"```

### Ver Opciones globales guardadas
```git config --global -e```

### Configuración de CRLF 
##### "input" para MacOS o Linux y "true" para windows
```git config --global core.autocrlf input```

### Mostrar Opciones de Git
```git config -h```

***
># Inicializar Proyecto en Git
### Local
```git init```

```git branch -M main```

```git add .``` 

```git add archivo1 archivo2 ...```

```git commit -m "descripción del commit..."```

```git status```

### GitHub
* Crear un nuevo proyecto en la Web de GitHub.
* Copiar el URL del nuevo proyecto.
* Entrar a la carpeta del proyecto en Git local y colocar el siguiente comando con el URL:
  * ```git remote add origin https://github.com/...```
* Luego de hacer commit colocar el siguiente comando para subir al repositorio online el estado del proyecto local:
  * ```git push -u origin master```

<br>

> # Comandos Comunes de Git
#### ```git init``` 
"Crea un nuevo repositorio local de Git. Puedes ejecutar este comando en el directorio actual para iniciar un repositorio o especificar un nombre de proyecto para crear un repositorio en un directorio nuevo."

---

#### ```git clone```
"Copia un repositorio. Si el repositorio está en un servidor remoto, utiliza ```git clone urlDelRepositorio```"

---

#### ```git add```
"Agrega archivos al área de preparación (staging). Por ejemplo, para indexar el archivo temp.txt, utiliza git add temp.txt. Para agregar todos los archivos utiliza el "." ````git add .``"

---

#### ```git commit```
"Crea una instantánea de los cambios y la guarda en el directorio Git. Acompaña tu commit con un mensaje descriptivo: git commit -m "Mensaje del commit aquí"

---

#### ```git status```
"Muestra la lista de archivos modificados, así como los archivos que están por ser preparados o confirmados."

---

#### ```git push -u origin main``` 
"Envía tus cambios confirmados al repositorio remoto. Si tu rama no es la "main" utiliza: ```git push -u origin nombreDeLaRama```"

---

#### ```git branch ```
"Lista las ramas disponibles"
* ```git branch nombreDeLaRama``` "crea una rama con el nombre indicado."
* ```git branch -d nombreDeLaRama``` "elimina la rama indicada."

---

#### ```git switch nombreDeLaRama```
"Cambia a la rama indicada."

---

#### ```git pull```
"Descarga los cambios del repositorio remoto y los fusiona con tu rama local."

---

#### ```git merge nombreDeLaRama```
"Fusiona cambios de una rama indicada con la actual."

---

#### ```git log```
"Muestra el historial de commits."

---

#### ```git fetch```
"Verifica cambios en la versión de GitHub sin fusionarlos con la rama local."

---

#### ```git checkout -- <nombre_del_archivo_o_directorio>```
"Este comando sobrescribirá los cambios no confirmados en el directorio de trabajo con la versión más reciente del archivo o directorio tal como está en el último commit (HEAD)."

---

#### ```git reset --hard HEAD```
"Descarta todos los cambios en el directorio de trabajo (Working Directory)y vuelve al estado del último commit. ___IRREVERSIBLE___"

---

#### ```git rm --cached <file>..." to unstage```

Borra del stage los ultimo cambios despues del último commit...

---

#### ```git checkout -b nuevaRama```

Crea la rama y se cambia a ella

---

#### ```git push origin nombre_de_la_nueva_rama```

Si se crea una rama nueva y no se hacen cambios se puede pushear directamente a github

--- 

#### ```git restore --staged archivoX.txt```

Se limpia el directorio de trabajo de los cambios a un archivo en específico.

---

#### ```git reset <hash_de_confirmacion>```

Retroceder a una confirmación anterior con el número de hash

---

#### ```git reflog```

muestra el registro completo almacenado en el repositorio despues de eliminado con git reset --hard y muestra un hash más corto para volver atrás...

---

#### ```git checkout <hash>```

Vuelve aun estado anterior con el hash de un "git reflog" 

---

#### ```git checkout -- archivo1.txt```

revierte con cambios aún no incluidos al stage en working directory, volviendo al estado del último commit.

---

#### _I'm back_
