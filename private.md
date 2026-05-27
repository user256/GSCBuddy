# private.md

**This file is gitignored.** It's a per-developer, per-machine scratchpad.
Treat it as your local working notes — paths that only exist on your machine,
the command you actually run, environment-specific quirks.

**Do not put secrets in this file.** Even though it's gitignored, it can leak
via backups, screen shares, or accidental `git add -f`. Real secrets go in
`.env`. This file documents the *shape* of `.env`, not its values.

---

## Local paths

Anything machine-specific. Examples:

```
DESIGN_GUIDE = /home/{you}/resources/awesome-design-md/design-md/proton
DATA_DIR     = /home/{you}/data/{project}
MODEL_CACHE  = /home/{you}/.cache/{project}
```

Replace with your actual paths. These don't belong in the repo because they
won't match anyone else's filesystem.

---

## `.env` layout

The variables this project expects. Copy these into `.env` and fill in real
values. Update this list when you add a new env var to the code.

```
# Required
ANTHROPIC_API_KEY=
# OPENAI_API_KEY=          # uncomment if/when you wire in OpenAI

# Optional
LOG_LEVEL=INFO             # DEBUG | INFO | WARNING | ERROR
RUN_DIR=./runs             # where artefacts land
EVAL_DIR=./evals           # eval datasets and runners
```

---

## Quick run example

The exact command you use to invoke the project, with a small input you know
works. Paste the real thing here so you don't have to reconstruct it every
time.

```bash
source .venv/bin/activate
python run.py \
    --input fixtures/sample.json \
    --output runs/$(date +%Y%m%d-%H%M%S) \
    --model claude-opus-4-7
```

### Main parameters

Document the flags you actually use, with values that worked. This is for
*you*, future-you, and anyone you pair with — not a user manual.

- `--input PATH`        — input JSON; `fixtures/sample.json` is a known-good case.
- `--output DIR`        — run artefacts go here; one subdir per run.
- `--model NAME`        — model string. `claude-opus-4-7` for quality, `claude-haiku-4-5` for speed.
- `--temperature FLOAT` — leave at default unless you're chasing a determinism bug.

---

## Local notes

Append-only scratch. Things you'll forget by next week.

- {date} — {what you learned, what you tried, what surprised you}
