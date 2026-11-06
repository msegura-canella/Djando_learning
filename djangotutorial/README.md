# Tutorial de Django: capítulos 1 al 7

Proyecto de aprendizaje con una aplicación de encuestas (`polls`), votación,
resultados y personalización del administrador de Django. Sigue los capítulos
1 al 7 del tutorial oficial «Writing your first Django app» de Django 6.1.

## Contenido del tutorial

| Capítulo | Tema |
| --- | --- |
| [1](https://docs.djangoproject.com/en/6.1/intro/tutorial01/) | Crear el proyecto, la aplicación `polls`, vistas y rutas. |
| [2](https://docs.djangoproject.com/en/6.1/intro/tutorial02/) | Base de datos, modelos, migraciones y administrador. |
| [3](https://docs.djangoproject.com/en/6.1/intro/tutorial03/) | Vistas, plantillas y nombres de rutas. |
| [4](https://docs.djangoproject.com/en/6.1/intro/tutorial04/) | Formularios, votación y vistas genéricas. |
| [5](https://docs.djangoproject.com/en/6.1/intro/tutorial05/) | Pruebas automatizadas de modelos y vistas. |
| [6](https://docs.djangoproject.com/en/6.1/intro/tutorial06/) | Archivos estáticos: estilos e imágenes. |
| [7](https://docs.djangoproject.com/en/6.1/intro/tutorial07/) | Personalizar formularios, listados y plantillas del administrador. |

## Ejecutar localmente

Necesitas Python, pip y Git instalados. El proyecto usa la versión de Django
indicada en `requirements.txt`.

Para descargarlo desde cero:

```powershell
git clone https://github.com/msegura-canella/Djando_learning.git
cd Djando_learning/djangotutorial
```

Si ya tienes el proyecto, abre una terminal en la carpeta `djangotutorial`,
donde está `manage.py`. Luego, en Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Encuestas: http://127.0.0.1:8000/polls/

Administración: http://127.0.0.1:8000/admin/

## Cómo usar la aplicación

1. Entra al administrador con el usuario creado mediante `createsuperuser`.
2. En `Questions`, crea una pregunta con una fecha de publicación actual o pasada.
3. Agrega sus opciones de respuesta (`Choices`) y guarda los cambios.
4. Abre `/polls/`, selecciona la pregunta y vota por una opción.
5. Consulta los resultados después de votar.

Una base de datos nueva no contiene encuestas; debes crearlas en el administrador.
Las preguntas con fecha futura no aparecen en el listado de encuestas.
Para detener el servidor, presiona `Ctrl+C`. Para iniciarlo otra vez, activa
el entorno virtual y ejecuta `python manage.py runserver`.

## Configuración local

La base de datos local no se incluye en Git; las migraciones crean una nueva.
La configuración usa `DJANGO_SECRET_KEY` si está definida; en caso contrario
genera una clave temporal al iniciar. Para conservar las sesiones entre reinicios,
define una clave estable en esa variable de entorno. La configuración actual
está preparada para desarrollo local (`DEBUG = True`).

## Pruebas

```powershell
python manage.py test
```
