# Tutorial de Django

Proyecto de aprendizaje con una aplicación de encuestas (`polls`), votación,
resultados y personalización del administrador de Django.

## Ejecutar localmente

Desde esta carpeta, con Python y pip instalados:

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

La base de datos local no se incluye en Git; las migraciones crean una nueva.
La configuración usa `DJANGO_SECRET_KEY` si está definida; en caso contrario
genera una clave temporal al iniciar. Para conservar las sesiones entre reinicios,
define una clave estable en esa variable de entorno. La configuración actual
está preparada para desarrollo local (`DEBUG = True`).

## Pruebas

```powershell
python manage.py test
```
