# MASS Meet Day — state file

Updated 2026-07-19, after Dennis's Bay State session build-out.

## What this is

Competition-day coaching app for Olympic weightlifting. One page, works
offline at the venue, built for Kyle's phone. Live at
https://ktkb2026.github.io/emily-meetday/ (public repo, first names only).
Code: github.com/KTKB2026/emily-meetday, working copy at
~/code/emily-meetday.

## What's built (version log)

- v1 (Jul 18): Emily's single-athlete card. Warm-up ladder with
  attempts-out pacing, low/plan/high attempt board with good/miss marks,
  live totals, strategy notes, meet history. Used at Bay State day 1.
- v2 (Jul 19): bottom tabs (Snatch, C&J, Rules, History, Notes), type-in
  attempts-out counter, running session stopwatch with "last set X ago"
  (amber past 6:00), warm-up row delete, info button.
- v3 (Jul 19): multi-athlete. Athlete switcher, everything per athlete,
  day schedule strip, save meet to history, export day as text.
- v4 (Jul 19): initials-only athlete chips, collapsible schedule bar,
  weigh-in split into time + bodyweight (BW flows into history and export).
- v5 (Jul 19): Dennis's full plan baked in (snatch 105/110/115 planned,
  C&J 125/132/140 planned, PRs 110/135, entry 240). Plan-version system:
  shipping a new baked plan replaces stored warm-ups/attempts once, keeps
  saved meets, notes, records.
- v6 (Jul 19): taller bottom tabs, clear of the iPhone swipe bar. Used at
  Bay State day 2 for Dennis.

## How versions are kept safe

- main is the live branch. Every version is built on its own branch,
  tested, then merged. Tags v1 through v6 mark each working version.
- If something breaks: point main back at the last good tag. Nothing is
  ever lost; every commit is a permanent snapshot.
- Each deploy bumps the CACHE name in sw.js so phones pick up the update.
- Quirk: GitHub sometimes skips the auto-build after a push. Fix:
  `gh api --method POST repos/KTKB2026/emily-meetday/pages/builds`.
  Their CDN also caches pages up to 10 minutes.

## How data flows

- Everything typed on the phone saves to that phone only. It does not
  sync back to GitHub.
- After a meet: History tab, Save meet to history, then Export day and
  send Kyle's paste to Claude. Results get baked into the repo so they
  are permanent and reviewable for programming.

## Where we left off

Waiting on:
1. Dennis's export from today's session (then bake his results into his
   history table).
2. Emily's Bay State results (Kyle screenshotted them; bake into her
   history when he sends them).

Agreed next builds, not started:
- Linked counters for two athletes in the same flight (one -1 ticks both).
- Session dashboard: every athlete's counter, next warm-up, and attempt
  status on one screen.
- Records and qualifying totals: cards exist, need real numbers per
  athlete.
- Retarget Emily's card for her fall meet (Sn 65 / C&J 85 cycle) once the
  meet is picked.
- Add-athlete form so Kyle can create a lifter without a code change.

Bigger picture:
- Kyle's goal is a product other coaches pay for. Plan: friendly coaches
  alpha test it, feedback drives changes, testers get a discount later.
  Before that gets real: athlete data has to move out of the code
  (accounts or per-coach setup) and the app needs a neutral product name
  and its own repo name.

## How to pick this back up

Open a session in MASS Cowork and say "continue the meet-day app." The
running memory has the full context; this file is the human-readable
version of it.
