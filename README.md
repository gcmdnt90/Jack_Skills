# Skill LLM in italiano

Una raccolta di skill portabili in formato `SKILL.md`, pensate per chi lavora in
italiano con assistenti basati su LLM (Claude, Codex/ChatGPT, Gemini, agenti
locali). Ogni skill vive in una propria cartella sotto `skills/` e può essere
usata singolarmente.

*English version available in `README_EN.md`.*

Il repository nasce dalla skill di alfabetizzazione all'IA e si sta allargando a
un insieme più ampio di skill di ingegneria e produttività, tradotte e adattate
in italiano.

## Skill disponibili

| Skill | A cosa serve | Scarica |
| --- | --- | --- |
| **ai-literacy-course** | Tutor adattivo di alfabetizzazione all'IA: crea, esegue, aggiorna e monitora un corso personale con tracker persistente. | [SKILL.md](skills/ai-literacy-course/SKILL.md) · [download diretto](https://raw.githubusercontent.com/gcmdnt90/AI-Literacy-LLMSkill/master/skills/ai-literacy-course/SKILL.md) |
| **grill-me** | Ti intervista e ti interroga senza tregua su un piano o un progetto finché ogni decisione non è chiarita. | [SKILL.md](skills/grill-me/SKILL.md) · [download diretto](https://raw.githubusercontent.com/gcmdnt90/AI-Literacy-LLMSkill/master/skills/grill-me/SKILL.md) |
| **grill-with-docs** | Come `grill-me`, ma mette alla prova il piano rispetto al modello di dominio, affina la terminologia e aggiorna `CONTEXT.md` e gli ADR. | [SKILL.md](skills/grill-with-docs/SKILL.md) · [download diretto](https://raw.githubusercontent.com/gcmdnt90/AI-Literacy-LLMSkill/master/skills/grill-with-docs/SKILL.md) |

I nomi delle skill (`grill-me`, `grill-with-docs`) restano in inglese, ma la
descrizione è bilingue: la skill si attiva anche quando in italiano dici
ad esempio "intervistami", "interrogami", "mettimi alla prova", "definizione".

> Le skill `grill-me` e `grill-with-docs` sono adattamenti e traduzioni in
> italiano delle skill omonime di [Matt Pocock](https://github.com/mattpocock/skills)
> (licenza MIT). Vedi [`CREDITS.md`](CREDITS.md).

## Struttura del repository

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

## Installazione

### Chatbot generico — valido anche per Claude/Gemini/ChatGPT

Scarica il `SKILL.md` della skill che ti interessa (vedi la tabella sopra) e
allegalo a una conversazione, chiedendo all'assistente di seguirlo come
procedura operativa.

### OpenAI / Codex

Copia la cartella della skill nella tua directory delle skill, per esempio:

```text
~/.codex/skills/ai-literacy-course
~/.codex/skills/grill-me
~/.codex/skills/grill-with-docs
```

### Claude / Anthropic

Installa la cartella della skill come skill personalizzata nella posizione
supportata dal tuo prodotto Claude. Ogni skill segue il pattern di directory
`SKILL.md` con file `references/` e `assets/` opzionali.

### Gemini / Gems

Le Gemini Gems usano istruzioni personalizzate invece del loader nativo
`SKILL.md`. Usa `adapters/gemini-gem-instructions.md` come corpo delle
istruzioni della Gem e carica o incolla il `SKILL.md` della skill desiderata.

### Chatbot generici

Usa `adapters/generic-chatbot-prompt.md`. Allega o incolla il `SKILL.md` della
skill e chiedi al chatbot di seguirlo come procedura operativa.

## Nota sulla skill ai-literacy-course

La skill `ai-literacy-course` ha bisogno di uno stato persistente. Il file di
stato preferito è `ai-literacy-program.md`. Se l'ambiente non può scrivere o
conservare file, la skill chiede all'utente di abilitare file locali, artifact,
memoria di progetto o un altro meccanismo di archiviazione persistente prima di
fare affidamento sulla continuità.

Riferimenti principali della skill:

- Stanford Teaching Commons, Artificial Intelligence Teaching Guide.
- Stanford Teaching Commons, Understanding AI Literacy.
- MAILS and MAILS short version.
- GAAIS and GAAIS-IT.
- Generative AI Literacy: Twelve Defining Competencies.

La gestione dettagliata delle fonti si trova in `skills/ai-literacy-course/references/`.

## Licenza

Codice e contenuti di questo repository sono rilasciati con licenza MIT (vedi
[`LICENSE`](LICENSE)). Il materiale derivato da terze parti e le relative note
di licenza sono elencati in [`CREDITS.md`](CREDITS.md).
