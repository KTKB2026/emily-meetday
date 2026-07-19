# MASS Meet Day (emily-meetday repo)

OLY competition-day coaching card for MASS Strength. Single `index.html`
plus `sw.js` (offline cache), served via GitHub Pages from
github.com/KTKB2026/emily-meetday. As of v3 it is multi-athlete (athlete
switcher, per-athlete tabs, day schedule, save-meet, export).

Public repo rules: first names only, no contact info, only numbers that
are already public meet data (attempts, PRs, entry totals).

Workflow rules (Kyle wants version safety):
- main is the live branch; Pages serves it. Never build directly on main.
- Build on a feature branch (v4-..., v5-...), verify, then merge to main.
- Tag every merged version (v1, v2, v3, ...) and push tags. Reverting =
  point main back at the last good tag.
- Bump the `CACHE` name in `sw.js` on every deploy so phones pick up
  changes.
- Athlete meet results Kyle sends after a meet get baked into that
  athlete's history table so they live in the repo, not just his phone.

Athletes are data inside this one app. Do not create per-athlete repos.
Per-athlete bar weights: ATHS[..].bar (women 15, men 20); plate math
assumes bar + 2.5 kg collars.

This folder is canonical. Global rules: `~/.claude/CLAUDE.md`.
