# TODO API - Proyecto Formativo

## Descripción
API REST para gestión de tareas, desarrollada con Python/Flask y PostgreSQL.

## Tecnologías
- Python 3.9
- Flask + Flask-SQLAlchemy
- PostgreSQL
- Docker / Docker Compose
- Render (despliegue en la nube)

## Endpoints

| Método | Endpoint             | Body (JSON)                                  | Acción         |
|--------|----------------------|-----------------------------------------------|----------------|
| GET    | /api/tasks           | -                                               | Listar tareas  |
| GET    | /api/tasks/:id       | -                                               | Ver una tarea  |
| POST   | /api/tasks           | {"title": "Mi tarea", "description": "Desc"}   | Crear tarea    |
| PUT    | /api/tasks/:id       | {"completed": true}                            | Actualizar     |
| DELETE | /api/tasks/:id       | -                                               | Eliminar       |

## Instalación local (sin Docker)

```bash
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
pip install -r requirements.txt
python src/app.py
```

## Despliegue con Docker

```bash
docker-compose up -d
docker-compose ps
docker-compose logs api
```

La API queda disponible en http://localhost:5000

## Despliegue en Producción (Render)

URL: https://todo-api-tu-nombre.onrender.com
