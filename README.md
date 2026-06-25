# Voice Builder Skill

Public, white-label skill for turning a person's or brand's communication style into two reusable files:

- `about-me.md`: identity, audience, topics, positioning, boundaries.
- `voice.md`: tone, rhythm, vocabulary, structure, rules, absences.

Agents can load those files before writing posts, emails, scripts, web copy, newsletters, proposals, or internal communication.

Repository:

[https://github.com/albertlopezyt/voice-builder-skill](https://github.com/albertlopezyt/voice-builder-skill)

Visual guide:

[https://albertlopezyt.github.io/voice-builder-skill/](https://albertlopezyt.github.io/voice-builder-skill/)

For a Spanish step-by-step user guide, read [GUIA.md](GUIA.md).

## Install

Clone or download this repository. Then copy the skill folder into your local skills directory.

For Codex:

```bash
mkdir -p ~/.codex/skills
cp -R voice-builder ~/.codex/skills/
```

For Claude Code:

```bash
mkdir -p ~/.claude/skills
cp -R voice-builder ~/.claude/skills/
```

For environments that use a project-local skills folder:

```bash
mkdir -p ./.codex/skills
cp -R voice-builder ./.codex/skills/
```

Or, for a project-local Claude Code setup:

```bash
mkdir -p ./.claude/skills
cp -R voice-builder ./.claude/skills/
```

Restart your agent session after copying the folder.

## Use

Start a new agent session and invoke:

```text
Use $voice-builder to build my voice profile.
```

The skill will ask for:

1. A structured interview.
2. 3 to 5 writing samples.

It will then create:

```text
voice-profiles/{profile-slug}/about-me.md
voice-profiles/{profile-slug}/voice.md
```

Use those two files as the source of truth before generating communication for that person, company, or team.

## Files

```text
index.html
GUIA.md
README.md
LICENSE
voice-builder/
  SKILL.md
  agents/openai.yaml
  references/
    about-me-template.md
    interview-questions.md
    voice-template.md
```

## Notes

- The skill does not depend on a specific company, niche, language, or content format.
- The output should preserve the source voice, not replace it with generic AI writing rules.
- The templates are intentionally compact so other agents can load them cheaply before writing.
