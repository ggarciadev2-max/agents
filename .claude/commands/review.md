---
description: Revisa el código actual en busca de problemas de calidad y seguridad
argument-hint: [archivo o carpeta a revisar]
---

Realiza una revisión de código de $ARGUMENTS.

Revisa los siguientes aspectos:
1. **Seguridad**: datos sensibles expuestos, inputs sin validar, secrets hardcodeados.
2. **Calidad**: código duplicado, funciones muy largas, nombres poco descriptivos.
3. **Rendimiento**: consultas N+1, re-renders innecesarios, imports no usados.
4. **Convenciones**: cumplimiento de las reglas definidas en `.claude/rules/`.

Presenta los hallazgos organizados por severidad: 🔴 Crítico | 🟡 Advertencia | 🟢 Sugerencia.
Para cada problema, muestra: qué es, dónde está y cómo corregirlo.
