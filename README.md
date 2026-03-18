# Skills

A collection of reusable AI skills for Claude Code.

## Available Skills

### Extracting Voice DNA

A repeatable method for extracting anyone's authentic writing voice and turning it into an AI-ready system prompt.

**Files:**

| File | What it is |
|------|-----------|
| `SKILL.md` | Main skill — process overview, phases, quality checks, tips |
| `analysis-prompt.md` | Copy-paste forensic analysis prompt for Claude or ChatGPT |
| `example-profile.md` | Full example of a finished Voice DNA profile |

**Quick start:**

1. Collect 3–5 writing samples where the person sounds most like themselves
2. Open `extracting-voice-dna/analysis-prompt.md`
3. Paste the prompt + samples into Claude (or any capable model)
4. Review the output against the quality checks in `SKILL.md`
5. Run one calibration round — show the test paragraph, ask "does this sound like you?"
6. Deploy the system prompt wherever you need it

**As a Claude Code skill:**

Copy `extracting-voice-dna/` into `~/.claude/skills/` and it will be available as a skill in any Claude Code session.
