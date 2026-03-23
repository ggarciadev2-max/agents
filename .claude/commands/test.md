---
description: Ejecuta los tests del proyecto
argument-hint: [backend|frontend|all]
---

Ejecuta los tests para $ARGUMENTS.

- Si es `backend`: ejecuta `cd backend && poetry run pytest -v`
- Si es `frontend`: ejecuta `cd frontend && npm run test -- --run`
- Si es `all`: ejecuta ambos en orden.

Al finalizar, presenta un resumen:
- ✅ Tests pasados / ❌ Tests fallados
- Si hay fallos, analiza los errores y sugiere posibles causas y soluciones.
- Si la cobertura está disponible, indícala y señala las áreas con baja cobertura.
