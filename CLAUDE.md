# Proyecto: Agents — Python + React

## Descripción del proyecto
Aplicación fullstack para gestión de agentes autónomos. El backend expone
a API REST con autenticación JWT; el frontend consume esa API con React.

## Stack técnico
- **Backend**: Python 3.11+ / FastAPI / SQLAlchemy 2.x async / Pydantic v2 / pytest
- **Frontend**: React 18 / TypeScript strict / Vite / Tailwind CSS
- **Base de datos**: PostgreSQL
- **Auth**: JWT con refresh tokens, bcrypt para hashing
- **Logs**: `loguru` en backend; `console.log` solo en desarrollo en frontend
- **Linter/Formatter**: `ruff` (backend), ESLint (frontend)

## Estructura de directorios
```
backend/
├── routers/      # Endpoints FastAPI (handlers delgados)
├── services/     # Lógica de negocio
├── models/       # Modelos SQLAlchemy
├── schemas/      # Schemas Pydantic (request/response)
├── core/         # Config, deps, seguridad (JWT, bcrypt)
└── tests/        # pytest + httpx

frontend/
├── src/
│   ├── components/   # Componentes React reutilizables
│   ├── hooks/        # Custom hooks (useXxx.ts)
│   ├── store/        # Estado global (Zustand)
│   ├── api/          # Clientes de API (React Query)
│   └── types/        # Interfaces y tipos TypeScript
└── tests/
```

## Comandos de desarrollo

### Backend
```bash
cd backend && poetry run uvicorn main:app --reload   # Servidor de desarrollo
cd backend && poetry run pytest -v                   # Tests
cd backend && poetry run ruff check .                # Linter
```

### Frontend
```bash
cd frontend && npm run dev      # Servidor de desarrollo
cd frontend && npm run test     # Tests (Vitest)
cd frontend && npm run build    # Build de producción
cd frontend && npm run lint     # Linter (ESLint)
```

## Sub-agentes disponibles

| Agente | Cuándo usarlo |
|---|---|
| `python-expert` | Endpoints, servicios, modelos DB, auth, tests de backend |
| `react-expert`  | Componentes, hooks, estado global, formularios, tests de frontend |

## Convenciones de código
- **Backend**: usa Pydantic v2 para validar requests y responses. Lógica de negocio en servicios (`services/`), no en handlers.
- **Frontend**: componentes funcionales con hooks. Props siempre tipadas con TypeScript. Sin `any`.
- **Tests**: pytest + httpx para backend; Vitest + React Testing Library para frontend.
- **Commits**: sigue Conventional Commits (`feat:`, `fix:`, `chore:`, `docs:`, etc.).

## Decisiones de arquitectura (ADRs)
- **Poetry sobre pip**: lock file reproducible, grupos de dependencias (dev/prod).
- **ruff sobre flake8+black**: más rápido, unifica linting y formatting en un solo tool.
- **Zustand sobre Redux**: menos boilerplate para el tamaño de este proyecto.
- **React Query sobre fetch manual**: maneja caché, loading y error states de forma declarativa.
- **Vite sobre CRA**: arranque instantáneo, HMR más rápido.
- **SQLAlchemy async**: no bloquea el event loop de FastAPI.

## Archivos sensibles — NO leer ni modificar
- `.env`, `.env.local`, `.env.*.local`
- Cualquier archivo que contenga `SECRET`, `TOKEN`, `PASSWORD`, `API_KEY`
- No ejecutar comandos que modifiquen la base de datos en producción sin confirmación explícita.