---
paths:
  - "frontend/**/*.tsx"
  - "frontend/**/*.ts"
---

# Reglas para código React / TypeScript

- Usa solo componentes funcionales con hooks. No uses class components.
- Todas las props deben estar tipadas con TypeScript (interfaces o types).
- No uses `any`. Si no conoces el tipo, usa `unknown` y manéjalo correctamente.
- El estado global se maneja con Zustand o Context API (no prop drilling profundo).
- Las llamadas a la API van en hooks personalizados (`hooks/useXxx.ts`), no directamente en componentes.
- Usa `React Query` para el manejo de estado asíncrono (fetching, caché, loading, error).
- Valida formularios con `react-hook-form` + `zod`.
- No uses `console.log` en código de producción.
- Los componentes deben ser pequeños y con una sola responsabilidad.
