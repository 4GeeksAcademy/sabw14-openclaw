---
name: task-to-calendar
description: Revisa mis Google Tasks pendientes sin horario asignado y crea automáticamente bloques de tiempo en Calendar para ellas.
user-invocable: true
---

# Tarea → Calendar

## Cuándo se usa
El usuario pide algo como "organiza mis tareas" o "agéndame las tareas pendientes".
No necesita listar las tareas manualmente — la skill las lee directo de Google Tasks.

## Antes de actuar
1. Lee `TOOLS.md` para identificar: qué lista de Google Tasks es la relevante,
   el calendario por defecto, y la duración estándar a usar por tarea si el
   usuario no la especifica (ej. 30 o 60 minutos).
2. Lee `USER.md` para conocer el horario habitual de trabajo/estudio del usuario
   — los bloques nuevos deben caer dentro de ese rango, nunca de madrugada ni en
   horarios que el usuario no usa.
3. Si el usuario no indica cuántos días hacia adelante mirar, usa por defecto
   los próximos 7 días.

## Qué hacer
1. Lista las tareas pendientes (no completadas) de la lista de Google Tasks
   configurada.
2. Filtra las que **no** tengan ya un evento de Calendar asociado o un bloque de
   tiempo reconocible (evita duplicar si ya se agendaron antes).
3. Para cada tarea sin horario, crea un evento en el calendario por defecto:
   - Título: el mismo texto de la tarea (o una versión clara si es muy larga).
   - Duración: la especificada en la tarea si existe, si no la estándar de
     `TOOLS.md`.
   - Ubicación temporal: el primer hueco libre disponible dentro del horario
     habitual del usuario, dentro del rango de días a considerar.
4. Si hay más tareas que huecos libres disponibles en el rango, prioriza por
   fecha de vencimiento de la tarea (si existe) y avisa al usuario cuáles
   quedaron sin agendar.
5. Reporta al usuario cuántos bloques creó y para qué tareas, con sus horarios.

## Cómo saber que funcionó
Cada tarea pendiente sin horario previo ahora tiene un evento correspondiente en
Calendar, dentro del horario habitual del usuario, y el número de bloques creados
coincide con lo que el agente reportó.
