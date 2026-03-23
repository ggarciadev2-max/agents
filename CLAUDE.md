# Proyecto: Agents — Python + React

## Stack técnico
- **Backend**: Python 3.11+ / FastAPI / SQLAlchemy / Pydantic / pytest
- **Frontend**: React 18 / TypeScript / Vite / Tailwind CSS
- **Base de datos**: PostgreSQL
- **Auth**: JWT con refresh tokens
- **Logs**: `loguru` en backend; `console.log` solo en desarrollo en frontend

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

## Convenciones de código
- **Backend**: usa Pydantic para validar requests y responses. Lógica de negocio en servicios, no en handlers.
- **Frontend**: componentes funcionales con hooks. Props siempre tipadas con TypeScript.
- **Tests**: pytest + httpx para backend; Vitest + React Testing Library para frontend.
- **Commits**: sigue Conventional Commits (`feat:`, `fix:`, `chore:`, `docs:`, etc.).

## Archivos sensibles — NO leer ni modificar
- `.env`, `.env.local`, `.env.*.local`
- Cualquier archivo que contenga `SECRET`, `TOKEN`, `PASSWORD`, `API_KEY`
- No ejecutar comandos que modifiquen la base de datos en producción sin confirmación explícita.
