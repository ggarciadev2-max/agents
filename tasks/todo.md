# Plan de trabajo: Configuración Claude Code

## Tareas

- [x] Crear `tasks/todo.md` con el plan
- [x] Crear `.gitignore`
- [x] Crear `CLAUDE.md` principal
- [x] Crear `CLAUDE.local.md.example`
- [x] Crear `.claude/settings.json`
- [x] Crear reglas modulares (`rules/`)
- [x] Crear comandos slash (`commands/`)
- [x] Crear sub-agentes (`agents/`)

## Revisión

### Resumen de cambios
Se configuró la estructura completa de Claude Code para el proyecto Python + React:
- `CLAUDE.md`: instrucciones globales del proyecto (stack, comandos, convenciones, seguridad).
- `.claude/settings.json`: permisos allow/deny para que el agente opere de forma segura.
- `.claude/rules/`: reglas modulares separadas por contexto (general, backend, frontend).
- `.claude/commands/`: comandos slash personalizados para tareas repetitivas.
- `.claude/agents/`: sub-agentes especializados para backend (Python) y frontend (React).
- `.gitignore`: ignora archivos locales, `.env` y configuraciones personales.

### Notas de seguridad
- Los archivos `.env` y `CLAUDE.local.md` están en `.gitignore`.
- El `settings.json` deniega explícitamente la lectura de archivos con secrets.
- No hay claves ni tokens hardcodeados en ningún archivo.
