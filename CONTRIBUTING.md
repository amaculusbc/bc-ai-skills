# Contributing

## Naming
- Skill folders: kebab-case, named by what they do — `article-writer`, `headline-generator`, `fact-checker`.
- Shared blocks: kebab-case by topic — `action-network.md`, `responsible-gambling.md`.

## Adding a skill
1. Copy `templates/skill-template/` → `skills/<your-skill>/`.
2. Fill in `gem.md`, `meta.yaml`, `README.md`, and at least one entry in `examples/test-cases.md`.
3. Reference shared blocks in `meta.yaml` under `uses:` — don't paste voice/compliance text inline.
4. Run `python scripts/build_registry.py` to refresh `registry.md`.
5. Open a PR.

## PR checklist
- [ ] `meta.yaml` is complete (owner, version, target models, last_tested).
- [ ] Reuses shared blocks instead of duplicating them.
- [ ] Has at least one test case with expected behavior.
- [ ] Registry rebuilt.

## Versioning
Semver in `meta.yaml`. Bump on any instruction change. Note what changed in the skill's README.
