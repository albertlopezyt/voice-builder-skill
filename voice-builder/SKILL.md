---
name: voice-builder
description: Build a reusable writing voice profile for a person, founder, company, executive, creator, or team. Use when the user wants to capture tone, style, editorial judgment, brand voice, messaging criteria, or communication patterns from an interview plus 3 to 5 writing samples. Produces two canonical files, about-me.md and voice.md, that other agents can read before generating content, emails, posts, web copy, scripts, or any client-facing communication.
---

# Voice Builder

Create a portable voice system from two inputs: a structured interview and 3 to 5 writing samples. The output is two Markdown files:

1. `about-me.md`: identity, audience, point of view, topics, positioning, boundaries.
2. `voice.md`: tone, rhythm, openings, closings, vocabulary, rules, absences, anti-patterns.

Default destination: `voice-profiles/{profile-slug}/`. If the user gives another folder, use that.

## Operating Rules

- Do not invent voice patterns. Extract them from repeated evidence across samples.
- Distinguish declared preference from observed behavior.
- If a section has weak evidence, write `sin patrón claro en N muestras`.
- Preserve the language variety of the user unless they request another one.
- Preserve the source author's actual style. Do not apply generic writing rules that conflict with the samples.
- Do not include proprietary company names, internal workflow names, client names, or private examples unless the user explicitly provided them for this profile.
- Keep outputs compact and operational. These files are meant to be read by other agents before generating work.

## Workflow

### Step 1. Start the Interview

Load `references/interview-questions.md` and send the 10 questions in a single plain-text message.

Use numbered labels exactly like `1a / 1b / 1c / 2a / 2b...` so the user can answer in one block. Do not use interactive forms or multiple-choice UI.

If the profile slug or destination folder is unclear, ask for it in the first line before the questions.

Close with: `Responde en bloque, copiando los códigos. Si una pregunta no aplica, escribe "na".`

Wait for the user's answer before continuing.

### Step 2. Validate the Interview

If more than two answers are missing, ask only for the missing labels. If answers remain ambiguous after one follow-up, mark the relevant field as `no resuelto` or `no declarado en entrevista` and continue.

### Step 3. Request Writing Samples

Ask for 3 to 5 pieces written by the source person or brand. Accept LinkedIn posts, newsletters, web sections, sales emails, internal messages, support replies, scripts, transcripts, or long-form articles.

Minimum: 3 samples. If the user provides 1 or 2, ask for more before analyzing. If they have none available, suggest likely sources and wait.

### Step 4. Analyze the Samples

Read every sample completely. Extract cross-sample patterns, not one-off quirks.

Voice signals:
- Average sentence and paragraph length.
- Rhythm: short fragments, long arguments, line breaks, repetition, punctuation.
- Opening patterns: data, opinion, scene, confession, question, diagnosis, contrast.
- Narrative person: first person singular, company plural, second person, observational voice.
- Tone: technical, direct, warm, ironic, calm, combative, didactic, editorial.
- Recurrent words, phrases, metaphors, and sentence constructions.
- Closing patterns: CTA, reflection, summary, question, signature, no CTA.

Structural signals:
- Typical length by format.
- Prose versus lists.
- Headers, bullets, numbering, bold, spacing.
- How sections connect.

Topic signals:
- Recurring subject areas.
- Audience assumptions.
- Beliefs the author defends.
- Topics the author avoids.

Absence signals:
- Words, punctuation, structures, hooks, tones, or formats absent from all samples.
- Generic AI-writing artifacts that are absent from the source voice.
- Formats the author appears to avoid.

### Step 5. Create `about-me.md`

Load `references/about-me-template.md`. Fill it using the interview answers only. Save it as:

`voice-profiles/{profile-slug}/about-me.md`

Use the destination requested by the user if different. Maximum 300 words.

### Step 6. Create `voice.md`

Load `references/voice-template.md`. Fill it using:

- Evidence from the writing samples.
- Explicit rules from the interview.
- Clear absences found across all samples.

Save it as:

`voice-profiles/{profile-slug}/voice.md`

Use the destination requested by the user if different. Maximum 500 words.

### Step 7. Confirm Delivery

Reply with the exact files created and one short note about how to use them:

`Voz instalada en {destination}. Antes de generar contenido para este perfil, carga about-me.md y voice.md.`

## Slug Convention

Use lowercase kebab-case without accents:

- `maria-garcia`
- `norte-ops`
- `acme-consulting`
- `founder-newsletter`

If the slug is unclear, ask once before creating files.

## Expected Output

Two Markdown files:

1. `about-me.md`: who the profile is, who they serve, topics, point of view, anti-topics, promise.
2. `voice.md`: how the voice sounds, how it structures ideas, what it says, what it avoids, and what rules future agents must follow.
