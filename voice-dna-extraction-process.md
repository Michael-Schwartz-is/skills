# Voice DNA Extraction Process

A repeatable method for extracting anyone's authentic writing voice and turning it into an AI-ready system prompt.

---

## What This Is

This document captures the exact process for extracting someone's unique writing voice and packaging it as a deployable AI directive. The output is a Voice DNA Profile: a structured file that any AI model can use to write authentically in that person's style.

The process was developed through real extraction sessions and refined iteratively. It works for any language, any platform, any writing style. The key insight: voice is not a vibe. It's a set of structural patterns, rhythmic habits, vocabulary signatures, and emotional registers that can be measured, documented, and reproduced.

**Who is this for?** Content teams building brand voice guidelines, agency owners offering voice-matched ghostwriting, freelancers who want AI to write in their client's voice, or anyone who wants their AI tools to actually sound like them.

---

## Process Overview

The extraction follows five phases. Each phase builds on the previous one. Skipping phases produces shallow profiles that drift under generation.

1. **Collect** — Gather 3–5 authentic writing samples from the subject.
2. **Analyze** — Run the samples through a forensic analysis framework.
3. **Profile** — Synthesize findings into a structured Voice DNA Profile.
4. **Calibrate** — Test the profile with a writing sample and get feedback.
5. **Deploy** — Package as a system prompt and embed in the workflow.

Total time from start to deployable profile: roughly 60–90 minutes for the first session, with a follow-up calibration round of 15–20 minutes.

---

## Phase 1: Collect Writing Samples

This is the most important step. Bad samples produce bad profiles. The quality of the extraction is capped by the quality of the input.

### What to collect

You need 3–5 pieces of writing where the person felt most like themselves. Not their best-performing content, not their most polished work. The pieces where they read it back and thought "yeah, that's me."

Ideal sample types:

- **Published posts** (LinkedIn, blog, newsletter) where they wrote freely, not to a brief
- **Long-form messages** (Slack, WhatsApp, email) where they explained something they care about
- **Voice note transcriptions** where they were thinking out loud, unfiltered
- **Threads or replies** where they were reacting to something in real time

### What to avoid

- Content written by someone else and edited by the subject
- Highly formatted or templated pieces (carousel posts, listicles they followed a formula for)
- Content written for a client or in a brand voice that isn't theirs
- Very short pieces (under 100 words) that don't show enough pattern

### How to ask for samples

If you're doing this for someone else, don't ask them to "send their best writing." That triggers self-editing. Instead, try:

> "Send me 3–5 things you've written where you thought: this sounds exactly like me. Not your best-performing posts. The ones where the voice felt natural, like you were explaining something to a friend who'd actually get it. Could be a LinkedIn post, a long email, a Slack rant, even a voice memo transcript."

### Minimum viable input

You can run the extraction with as few as 3 samples, but the calibration step becomes more important. With 5+ samples across different contexts (one post, one email, one voice note), the AI has enough surface area to separate the person's actual patterns from context-specific behavior.

---

## Phase 2: Run the Analysis

This is where the AI does the heavy lifting. You feed the samples into a structured analysis prompt that examines five dimensions of voice. The prompt is designed to produce measurable, enforceable observations, not vague descriptions.

### The Five Analysis Dimensions

**1. Structural Fingerprint**

How the person builds sentences and paragraphs. This is the single most distinctive marker of voice, more reliable than vocabulary.

- Sentence length variance: the gap between shortest and longest (not the average)
- Paragraph shape: percentage of 1-sentence, 2–3 sentence, and 4+ sentence paragraphs
- Dominant opener type: how they start pieces (question, declaration, anecdote, negation)
- Closing pattern: how they end (soft fade, callback, theory, question to audience, CTA)
- Transition habits: the phrases they use to connect ideas

**2. Rhythm & Punctuation**

The musicality of the writing. This is what makes someone's writing feel like them even before you process the words.

- Punctuation personality: em dashes, ellipses, parenthetical asides, commas as flow devices
- Isolated short lines used as punches or breathing room
- List-making tendency: bullet-heavy, occasional, or never
- Rhetorical question frequency

**3. Vocabulary Signature**

The words and phrases that are distinctly theirs, plus the words they never use (which is equally important for AI generation).

- Signature phrases: quoted directly from samples
- Emphasis patterns: what they reach for when driving a point home
- Red flag words: AI-default phrases that never appeared in their writing

**4. Voice Archetype**

A classification that tells the AI what mode to operate in. This matters because AI defaults to "Teacher" mode (structured, numbered, CTA-heavy), which breaks most people's voice.

The three primary archetypes:

- **Conversationalist:** short paragraphs, high you/I ratio, casual transitions, soft or no CTA
- **Teacher:** structured headers, frameworks, numbered logic, hard CTAs
- **Storyteller:** longer paragraphs, anecdote-led, analogy-heavy, no CTA

Most people are a blend. The profile should name the primary and secondary archetype and explain what constraint overrides the AI's default Teacher behavior.

**5. Emotional & Authority Register**

How the person handles credibility, disagreement, and emotional range.

- Formality level on a 1–10 scale with a quoted example sentence
- Disagreement style: hedging, asserting, or reframing
- Credibility source: experience, numbers, logic, observation specificity, or assertion
- Implicit thesis: what they assume the reader believes vs. what they think the reader is getting wrong

---

## The Analysis Prompt

Below is the complete prompt you paste into Claude (or any capable model) along with the writing samples. This is the engine of the whole process.

```
You are a forensic linguist and writing coach specializing in voice extraction.

TASK: Analyze the writing samples below and produce a Voice DNA Profile
that is immediately usable — not a document to read, but a tool to deploy.

MY WRITING SAMPLES:
[Paste 3–5 pieces where you felt most like yourself]

---

ANALYSIS FRAMEWORK:

1. STRUCTURAL FINGERPRINT
- Sentence length variance: the gap between shortest and longest (not average)
- Paragraph shape: % of 1-sentence / 2–3 sentence / 4+ sentence paragraphs
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
- Formality 1–10 with a quoted example sentence
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
Enforceable rules only. Not "uses short sentences" but "every 2–3 long
sentences must be followed by a line under 6 words." Specific enough
that a different AI could follow them as instructions.

SENTENCE TEMPLATES
10 fill-in-the-blank templates extracted from actual patterns.
Build from real sentence structures, not invented ones.

THE DON'T LIST
7–10 things they never do, each with WHY it breaks the voice.
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
After producing the profile, write one short paragraph (5–7 sentences)
on a neutral topic relevant to the person's domain — using only the
Voice DNA Profile you just created.

Then ask: "Does this sound like you? What's off?"
```

---

## Phase 3: Build the Profile

When the AI returns the analysis, you're looking for specific things to validate before moving to calibration.

### Quality checks

- **Real quotes, not summaries.** Every signature element should reference an actual phrase from the samples. If the AI is generalizing ("uses casual language"), push it to cite.
- **Enforceable constraints.** Structural rules should be specific enough to follow mechanically. "Keep it conversational" is useless. "Alternate no more than 3 long sentences before a sub-5-word line" is enforceable.
- **The Don't List is concrete.** Each item should name a specific behavior AND explain why it breaks the voice. "Don't use bullet points" is okay. "Don't use bullet points because their voice is paragraph-native and lists make it sound like a LinkedIn template" is better.
- **Sentence templates come from real patterns.** If you can't trace a template back to an actual sentence in the samples, it's invented and will produce generic output.

### Common issues to fix

- The profile is too positive. Good profiles include what the person does badly or inconsistently.
- Archetype is listed but not operationalized. There should be a clear constraint that overrides AI defaults.
- The system prompt is too long. Over 200 words dilutes the signal. The best system prompts encode 5–7 hard rules, not 15 soft suggestions.

---

## Phase 4: Calibrate

This is the phase that separates a useful profile from a decorative one. The calibration step is built into the prompt, but here's how to run it properly.

### The test paragraph

The AI writes a short paragraph (5–7 sentences) on a topic close to the person's actual domain. The topic should be close enough that voice drift is immediately obvious, but generic enough that the AI can't just copy a sample.

Good calibration topics:

- For a marketer: "Why most landing pages don't convert"
- For a developer: "Why refactoring feels productive but often isn't"
- For a founder: "Why most founders pick the wrong agency"
- For a designer: "Why most redesigns make things worse"

### The feedback loop

Show the test paragraph to the person and ask one question: "Does this sound like you? What's off?"

Their answer will typically fall into one of three categories:

1. **Tone is wrong.** "This is too formal / too casual / too aggressive / too soft." Adjust the formality scale and emotional register in the profile.
2. **Structure is wrong.** "I wouldn't open like that" or "I'd never end with a question." Tighten the structural constraints and opener/closer rules.
3. **Words are wrong.** "I'd never say 'leverage' or 'unlock.'" Add to the Don't List with specific replacements.

One round of feedback is usually enough to get the profile to 85–90% accuracy. Two rounds gets it to 95%+. After that, the remaining refinement happens organically as the person uses the profile and flags what feels off.

---

## Phase 5: Deploy

The final profile should be packaged as a markdown file with two usable components:

1. **The full Voice DNA Profile** with all analysis, examples, constraints, and templates. This is the reference document.
2. **The system prompt** (~150 words) extracted from the profile. This is the operational tool.

### Deployment options

- **Claude Project:** Upload the full profile as a knowledge file. Any conversation in that project automatically writes in the person's voice.
- **ChatGPT Custom GPT:** Paste the system prompt into the instructions field.
- **API / automation:** Include the system prompt in the system message of any API call.
- **Agent framework:** Store the markdown file in the agent's knowledge base (Obsidian vault, skill directory, etc.).

### Ongoing maintenance

The profile improves over time with two simple habits:

- **When something sounds wrong:** The person describes what specifically felt off. Add it to the Don't List with the reason.
- **When something sounds perfect:** Save the closing sentence as a new sentence template. The best templates come from actual successful outputs, not initial extraction.

---

## Example: What a Finished Profile Looks Like

Here's a condensed example of what the final output structure looks like (content is illustrative):

```
# Voice DNA — [Name]

## VOICE SNAPSHOT
[Name] writes like a colleague at a whiteboard who just connected two
ideas nobody else saw. Posts are the thinking process, not the
conclusion. Every technical thing gets reframed as a human story.

## TOP 5 SIGNATURE ELEMENTS
1. Negation opener — defines what it's NOT before what it IS
2. Personal confession hook — starts with catching themselves doing something
3. Pivot sentence — one short line alone that flips the frame
4. Honest ambivalence — excitement AND criticism in the same post
5. Closing theory — ends with a personal observation, never a CTA

## STRUCTURAL CONSTRAINTS
- Every 2–3 long sentences: follow with a line under 6 words
- Visual rhythm: alternate block sizes (1-line, 3-line, 1-line, 2-line)
- Flow with commas, not periods. Let sentences breathe
- No headers, no bold, no bullet points in posts

## SENTENCE TEMPLATES
- "Not [hype framing]. Not [technical framing]. [Simple reframe]."
- "[Caught myself thinking/doing X]. And then [realization]."
- "Most [group] think [common belief]. The problem is [reframe]."

## DON'T LIST
- No em dashes (signals AI-written content)
- No audience questions at end ("What do you think?")
- No CTAs ("Follow me for more")
- No headers or bold text in body
- Never fully bullish. Always pair excitement with honest friction

## SYSTEM PROMPT
Write as [Name]: a peer thinking out loud, not an expert teaching.
[Language]. Conversationalist + Storyteller archetype. Open with negation
or a personal moment, never a declaration. Alternate block sizes for
visual rhythm. Flow with commas. End with a short personal theory,
never a CTA or summary. Pair every moment of excitement with honest
friction. Credibility comes from observation specificity, not credentials.
Never use: em dashes, bold, headers, audience questions, bullet points.

## CALIBRATION NOTE
To test: ask AI to write a paragraph on [domain-relevant topic].
If it sounds like them — the profile works.
If not — describe what's off, update the system prompt.
```

---

## Tips from Real Extraction Sessions

- **Voice notes are gold.** Transcribed voice notes capture how someone actually thinks before they self-edit. The patterns in voice notes are often more authentic than published writing.

- **The Don't List does more work than the Do List.** AI models are good at following positive instructions but great at avoiding specific prohibitions. A tight Don't List with 7 items outperforms a loose style guide with 20 suggestions.

- **Paragraph shape is the #1 signal.** Research on voice extraction found that paragraph length distribution was the strongest distinguishing marker across writers, stronger than vocabulary. Pay extra attention to it.

- **The calibration topic matters.** Pick something the person would actually write about. If the topic is too far from their domain, you're testing the AI's knowledge, not the voice profile.

- **One round of feedback is not optional.** The extraction prompt produces a good first draft. The feedback loop is what makes it accurate. Without calibration, you're shipping a guess.

- **System prompts decay.** As someone's writing evolves, the profile needs updating. Build in a habit of flagging what sounds wrong and what sounds perfect. The profile should be a living document, not a one-time deliverable.
