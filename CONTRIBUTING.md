# Contributing

## Register a Gem
1. Copy `templates/gem-template/` → `gems/<gem-slug>/` (kebab-case).
2. Fill `meta.yaml`: name, description, **gem_url** (the share link), owner, version,
   and the `uses:` list of modules.
3. Paste a reference snapshot of the instructions into `gem.md`.
4. Run `python scripts/build_registry.py` and open a PR.

## Add a prompt module
- Drop it in the right `modules/` subfolder (`voice/`, `compliance/`, `formats/`, …),
  kebab-case filename. Keep it self-contained so any Gem can attach it.

## Keep it honest
- Modules are referenced, never pasted into Gems. If you need a Gem to use a rule,
  add the module to its `uses:` and attach it as a knowledge file (Drive = auto-updating).
- Update `gem.md` whenever you change the live Gem, so the snapshot doesn't drift.

## PR checklist
- [ ] `meta.yaml` has a working `gem_url`.
- [ ] `uses:` lists real modules (the registry script validates this).
- [ ] Registry rebuilt.
