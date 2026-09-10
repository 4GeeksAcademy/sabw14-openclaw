---
name: github-daily-digest
description: Lee issues abiertos y commits recientes de mis repos de GitHub y envía un briefing breve por Telegram.
user-invocable: true
---

# Resumen diario de GitHub por Telegram

## Cuándo se usa
El usuario activa esta skill (ej. "dame el resumen de GitHub", o mediante un
disparador programado) sin necesidad de dar más detalles la mayoría de las veces.

## Antes de actuar
1. Lee `TOOLS.md` para identificar: qué repos sigue el usuario habitualmente por
   defecto, y a qué chat/canal de Telegram debe enviarse el resumen.
2. Si el usuario no especifica un repo distinto, usa los repos por defecto de
   `TOOLS.md`. Si `TOOLS.md` no tiene ningún repo configurado, pregunta al
   usuario cuál(es) repo(s) revisar antes de continuar.
3. El rango de tiempo por defecto es "últimas 24 horas", salvo que el usuario
   pida otro (ej. "de esta semana").

## Qué hacer
1. Para cada repo relevante, obtén:
   - Issues abiertos nuevos o actualizados en el rango de tiempo.
   - Commits realizados en el rango de tiempo (mensaje + autor si es relevante).
2. Redacta un mensaje breve y accionable (tono de `SOUL.md`: directo, sin relleno),
   con esta estructura aproximada:

   📋 Resumen GitHub — <fecha>
   
   <repo>: N issues abiertos, M commits
   
   Issues a revisar:
   
   - <título> (<link>)
   
   Commits recientes:
   
   - <mensaje corto> — <autor>

   
   Si no hay novedades en un repo, dilo explícitamente ("sin cambios en las
   últimas 24h") en vez de omitirlo silenciosamente.
3. Envía el mensaje por Telegram al chat/canal configurado en `TOOLS.md`.

## Cómo saber que funcionó
El usuario recibe el mensaje en Telegram, y los números/issues/commits que
reporta coinciden con lo que se ve directamente en GitHub para ese repo y rango
de tiempo.
