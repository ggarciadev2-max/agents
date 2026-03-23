# Reglas generales (aplican siempre)

- Escribe código simple y legible. Evita sobre-ingeniería.
- Cada cambio debe afectar la menor cantidad de código posible.
- Antes de implementar, explica brevemente el plan.
- Sigue las convenciones del proyecto definidas en CLAUDE.md.
- No dejes `TODO` sin registrar en `tasks/todo.md`.
- Usa variables de entorno para cualquier valor sensible. Nunca hardcodees secrets.
- Valida siempre las entradas del usuario (XSS, SQLi, input malicioso).
- Revisa seguridad antes de cada commit:
  - ¿Hay datos sensibles expuestos?
  - ¿Las APIs están protegidas?
  - ¿Los formularios validan entradas?
