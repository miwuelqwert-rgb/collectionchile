# ColectionsChile — React + Django

Catálogo editorial para publicar **colecciones y perfumes**. El frontend está hecho con React + Vite y consume una API REST de Django REST Framework. Los productos se administran desde Django Admin.

## Requisitos
- Node.js 20+
- Python 3.11+

## 1. Backend Django
```bash
cd backend
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```
API: http://127.0.0.1:8000/api/items/  
Administración: http://127.0.0.1:8000/admin/

En el admin crea y publica elementos marcando **Publicado**. Tipo disponible: Colección o Perfume.

## 2. Frontend React
En otra terminal:
```bash
cd frontend
npm install
npm run dev
```
Abre la URL que muestre Vite (normalmente http://localhost:5173).

La API por defecto es `http://127.0.0.1:8000/api`. Puedes cambiarla con `VITE_API_URL`.

## Funciones
- Catálogo adaptable a móviles y escritorio.
- Filtros por Colecciones y Perfumes.
- Búsqueda por nombre, marca, categoría y descripción.
- Tarjetas con imagen, precio opcional, estado y descripción.
- Django Admin para crear, editar, publicar u ocultar entradas.
- API pública de solo lectura para entradas publicadas; escritura protegida por el panel de administración de Django.

Nota: proyecto base listo para desarrollo local. Antes de desplegar, configura `DEBUG=False`, `SECRET_KEY`, `ALLOWED_HOSTS`, HTTPS y una base de datos de producción.
