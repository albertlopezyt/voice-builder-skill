# voice.md Template

Produce a compact voice profile that future agents can load before generating content for this profile. Maximum: 500 words.

Use evidence from writing samples plus explicit rules from the interview. If evidence is weak, say so.

```markdown
# Voice Profile · {Profile Name}

> Slug: `{profile-slug}` · Built on {YYYY-MM-DD} with voice-builder from {N} samples.

## What This Voice Sounds Like

{2 to 3 plain-language sentences describing the overall voice. Example: "Senior operator voice: direct, specific, and calm. Prefers diagnosis over inspiration. Uses concrete business language and avoids hype."}

## Tone

{3 to 5 tones used consistently.}
{1 to 3 tones avoided, based on repeated absence or explicit blacklist.}

## Narrative Person

{First person singular, company plural, second person, or observational voice. State the default and when it changes.}

## Rhythm and Length

{Average sentence and paragraph length. Line-break pattern. Punctuation habits. Example: "Short paragraphs, usually 1 to 3 sentences. Frequent line breaks after a key claim. Avoids long nested sentences."}

## Opening Patterns

{3 to 5 observed opening patterns, with a short invented example for each. Mark invented examples clearly as examples, not quotes.}
{Opening types the voice avoids if there is evidence.}

## Closing Patterns

{How the voice ends. CTA, reflection, direct close, open loop, question, signature, or no CTA. Include what it avoids.}

## Own Vocabulary

{Words, phrases, metaphors, and concepts that recur in the samples or were declared in the interview.}

## Forbidden Vocabulary

{Explicit blacklist from the interview plus words or tones absent from all samples. Do not add generic bans unless they fit the evidence.}

## Typical Structure

{Lists versus prose, headers, bullets, numbering, bold, paragraph spacing, narrative arc.}

## What This Voice Never Does

{3 to 5 concrete behaviors avoided by this voice. Each item must come from the interview or from absence across samples.}

## Hard Rules for Future Agents

{Rules every future output must follow. Include only rules declared by the user, strongly evidenced by samples, or necessary to preserve the voice.}

## Exceptions

{Situations where the voice changes by channel, audience, format, or intent. If none, write "no hay excepciones declaradas".}
```

## Fill Rules

- Do not quote private samples unless the user asks. Use short invented examples when needed.
- Mark examples as examples, not source quotes.
- Do not force a polished "AI writing" style. Preserve the original voice, including quirks, if they are consistent.
- If the author uses emojis, slang, long sentences, em dashes, rhetorical questions, or informal phrasing intentionally, document how they use them instead of banning them.
- If the author never uses a pattern across all samples, list it as an absence only when useful.
- Separate `explicit rule` from `observed pattern` when there could be doubt.
