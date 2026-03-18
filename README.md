# Voice DNA Extraction

Make AI actually sound like you (or your client, or anyone).

## The Problem

You paste your writing into ChatGPT or Claude, ask it to "write in my style," and get back something that sounds like a LinkedIn template with your name on it. That's because "write casually" or "match my tone" doesn't give AI enough to work with.

## What This Does

This is a process for extracting someone's real writing voice — the sentence rhythms, word choices, paragraph shapes, and habits that make their writing sound like *them* — and packaging it into a system prompt that any AI can follow.

The output is a **Voice DNA Profile**: a structured file with enforceable rules, sentence templates pulled from real writing, and a ready-to-paste system prompt. Not vibes. Actual patterns.

## How It Works

1. **Collect** 3–5 writing samples where the person sounds most like themselves
2. **Paste** the samples + the analysis prompt (included) into Claude or ChatGPT
3. **Review** the profile it generates — check that the rules are specific and the quotes are real
4. **Calibrate** — show the test paragraph to the person, ask "does this sound like you?", tweak what's off
5. **Deploy** — paste the system prompt into whatever tool you use

~60–90 minutes for the first run. 15–20 minutes for calibration. After that, every piece of AI-generated content sounds like them.

## Who This Is For

- Content teams building brand voice guidelines
- Freelancers and agencies doing ghostwriting with AI
- Founders who want their AI tools to actually sound like them
- Anyone tired of AI writing that sounds like AI writing

## Using It

Everything you need is in the `extracting-voice-dna/` folder:

- **`SKILL.md`** — The full process with tips and quality checks
- **`analysis-prompt.md`** — The prompt you paste into AI with your writing samples
- **`example-profile.md`** — What a finished Voice DNA profile looks like

Start with `analysis-prompt.md`. That's the engine.

## As a Claude Code Skill

Copy the `extracting-voice-dna/` folder into `~/.claude/skills/` and Claude will have access to it in every session.
