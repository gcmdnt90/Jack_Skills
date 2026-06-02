# Italian LLM Skills

A collection of portable `SKILL.md` skills aimed at people working in Italian
with LLM-based assistants (Claude, Codex/ChatGPT, Gemini, local agents). Each
skill lives in its own folder under `skills/` and can be used on its own.

The repo started as an AI literacy skill and is expanding into a wider set of
engineering and productivity skills, translated and adapted into Italian.

## Available skills

| Skill | What it does | Download |
| --- | --- | --- |
| **ai-literacy-course** | Adaptive AI literacy tutor: creates, runs, updates, and tracks a personal course with a durable tracker. | [SKILL.md](skills/ai-literacy-course/SKILL.md) · [direct download](https://raw.githubusercontent.com/gcmdnt90/AI-Literacy-LLMSkill/master/skills/ai-literacy-course/SKILL.md) |
| **grill-me** | Interviews and grills you relentlessly about a plan or design until every decision is pinned down. | [SKILL.md](skills/grill-me/SKILL.md) · [direct download](https://raw.githubusercontent.com/gcmdnt90/AI-Literacy-LLMSkill/master/skills/grill-me/SKILL.md) |
| **grill-with-docs** | Like `grill-me`, but stress-tests the plan against the domain model, sharpens terminology, and updates `CONTEXT.md` and ADRs. | [SKILL.md](skills/grill-with-docs/SKILL.md) · [direct download](https://raw.githubusercontent.com/gcmdnt90/AI-Literacy-LLMSkill/master/skills/grill-with-docs/SKILL.md) |

The skill names (`grill-me`, `grill-with-docs`) stay in English, but the
description is bilingual: the skill also triggers when you speak Italian, e.g.
"intervistami", "interrogami", "mettimi alla prova", "definizione".

> The `grill-me` and `grill-with-docs` skills are Italian adaptations and
> translations of the same-named skills by
> [Matt Pocock](https://github.com/mattpocock/skills) (MIT license).
> See [`CREDITS.md`](CREDITS.md).

## Repo structure

```text
AI-Literacy-LLMSkill/
  README.md
  README_EN.md
  LICENSE
  CREDITS.md
  .gitignore
  adapters/
    gemini-gem-instructions.md
    generic-chatbot-prompt.md
  skills/
    ai-literacy-course/
      SKILL.md
      agents/openai.yaml
      references/
        standards-map.md
        course-update-sources.md
      assets/
        ai-literacy-program-template.md
    grill-me/
      SKILL.md
    grill-with-docs/
      SKILL.md
      CONTEXT-FORMAT.md
      ADR-FORMAT.md
```

## Install

### Generic chatbot — also works for Claude/Gemini/ChatGPT

Download the `SKILL.md` of the skill you want (see the table above) and attach it
to a conversation, asking the assistant to follow it as an operating procedure.

### OpenAI / Codex

Copy the skill folder into your skills directory, for example:

```text
~/.codex/skills/ai-literacy-course
~/.codex/skills/grill-me
~/.codex/skills/grill-with-docs
```

### Claude / Anthropic

Install the skill folder as a custom skill in the location supported by your
Claude product. Each skill follows the `SKILL.md` directory pattern with optional
`references/` and `assets/`.

### Gemini / Gems

Gemini Gems use custom instructions rather than the native `SKILL.md` loader.
Use `adapters/gemini-gem-instructions.md` as the Gem instruction body, and upload
or paste the desired skill's `SKILL.md`.

### Generic Chatbots

Use `adapters/generic-chatbot-prompt.md`. Attach or paste the skill's `SKILL.md`
and ask the chatbot to follow it as an operating procedure.

## Note on the ai-literacy-course skill

The `ai-literacy-course` skill needs durable state. The preferred state file is
`ai-literacy-program.md`. If the environment cannot write or preserve files, the
skill asks the user to enable local files, artifacts, project memory, or another
durable storage mechanism before relying on continuity.

Main references for the skill:

- Stanford Teaching Commons, Artificial Intelligence Teaching Guide.
- Stanford Teaching Commons, Understanding AI Literacy.
- MAILS and MAILS short version.
- GAAIS and GAAIS-IT.
- Generative AI Literacy: Twelve Defining Competencies.

Detailed source handling is in `skills/ai-literacy-course/references/`.

## License

The code and content in this repository are released under the MIT license (see
[`LICENSE`](LICENSE)). Third-party material and its license notices are listed in
[`CREDITS.md`](CREDITS.md).
