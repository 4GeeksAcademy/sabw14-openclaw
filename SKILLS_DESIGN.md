# SKILLS_DESIGN.md

Diseño de las skills personalizadas del agente, antes de cualquier implementación.
Cada skill responde tres preguntas: qué hace, qué input necesita (y qué ya sabe
gracias a los cinco archivos de `.openclaw`/`workspace`), y cómo es un buen output.

---

## 1. Diario de aprendizaje diario (`daily-learning-journal`)

**¿Qué hace esta skill?**
Convierte unos pocos puntos sobre lo que aprendí hoy en una entrada estructurada
y la añade (sin borrar las anteriores) a mi Google Doc de diario de conocimiento.

**¿Qué input necesita?**
Le doy una lista breve en lenguaje natural: tema del día, 2-4 puntos de lo aprendido,
y opcionalmente una duda o dificultad. No necesito indicar formato ni fecha.
Ya sabe, gracias a la configuración:
- Qué Google Doc es "el diario" y su ubicación en Drive (`TOOLS.md`).
- Mi contexto de bootcamp/proyectos actuales, para dar contexto a las entradas (`USER.md`).
- El tono con el que debe redactar — directo, sin relleno (`SOUL.md`).
- Que nunca debe borrar contenido existente del documento, solo añadir (`AGENTS.md`).

**¿Cómo es un buen output?**
Una nueva sección al final del documento, con fecha en formato `## YYYY-MM-DD — <tema>`,
subsecciones "Qué aprendí" y "Dudas / próximos pasos". Sé que funcionó porque abro el
Doc y veo la entrada nueva agregada al final, con las entradas previas intactas.

---

## 2. Plan de semana (`weekly-plan`)

**¿Qué hace esta skill?**
A partir de mis objetivos y compromisos de la semana, escribe un plan semanal
priorizado, lo guarda como un nuevo Google Doc y crea en Calendar los eventos
para los compromisos con hora fija.

**¿Qué input necesita?**
Una lista de objetivos/compromisos en texto libre (con o sin horario). No necesito
decir plantilla ni prioridades explícitas — el agente las infiere.
Ya sabe:
- Mi calendario por defecto y la carpeta de Drive donde van estos planes (`TOOLS.md`).
- Mi horario habitual de estudio/trabajo, para no proponer bloques fuera de rango (`USER.md`).
- Si debe preguntar antes de crear eventos o proceder directo (`SOUL.md`/`AGENTS.md`).

**¿Cómo es un buen output?**
Un Google Doc nuevo titulado `Plan semana del <fecha lunes>` con los días Lunes-Domingo
y cada ítem marcado Alta/Media/Baja prioridad, más los eventos con hora fija creados
en Calendar. Sé que funcionó porque el Doc existe en Drive y los eventos clave
aparecen en mi Calendar para esa semana.

---

## 3. Eventos de Calendar más inteligentes (`smart-calendar-event`)

**¿Qué hace esta skill?**
Traduce una descripción de evento en lenguaje natural a un evento completo y bien
formado en Calendar, sin que yo tenga que especificar cada campo.

**¿Qué input necesita?**
Una frase libre, ej. "sesión de estudio el jueves por la tarde, dos horas, con
recordatorio". No doy fecha exacta, calendario ni formato de recordatorio.
Ya sabe:
- Qué calendario usar por defecto y mi zona horaria (`TOOLS.md`).
- Qué cuenta como "recordatorio estándar" si no lo especifico (`TOOLS.md`).
- Cuándo debe confirmar conmigo antes de crear el evento si algo es ambiguo (`AGENTS.md`).

**¿Cómo es un buen output?**
Un evento en el calendario correcto, con título claro, fecha/hora interpretadas
correctamente, duración correcta y recordatorio configurado, más una confirmación
corta del agente con el resumen del evento creado. Sé que funcionó porque el evento
aparece en mi Calendar exactamente como lo describí.

---

## 4. Resumen diario de GitHub por Telegram (`github-daily-digest`)

**¿Qué hace esta skill?**
Revisa issues abiertos y commits recientes de mis repos y me manda un briefing
corto por Telegram cuando la activo.

**¿Qué input necesita?**
Nada obligatorio — al activarla, uso los repos por defecto configurados. Opcionalmente
puedo indicar un repo específico o un rango de tiempo distinto a "últimas 24h".
Ya sabe:
- Qué repos sigo habitualmente (`TOOLS.md`).
- A qué chat/canal de Telegram enviar el resumen (`TOOLS.md`).
- Qué tono usar en el mensaje — breve y accionable (`SOUL.md`).

**¿Cómo es un buen output?**
Un mensaje de Telegram con: número de issues abiertos relevantes (con links),
número de commits del período y de qué repos. Sé que funcionó porque recibo el
mensaje en Telegram con datos reales y verificables contra GitHub.

---

## 5. Tarea → Calendar (`task-to-calendar`)

**¿Qué hace esta skill?**
Revisa mis Google Tasks pendientes que no tienen bloque de tiempo asignado y crea
automáticamente eventos en Calendar para ellas.

**¿Qué input necesita?**
Nada obligatorio — se dispara con algo como "organiza mis tareas". Opcionalmente
puedo indicar cuántos días hacia adelante mirar.
Ya sabe:
- Qué lista de Google Tasks es la relevante (`TOOLS.md`).
- Calendario por defecto y duración estándar por tarea si no la especifico (`TOOLS.md`).
- Mi horario habitual de trabajo/estudio, para no agendar fuera de rango (`USER.md`).

**¿Cómo es un buen output?**
Cada tarea pendiente sin horario obtiene un bloque en Calendar dentro de mi horario
habitual, y el agente reporta cuántos bloques creó y para qué tareas. Sé que
funcionó porque los eventos aparecen en Calendar y corresponden 1:1 con las tasks
que estaban sin agendar.
