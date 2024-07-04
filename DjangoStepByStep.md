# Estructura recomendada:

myproject/
├── manage.py
├── myproject/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
└── myapp/
    ├── __init__.py
    ├── admin.py
    ├── apps.py
    ├── migrations/
    ├── models.py
    ├── tests.py
    ├── views.py
    └── urls.py

# 1. Crear un Proyecto Django
'''django-admin startproject myproject
cd myproject'''

# 2. Crear una Aplicación Django
python manage.py startapp myapp

# 3. Registrar la Aplicación en settings.py
'''# myproject/settings.py

INSTALLED_APPS = [
    ...
    'myapp',
]

# Agregar configuración para archivos estáticos y media
import os

STATIC_URL = '/static/'
STATICFILES_DIRS = [os.path.join(BASE_DIR, "static")]

MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, "media")'''

# 4. Crear Directorios para Templates y Archivos Estáticos
Dentro de tu aplicación, crea las carpetas templates, static, y media:

'''mkdir -p myapp/templates/myapp
mkdir -p myapp/static/myapp/css
mkdir -p myapp/static/myapp/images
mkdir -p media/products
'''

# 5. Crear Templates con Header y Footer
Ejemplo de un template base con header y footer:

'''<!-- myapp/templates/myapp/base.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>{% block title %}My Site{% endblock %}</title>
    <link rel="stylesheet" href="{% static 'myapp/css/header.css' %}">
    <link rel="stylesheet" href="{% block css %}{% endblock %}">
</head>
<body>
    <header>
        <h1>Header Content</h1>
    </header>

    {% block content %}{% endblock %}

    <footer>
        <p>Footer Content</p>
    </footer>
</body>
</html>
'''
Ejemplo de un template específico que hereda del base:

'''<!-- myapp/templates/myapp/home.html -->
{% extends "myapp/base.html" %}

{% block title %}Home{% endblock %}

{% block css %}
<link rel="stylesheet" href="{% static 'myapp/css/home.css' %}">
{% endblock %}

{% block content %}
<h2>Welcome to the Home Page</h2>
<p>This is the body content of the home page.</p>
{% endblock %}
'''

# 6. Crear Vistas Basadas en Funciones con render

'''# myapp/views.py
from django.shortcuts import render

def home(request):
    return render(request, 'myapp/home.html')

def product_view(request):
    return render(request, 'myapp/product.html')
'''

# 7. Configurar las URLs de la Aplicación

'''# myapp/urls.py
from django.urls import path
from .views import home, product_view

urlpatterns = [
    path('', home, name='home'),
    path('product/', product_view, name='product'),
]
'''

# 8. Incluir las URLs de la Aplicación en el Proyecto

'''# myproject/urls.py
from django.contrib import admin
from django.urls import path, include
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    path('myapp/', include('myapp.urls')),
]

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
'''

# 9. Crear Archivos CSS

'''/* myapp/static/myapp/css/header.css */
header {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 1em;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 1em;
}

/* myapp/static/myapp/css/home.css */
h2 {
    color: blue;
}
'''

# 10. Ejecutar el Servidor de Desarrollo

'''python manage.py runserver'''

# 11. Acceder a las Vistas en el Navegador

'''Home Page: http://127.0.0.1:8000/myapp/
Product Page: http://127.0.0.1:8000/myapp/product/'''
