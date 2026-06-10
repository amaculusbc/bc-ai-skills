# BC AI Skills

Shared library of reusable AI **skills** for the team. Each skill is a self-contained
bundle (instructions + knowledge + tests) that deploys as a **Gemini Gem** — but stays
portable to Claude Projects, GPTs, or pipelines because the source is plain files.

## How it's organized

- `skills/` — one folder per skill. Each maps to one Gem.
- `shared/` — reusable building blocks (brand voice, compliance rules, output formats).
  Skills *reference* these instead of duplicating them.
- `templates/` — copy `skill-template/` to start a new skill.
- `scripts/` — helpers (registry builder, validation).

## Using a skill

Each skill has one shared, live Gem. Grab its link from `registry.md` (or the skill's
`gem_url` in `meta.yaml`) and use it directly — don't make your own copy.

## Building / updating a skill (maintainers)

The repo is the source of truth; the Gem is the runtime.
1. Edit `gem.md` (instructions) and `meta.yaml` (incl. `gem_url`).
2. Create/update the Gem: paste `gem.md`, attach the `uses:` shared blocks + `knowledge/` files.
3. Run `python scripts/build_registry.py`.

> Gems don't sync from GitHub. When a shared block changes, re-upload it to the Gems
> that use it — the registry's `uses:` validation tells you the blast radius.

## Adding a skill

Copy `templates/skill-template/`, rename it (kebab-case), fill in the files, open a PR.
See `CONTRIBUTING.md`.
