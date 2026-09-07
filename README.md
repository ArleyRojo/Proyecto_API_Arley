# TODO API - Proyecto Formativo (SENA ADSO)

## Descripción
API REST para gestión de tareas, desarrollada en **Python con Flask** y **PostgreSQL**, contenerizada con Docker y desplegada en **Render**. Incluye además un tablero web sencillo (`/app`) para crear, completar y eliminar tareas desde el navegador.

**Demo en producción:** https://proyecto-api-arley.onrender.com/app

## Tecnologías
- Python 3.9
- Flask
- Flask-SQLAlchemy
- PostgreSQL
- Docker
- Docker Compose
- Render (despliegue)

## Estructura del proyecto
```
proyecto-todo-api/
├── src/
│   ├── app.py
│   └── templates/
│       └── index.html
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
└── README.md
```

## Instalación local (sin Docker)
```bash
git clone https://github.com/ArleyRojo/Proyecto_API_Arley.git
cd proyecto-todo-api
python -m venv venv
venv\Scripts\activate        # Windows
pip install -r requirements.txt
python src/app.py
```
Por defecto usa SQLite (`sqlite:///tasks.db`) si no defines la variable `DATABASE_URL`.

## Despliegue con Docker Compose (recomendado)
Levanta la API y la base de datos PostgreSQL juntas:
```bash
docker-compose up -d --build
```
Verificar que los contenedores quedaron activos:
```bash
docker-compose ps
```

La aplicación queda disponible en:
- API: http://localhost:5000
- Tablero web: http://localhost:5000/app

## Variables de entorno
| Variable | Descripción | Valor por defecto |
|---|---|---|
| `DATABASE_URL` | Cadena de conexión a PostgreSQL | `sqlite:///tasks.db` |
| `PORT` | Puerto en el que corre la aplicación | `5000` |

## Endpoints de la API
| Método | Endpoint | Body (JSON) | Descripción |
|---|---|---|---|
| GET | `/` | - | Redirige al tablero (`/app`) |
| GET | `/app` | - | Interfaz web del tablero de tareas |
| GET | `/api/tasks` | - | Listar todas las tareas |
| GET | `/api/tasks/<id>` | - | Obtener una tarea por ID |
| POST | `/api/tasks` | `{"title": "...", "description": "..."}` | Crear una tarea |
| PUT | `/api/tasks/<id>` | `{"title": "...", "completed": true}` | Actualizar una tarea |
| DELETE | `/api/tasks/<id>` | - | Eliminar una tarea |

## Despliegue en producción
El proyecto está conectado al repositorio de GitHub y se despliega automáticamente en Render con cada `git push` a la rama `main`.

- **URL:** https://proyecto-api-arley.onrender.com
- **Plataforma:** Render (plan gratuito)
- **Base de datos:** PostgreSQL gestionada por Render

## Autor
**Arley Rojo** — Análisis y Desarrollo de Software (ADSO), SENA