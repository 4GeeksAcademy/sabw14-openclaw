---
name: daily-learning-journal
description: Formatea lo aprendido hoy y lo añade como entrada nueva al Google Doc que uso como diario de conocimiento personal.
user-invocable: true
---

# Diario de aprendizaje diario

## Cuándo se usa
El usuario te va a dar, en 2-4 líneas de texto libre, lo que aprendió hoy (puede
incluir tema, dificultad, algo que no entendió, o un logro). Puede venir como
lista, párrafo suelto o mensaje de voz transcrito. No esperes un formato fijo.

## Antes de actuar
1. Lee `USER.md` para tener contexto de en qué bootcamp/proyecto está trabajando
   el usuario ahora mismo — úsalo para dar contexto a la entrada si el usuario
   no lo menciona explícitamente.
2. Lee `TOOLS.md` para identificar cuál es el Google Doc designado como "diario
   de aprendizaje" (nombre o ID) y en qué carpeta de Drive vive.
3. Si `TOOLS.md` no especifica un documento de diario, **detente y pregunta**
   al usuario cuál Google Doc usar antes de crear o tocar nada — no inventes uno
   ni crees un documento nuevo sin confirmar (regla de `AGENTS.md`).

## Qué hacer
1. Toma el input del usuario y estructura una entrada con este formato exacto:

### <YYYY-MM-DD> — <tema en 3-6 palabras>

**Qué aprendí**

- punto 1
- punto 2
- ...

**Dudas / próximos pasos**

- (solo si el usuario mencionó una duda o algo pendiente; si no, omite esta sección)


2. Usa la fecha de hoy (zona horaria del usuario, ver `TOOLS.md`/`USER.md`).
3. Redacta con el tono definido en `SOUL.md` — sin relleno, directo, en la voz
   del agente, no una transcripción literal del usuario.
4. Abre el Google Doc del diario y **añade** esta entrada al final del documento.
   Nunca sobrescribas ni borres contenido existente — solo agregar (regla dura
   de `AGENTS.md`: nunca destruir contenido del usuario sin confirmación).
5. Confirma al usuario en el chat (o Telegram si así lo pidió) con una frase
   corta: qué se agregó y un link o referencia al documento.

## Cómo saber que funcionó
El usuario puede abrir el Google Doc y ver la entrada nueva al final, con las
entradas anteriores intactas, y la fecha y el tema coinciden con lo que reportó
el agente.
