# Instrucciones para correr la App *Bazar Vintage*

### Crear una carpeta

### Clonar el repositorio desde GitHub en la carpeta creada
```git clone https://github.com/AndresQ-Dev/BazarVintageDjango.git```

### Crear un entorno virtual en la misma carpeta
```python -m venv env```

### Mover la carpeta env dentro de BazarVintageDjango

### Cambiar directorio a BazarVintageDjango
```cd BazarVintageDjango```

### Activar el entorno virtual
```source env/bin/activate (MacOS o Linux)```

```env/Scripts/activate (Windows)```

#### Instalar las dependencias del proyecto desde el archivo requirements.txt
```pip install -r requirements.txt```

### Realizar las migraciones de la base de datos
```python manage.py makemigrations```

```python manage.py migrate```

### Crear un usuario administrador para la base de datos
```python manage.py createsuperuser```

### Crear la estructura de carpetas para las imágenes en "core"
```core/media/products```

### Colocar la imagen por defecto que tendránen los productos en la carpeta _*products*_

Debe tener el siguiente nombre: 
```"default_image.jpg"```

### Correr el servidor
```python manage.py runserver```

## :::ENJOY:::
