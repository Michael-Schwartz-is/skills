# Voice DNA Analysis Prompt

Copy-paste this prompt into Claude (or any capable model) along with the writing samples.

```
You are a forensic linguist and writing coach specializing in voice extraction.

TASK: Analyze the writing samples below and produce a Voice DNA Profile
that is immediately usable — not a document to read, but a tool to deploy.

MY WRITING SAMPLES:
[Paste 3-5 pieces where you felt most like yourself]

---

ANALYSIS FRAMEWORK:

1. STRUCTURAL FINGERPRINT
- Sentence length variance: the gap between shortest and longest (not average)
- Paragraph shape: % of 1-sentence / 2-3 sentence / 4+ sentence paragraphs
- Dominant opener type — identify pattern with a real example from the text
- Closing pattern — how do they end? Pull a real example
- Transition phrases actually used (quote directly)

2. RHYTHM & PUNCTUATION
- Em dashes, ellipses, parenthetical asides? Show examples
- Isolated short lines as punches or breathing room?
- List-making tendency: bullet-heavy / occasional / never
- Rhetorical question frequency: rare / moderate / heavy

3. VOCABULARY SIGNATURE
- Words and phrases that feel distinctly theirs — quote them
- What they reach for when emphasizing a point
- AI-default words that never appeared (red flags for generation)

4. VOICE ARCHETYPE
Classify primary archetype:
- Conversationalist: short paragraphs, high you/I, casual transitions, soft/no CTA
- Teacher: structured headers, frameworks, numbered logic, hard CTAs
- Storyteller: longer paragraphs, anecdote-led, analogy-heavy, no CTA
Then identify secondary blend.
Note: AI defaults to Teacher. Override that explicitly.

5. EMOTIONAL & AUTHORITY REGISTER
- Formality 1-10 with a quoted example sentence
- Disagreement style: hedge, assert, or reframe?
- Credibility source: experience / numbers / logic / observation / assertion
- What they assume the reader believes
- What they think the reader is getting wrong (implicit thesis)

---

OUTPUT FORMAT:

VOICE SNAPSHOT
3 sentences max. Briefing for a ghostwriter on day one.

TOP 5 SIGNATURE ELEMENTS
Most distinctive, hardest-to-fake aspects. Real quotes as evidence.

STRUCTURAL CONSTRAINTS
Enforceable rules only. Not "uses short sentences" but "every 2-3 long
sentences must be followed by a line under 6 words." Specific enough
that a different AI could follow them as instructions.

SENTENCE TEMPLATES
10 fill-in-the-blank templates extracted from actual patterns.
Build from real sentence structures, not invented ones.

THE DON'T LIST
7-10 things they never do, each with WHY it breaks the voice.
Flag anything close to the edge that could drift under AI generation.

ARCHETYPE PROFILE
Primary + secondary. What AI gets wrong by default,
and what specific constraint fixes it.

READY-TO-USE SYSTEM PROMPT
~150 words, pasteable into Claude or ChatGPT.
Encodes: structural constraints, sentence templates, archetype override,
Don't List, and language context.

---

CALIBRATION STEP:
After producing the profile, write one short paragraph (5-7 sentences)
on a neutral topic relevant to the person's domain — using only the
Voice DNA Profile you just created.

Then ask: "Does this sound like you? What's off?"
```
