---
name: smart-calendar-event
description: Crea un evento completo en Calendar a partir de una descripción en lenguaje natural, resolviendo fecha, duración y recordatorio automáticamente.
user-invocable: true
---

# Eventos de Calendar más inteligentes

## Cuándo se usa
El usuario describe un evento en una frase informal, ej.: "sesión de estudio el
jueves por la tarde, dos horas, con recordatorio" o "reunión con el equipo mañana
a las 10". No espera que le pidas cada campo por separado.

## Antes de actuar
1. Lee `TOOLS.md` para: calendario por defecto, zona horaria del usuario, y qué
   significa "recordatorio estándar" si el usuario no da un tiempo específico
   (ej. "15 minutos antes").
2. Lee `AGENTS.md`/`SOUL.md` para saber cuándo detenerte a confirmar en vez de
   crear el evento directo — como mínimo, si la fecha/hora es ambigua (ej. "el
   jueves" cuando hay dos jueves posibles, o falta la hora), pregunta antes de
   crear nada. Si todo es claro, procede sin pedir confirmación extra.

## Qué hacer
1. Interpreta la frase del usuario y resuelve:
   - Título del evento (redáctalo claro, no copies la frase literal del usuario).
   - Fecha y hora de inicio (resuelve "jueves", "mañana", "por la tarde" contra
     la fecha actual y la zona horaria del usuario).
   - Duración (usa la mencionada; si no se menciona, usa 1 hora por defecto).
   - Recordatorio (usa el que pida el usuario; si dice "con recordatorio" sin
     especificar, usa el estándar definido en `TOOLS.md`).
   - Invitados, si el usuario los menciona por nombre o correo.
2. Crea el evento en el calendario por defecto indicado en `TOOLS.md`.
3. Confirma al usuario con una línea: título, fecha/hora, duración y recordatorio
   tal como quedaron creados — para que pueda detectar de inmediato si algo se
   interpretó mal.

## Cómo saber que funcionó
El evento aparece en el Calendar del usuario con el título, fecha, hora, duración
y recordatorio correctos, sin que el usuario haya tenido que especificar cada
campo manualmente.
