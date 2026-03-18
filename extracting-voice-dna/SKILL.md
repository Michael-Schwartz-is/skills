---
name: Extracting Voice DNA
description: Use when creating an AI-ready writing voice profile for a person or brand. Triggers include requests to clone a writing style, build voice guidelines, create a ghostwriting prompt, or make AI output sound like a specific person.
---

# Extracting Voice DNA

## Overview

A repeatable method for extracting someone's authentic writing voice into a deployable AI system prompt. Voice is not a vibe — it's structural patterns, rhythmic habits, vocabulary signatures, and emotional registers that can be measured and reproduced.

**Output:** A Voice DNA Profile (structured markdown) that any AI model can use to write authentically in that person's style.

## When to Use

- Building brand voice guidelines for AI generation
- Creating voice-matched ghostwriting prompts
- Making AI tools sound like a specific person
- Onboarding a new client's voice into a content workflow

**Not for:** Generic tone adjustments ("make it more casual"), single-sentence style notes, or brand guidelines that don't need AI enforcement.

## Process Overview

Five phases, each building on the previous. Skipping phases produces shallow profiles that drift under generation.

1. **Collect** — Gather 3-5 authentic writing samples
2. **Analyze** — Run samples through the forensic analysis framework
3. **Profile** — Synthesize into a structured Voice DNA Profile
4. **Calibrate** — Test with a writing sample and get feedback
5. **Deploy** — Package as a system prompt and embed in workflow

Total time: ~60-90 minutes first session, 15-20 minute calibration follow-up.

## Phase 1: Collect Writing Samples

Quality of extraction is capped by quality of input. You need 3-5 pieces where the person felt most like themselves — not best-performing, not most polished.

### Good samples

- Published posts where they wrote freely, not to a brief
- Long-form messages where they explained something they care about
- Voice note transcriptions (gold — captures pre-self-edit thinking)
- Threads or replies with real-time reactions

### Bad samples

- Content written/edited by others
- Templated pieces (carousel posts, formula listicles)
- Client or brand voice work
- Very short pieces (under 100 words)

### How to ask

Don't say "send your best writing" — that triggers self-editing. Instead:

> "Send me 3-5 things you've written where you thought: this sounds exactly like me. Not your best-performing posts. The ones where the voice felt natural, like you were explaining something to a friend who'd actually get it."

Minimum 3 samples works, but 5+ across different contexts (post, email, voice note) lets you separate actual patterns from context-specific behavior.

## Phase 2: Analyze

Feed samples into the analysis prompt with the five forensic dimensions:

1. **Structural Fingerprint** — Sentence length variance, paragraph shape, opener/closer patterns, transitions
2. **Rhythm & Punctuation** — Em dashes, ellipses, isolated short lines, list tendency, rhetorical questions
3. **Vocabulary Signature** — Signature phrases (quoted), emphasis patterns, AI-default red flag words
4. **Voice Archetype** — Conversationalist / Teacher / Storyteller blend (AI defaults to Teacher — must override)
5. **Emotional & Authority Register** — Formality scale, disagreement style, credibility source, implicit thesis

**Full analysis prompt:** See [analysis-prompt.md](analysis-prompt.md) — copy-paste ready.

## Phase 3: Build the Profile

### Quality checks

- **Real quotes, not summaries.** Every signature element must reference an actual phrase from samples. Push for citations if the AI generalizes.
- **Enforceable constraints.** "Keep it conversational" is useless. "Alternate no more than 3 long sentences before a sub-5-word line" is enforceable.
- **Concrete Don't List.** Each item names a behavior AND explains why it breaks the voice.
- **Templates from real patterns.** If you can't trace a template back to an actual sentence, it's invented.

### Common issues

- Profile is too positive — good profiles include inconsistencies
- Archetype listed but not operationalized — needs a clear AI-default override
- System prompt over 200 words — dilutes signal. Best prompts encode 5-7 hard rules, not 15 soft suggestions

**Full example profile:** See [example-profile.md](example-profile.md) — fictional persona with all output sections: Voice Snapshot, Top 5 Signature Elements, Structural Constraints, Sentence Templates, Don't List, Archetype Profile, System Prompt, Calibration Note.

## Phase 4: Calibrate

The phase that separates useful from decorative. Built into the analysis prompt but run it properly:

1. AI writes 5-7 sentences on a topic close to the person's domain (generic enough it can't just copy a sample)
2. Show to person, ask: "Does this sound like you? What's off?"

Feedback categories and fixes:

| Feedback | Fix |
|----------|-----|
| "Too formal/casual/aggressive" | Adjust formality scale and emotional register |
| "I wouldn't open/end like that" | Tighten structural constraints and opener/closer rules |
| "I'd never say that word" | Add to Don't List with specific replacements |

One round gets to ~85-90% accuracy. Two rounds: 95%+. Remaining refinement happens organically during use.

## Phase 5: Deploy

Package as markdown with two components:

1. **Full Voice DNA Profile** — All analysis, examples, constraints, templates (reference document)
2. **System Prompt** (~150 words) — The operational tool extracted from the profile

### Deployment targets

| Platform | Method |
|----------|--------|
| Claude Project | Upload full profile as knowledge file |
| Custom GPT | Paste system prompt into instructions |
| API / automation | Include system prompt in system message |
| Agent framework | Store markdown in agent's knowledge base |

### Maintenance

- **When something sounds wrong:** Describe what's off, add to Don't List with reason
- **When something sounds perfect:** Save the output sentence as a new template — best templates come from successful outputs, not initial extraction

## Tips from Real Extractions

- **Voice notes are gold.** Transcribed voice notes capture thinking before self-editing. Often more authentic than published writing.
- **The Don't List outperforms the Do List.** AI is great at avoiding specific prohibitions. 7 tight Don'ts beat 20 loose suggestions.
- **Paragraph shape is the #1 signal.** Paragraph length distribution is the strongest distinguishing marker across writers — stronger than vocabulary.
- **Calibration topic matters.** Pick something they'd actually write about. Too-far topics test AI knowledge, not the voice profile.
- **One feedback round is not optional.** The extraction prompt produces a good draft. Feedback makes it accurate. Without calibration, you're shipping a guess.
- **System prompts decay.** As writing evolves, the profile needs updating. Build a habit of flagging what sounds wrong and what sounds perfect.
