---
description: Analiza y corrige un issue específico del proyecto
argument-hint: [descripción del problema o número de issue]
---

Analiza y corrige el siguiente problema: $ARGUMENTS

Proceso a seguir:
1. **Entender**: lee el issue y reproduce el problema mentalmente.
2. **Investigar**: busca los archivos relevantes con Grep/Glob.
3. **Planear**: explica brevemente qué cambios harás y por qué.
4. **Implementar**: realiza el cambio más simple que resuelva el problema.
5. **Verificar**: ejecuta los tests relacionados para confirmar que el fix funciona.
6. **Documentar**: actualiza `tasks/todo.md` con el trabajo realizado.

Regla: haz el cambio mínimo necesario. Evita cambios colaterales no relacionados.
