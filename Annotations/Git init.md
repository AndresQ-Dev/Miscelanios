<div style="background-color: lightblue; padding: 10px; border-radius: 30px;">

# Opciones generales de Git


## Introducir usuario
```git config --global user.name "pepito"```

## Introducir @mail
```git config --global user.email pepito@gmail.com```

## Configura editor por default
```git config --global core.editor "code --wait"```

## Ver Opciones globales guardadas
```git config --global -e```

## Configuración de CRLF 
#### "input" para MacOS o Linux y "true" para windows
```git config --global core.autocrlf input```

## Mostrar Opciones de Git
```git config -h```


# Inicializar Proyecto en Git
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
* entrar a la carpeta del proyecto en Git local y colocar el siguiente comando con el URL:
  * ```git remote add origin https://github.com/...```

```git push -u origin main```




</div>