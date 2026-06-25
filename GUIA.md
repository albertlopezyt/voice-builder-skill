# Guía de instalación y uso · Voice Builder

Repositorio de GitHub:

```text
https://github.com/albertlopezyt/voice-builder-skill
```

Guía visual incluida en `index.html`.

## Qué vas a instalar

Voice Builder es una skill para Codex o Claude Code que convierte tu criterio de comunicación en dos archivos reutilizables:

- `about-me.md`: quién eres, a quién hablas, qué defiendes, qué temas tratas y qué temas evitas.
- `voice.md`: cómo escribes, qué tono usas, cómo abres, cómo cierras, qué palabras repites y qué patrones quieres evitar.

Después, cualquier agente puede leer esos dos archivos antes de escribir posts, emails, guiones, newsletters, páginas web o mensajes comerciales.

## Requisitos

Necesitas una de estas herramientas:

- Claude Code.
- Codex.

Y acceso básico a terminal para copiar una carpeta.

## Paso 1. Descargar el repo

Opción fácil:

1. Abre el repo de GitHub.
2. Pulsa `Code`.
3. Pulsa `Download ZIP`.
4. Descomprime el archivo.

Opción terminal:

```bash
git clone https://github.com/albertlopezyt/voice-builder-skill
cd voice-builder-skill
```

Si has descargado el ZIP, entra en la carpeta descomprimida desde la terminal.

## Paso 2. Instalar la skill

Si usas Claude Code:

```bash
mkdir -p ~/.claude/skills
cp -R voice-builder ~/.claude/skills/
```

Si usas Codex:

```bash
mkdir -p ~/.codex/skills
cp -R voice-builder ~/.codex/skills/
```

Si quieres instalarla solo dentro de un proyecto concreto, copia la carpeta en la ruta local del proyecto.

Para Claude Code:

```bash
mkdir -p ./.claude/skills
cp -R voice-builder ./.claude/skills/
```

Para Codex:

```bash
mkdir -p ./.codex/skills
cp -R voice-builder ./.codex/skills/
```

Después de copiarla, cierra y vuelve a abrir tu sesión de agente.

## Paso 3. Arrancar Voice Builder

En una conversación nueva con tu agente, escribe:

```text
Use $voice-builder to build my voice profile.
```

También puedes escribirlo en español:

```text
Usa $voice-builder para construir mi perfil de voz.
```

La skill te pedirá una entrevista en bloque. Responde copiando los códigos:

```text
1a. ...
1b. ...
1c. ...
2a. ...
```

Si una pregunta no aplica, escribe `na`.

## Paso 4. Dar muestras de escritura

Después de la entrevista, la skill te pedirá entre 3 y 5 muestras escritas por ti o por tu marca.

Sirven:

- Posts de LinkedIn.
- Newsletters.
- Emails a clientes.
- Textos de tu web.
- Guiones de vídeo.
- Transcripciones.
- Mensajes internos donde se vea tu forma natural de explicar.

Cuanto más parecidas sean a lo que quieres generar después, mejor.

## Paso 5. Revisar los archivos creados

La skill creará una carpeta parecida a esta:

```text
voice-profiles/mi-marca/
  about-me.md
  voice.md
```

`about-me.md` guarda el criterio de identidad y posicionamiento.

`voice.md` guarda las reglas de voz y estilo.

Estos dos archivos son la memoria que usarán otros agentes para escribir con más criterio.

## Paso 6. Usar tu voz en otros trabajos

Cuando quieras generar contenido con tu voz, dile al agente que lea esos archivos primero.

Ejemplo para escribir un post:

```text
Lee voice-profiles/mi-marca/about-me.md y voice-profiles/mi-marca/voice.md.
Después escribe un post de LinkedIn sobre [tema] respetando esa voz.
```

Ejemplo para revisar un texto:

```text
Lee voice-profiles/mi-marca/about-me.md y voice-profiles/mi-marca/voice.md.
Después revisa este texto y dime qué no encaja con mi voz:

[pega aquí el texto]
```

Ejemplo para sacar ideas:

```text
Lee voice-profiles/mi-marca/about-me.md y voice-profiles/mi-marca/voice.md.
Después dame 20 ideas de contenido que encajen con mis temas, mi punto de vista y mi tono.
```

Ejemplo para adaptar un email:

```text
Lee voice-profiles/mi-marca/about-me.md y voice-profiles/mi-marca/voice.md.
Después reescribe este email para que suene como yo:

[pega aquí el email]
```

## Qué no hace esta skill

Voice Builder no crea por sí sola un calendario completo de contenido, una newsletter, un sistema de ventas o una base de datos de ideas.

Lo que crea es el cimiento: dos documentos que otros agentes pueden leer para mantener tu voz y criterio.

## Problemas frecuentes

Si el agente no detecta `$voice-builder`, revisa tres cosas:

1. La carpeta `voice-builder` está dentro de `~/.claude/skills` o `~/.codex/skills`.
2. Dentro de `voice-builder` existe el archivo `SKILL.md`.
3. Has cerrado y vuelto a abrir la sesión del agente después de instalarla.

Si no tienes 3 muestras de escritura, usa lo que tengas:

- Mensajes largos que hayas enviado.
- Emails.
- Notas.
- Transcripciones de audios o vídeos.
- Textos publicados en tu web.

Si quieres que la voz sea para una empresa y no para una persona, responde la entrevista como marca y usa muestras escritas por esa marca.
