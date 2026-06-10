# BC AI Skills

The go-to place to **find our Gems** and the **prompt modules** they're built from.

Gems live in Gemini. This repo doesn't run them — it's the directory that points to
them and houses the reusable building blocks.

## What's here

- `registry.md` — **the front door.** Every Gem, what it does, and a link to open it.
- `gems/` — one folder per Gem: its link + metadata + a reference snapshot of its instructions.
- `modules/` — the **prompt modules** (voice, compliance, formats). Reusable blocks you
  pull from when building a Gem or any custom prompt.
- `templates/` — copy `gem-template/` to register a new Gem.
- `scripts/build_registry.py` — rebuilds `registry.md` and checks every `uses:` path exists.

## Find & use a Gem

Open `registry.md`, click the Gem's link. Done — the Gem is live in Gemini.

## Build a Gem (or any prompt) from modules

1. Pick the modules you need from `modules/` (voice + compliance + format + your task).
2. In Gemini: create the Gem, paste the task instructions, attach those modules as
   **knowledge files**. Tip: attach them from **Google Drive** so edits to a module
   propagate to the Gem automatically.
3. Register it: copy `templates/gem-template/` → `gems/<your-gem>/`, fill in `meta.yaml`
   (paste the share link), run `python scripts/build_registry.py`, open a PR.

> The modules are the single source of truth. Whether a Gem references them via Drive,
> or a pipeline reads and concatenates them at runtime, you edit the block in one place.
