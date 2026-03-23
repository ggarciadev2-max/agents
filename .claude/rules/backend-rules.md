---
paths:
  - "backend/**/*.py"
---

# Reglas para código Python / FastAPI

- Usa `async def` para todos los endpoints que llamen a la DB o APIs externas.
- Todos los endpoints deben incluir:
  - Tipo de retorno con modelo Pydantic.
  - Manejo de errores con `HTTPException`.
- No uses `print()`; usa `logger.info()` / `logger.error()` de `loguru`.
- La lógica de negocio va en la capa de servicios (`services/`), no en los handlers.
- Usa `Depends()` para inyectar dependencias compartidas (DB session, usuario autenticado).
- Las migraciones de base de datos se manejan con Alembic. No modifiques la DB directamente.
- Escribe primero el test, luego la implementación (TDD cuando sea posible).
- Mantén la cobertura de tests por encima del 80%.
