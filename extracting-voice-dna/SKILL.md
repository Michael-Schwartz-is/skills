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

Six phases, each building on the previous. Skipping phases produces shallow profiles that drift under generation.

1. **Collect** — Find and gather authentic writing samples (10-20+ is ideal)
2. **Context** — Understand who this person is, their business, and their audience
3. **Analyze** — Run samples through the forensic analysis framework
4. **Profile** — Synthesize into a structured Voice DNA Profile
5. **Calibrate** — Test with a writing sample and get feedback
6. **Deploy** — Package as a system prompt and embed in workflow

Total time: ~60-90 minutes first session, 15-20 minute calibration follow-up.

## Phase 1: Collect Writing Samples

Quality of extraction is capped by quality of input. More samples = better profile. 10-20 posts gives the analysis enough surface area to separate real patterns from one-off behavior.

### Step 1: Find what already exists

Before collecting new samples, check what's already saved:
- Existing markdown files, notes, or drafts the person has saved locally
- Google Docs, Notion pages, or other writing tools
- Saved LinkedIn post drafts

### Step 2: Extract from LinkedIn

Ask the user for the person's LinkedIn profile URL, then use Apify to scrape their posts:

1. Use an Apify LinkedIn post scraper actor (e.g. `apify/linkedin-profile-scraper` or search for a posts-specific actor)
2. Call the Apify API to run the actor with the profile URL
3. Pull the latest 20+ posts — more is better

```bash
# Example: run an Apify actor via CLI
apify call <actor-id> --input='{"profileUrls": ["https://www.linkedin.com/in/username/"]}'
```

The user needs an Apify account and API token. If they don't have one, or if the scrape fails, fall back to:
- **Copy-paste** — ask the user to paste their posts into a file or the chat
- **LinkedIn data export** — Settings → Get a copy of your data

### Step 3: Filter for authentic voice

From the full collection, identify the posts where the person sounds most like themselves:
- Posts they wrote freely, not to a brief or template
- Long-form messages where they explained something they care about
- Voice note transcriptions (gold — captures thinking before self-editing)
- Threads or replies where they were reacting in real time

Filter out:
- Content written/edited by others
- Templated pieces (carousel posts, formula listicles)
- Client or brand voice work
- Very short pieces (under 100 words)

### If collecting additional samples beyond LinkedIn

Ask for anything else they've written — long emails, voice note transcripts, Slack messages. Don't say "send your best writing" — that triggers self-editing. Instead:

> "Send me anything you've written that felt natural — not your best stuff, the stuff that sounds like you. Emails, voice notes, anything."

## Phase 2: Understand the Person

Before analyzing writing patterns, you need context on who this person is. The same sentence structure means different things coming from a VC vs. a freelance designer. This context shapes how you interpret the voice and what the system prompt prioritizes.

Have a conversation with the user to understand:

- **Who they are** — role, title, what they actually do day to day
- **Their business** — what they sell or build, who they serve, what makes them different
- **Their audience** — who are they writing for on LinkedIn? Peers, prospects, investors, a mix?
- **Their goal with content** — thought leadership, lead gen, building community, personal brand, all of the above?
- **How they want to come across** — not "professional and approachable" (everyone says that). What do they want people to *feel* after reading their post?
- **What they don't want to sound like** — equally important. "Don't sound like a guru," "don't sound salesy," etc.

Save this context — it feeds into the analysis and shapes the system prompt. A voice profile without business context produces posts that sound like the person but say nothing relevant.

## Phase 3: Analyze

Feed samples into the analysis prompt with the five forensic dimensions:

1. **Structural Fingerprint** — Sentence length variance, paragraph shape, opener/closer patterns, transitions
2. **Rhythm & Punctuation** — Em dashes, ellipses, isolated short lines, list tendency, rhetorical questions
3. **Vocabulary Signature** — Signature phrases (quoted), emphasis patterns, AI-default red flag words
4. **Voice Archetype** — Conversationalist / Teacher / Storyteller blend (AI defaults to Teacher — must override)
5. **Emotional & Authority Register** — Formality scale, disagreement style, credibility source, implicit thesis

**Full analysis prompt:** See [analysis-prompt.md](analysis-prompt.md) — copy-paste ready.

## Phase 4: Build the Profile

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

## Phase 5: Calibrate

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

## Phase 6: Deploy

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
