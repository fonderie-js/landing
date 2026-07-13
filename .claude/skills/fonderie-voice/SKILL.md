---
name: fonderie-voice
description: Use whenever writing or editing outward-facing Fonderie words — landing pages (platform/landing), README pitches, taglines, meta/OG descriptions, social posts, launch copy, or investor-facing one-liners. Also when reviewing existing copy for tone. Encodes the playbook distilled from tools that won developer mindshare (graphify et al.) plus Fonderie's own vocabulary rules.
---

# Fonderie voice

Stoic about claims, warm about people. The reference point is graphify's
README — a tool that reads as a utility and spread like one. What it does,
we do; what it never does, we never do.

## The playbook (what demonstrably works)

1. **Action before category.** Open with what happens when someone uses
   it, not what the thing "is". Graphify: "Type `/graphify` — it reads
   your files, builds a knowledge graph, and gives you back structure you
   didn't know was there." Verb → result → small delight. Never "X is the
   leading/first/only platform for Y."
2. **One honest number beats ten adjectives.** Graphify: "71.5x fewer
   tokens per query" — with the corpus stated. Only use numbers we can
   point to in the repo or in production (17 bricks, routes shipped,
   crewfinding live). Never invent or extrapolate a metric.
3. **Two-line install, visible.** The distance from reading to running
   must fit in one code pill. If a claim can be a command, make it a
   command.
4. **Proof is a worked example, not a testimonial.** Show the real thing
   (crewfinding in production), named, checkable. No hypothetical praise.
5. **Transparency section over mystique.** Say plainly what the stack is
   (plain TypeScript, your Postgres, no Fonderie server, MIT) and what it
   is not. Admitting a limit ("Claude Code native; others via rules
   files") buys more trust than a padded compatibility matrix.
6. **The warmth lives in specifics, not exclamation points.** Graphify's
   charm is "whiteboard photos" and Karpathy's `/raw` folder — concrete,
   human images. Ours: a founder saying "add subscriptions" over coffee
   and it's wired; the person who copy-pasted the same backend for three
   clients. One human image per page. Speak to "you".

7. **Real problem, not plausible problem.** Graphify sells the pain felt
   *every session* (tokens wasted), not a hypothetical one (what if your
   graph is wrong?). Ours: everyone — big tech or solo — keeps rebuilding
   login/payments/teams, and every AI session rebuilds them again. Lead
   with that. A breach is plausible; the waste is real and daily.
8. **The no-scroll test.** Before the first scroll, a stranger can say
   what it is, for whom, and how. Graphify's formula: "[Name] is an
   open-source skill that helps [who] [outcome] by [mechanism]." Plain
   description is not category bragging — "is an open-source skill that…"
   describes; "the best/first/standard for…" brags.

## Hard rules (Fonderie-specific)

- **Never tell founders not to audit.** The project is open source so
  they always *can*. The promise is "audit everything — or never need
  to," never "don't look" or "trust us".

- **Vocabulary:** foundry → mold → bricks → casting → **founders** (our
  users). Never "rails" (Ruby association). Never "users" when we mean
  founders.
- **Audience:** the landing page is for people who don't code. "Login,
  payments, teams" — not "auth"; "your server" — not "your process"; "already
  there" — not "endpoints". The HTTP-standard thesis and architecture talk
  live in FONDERIE.md and the README, where readers are technical.
- **No category self-definition on the landing page.** State the problem
  and what founders get; don't declare "we are the standard/skill/platform
  for X" — it closes doors and invites comparison shopping.
- **Banned words:** revolutionary, game-changing, AI-powered, blazingly,
  seamless, supercharge, unleash, 10x (unless measured).
- **Claims must be checkable.** Every "audited", "checked in the open",
  "in production" must map to something a skeptic can click.

## Checklist before shipping copy

- [ ] Could a non-coder repeat the pitch to a friend after one read?
- [ ] Is there at least one verb-first sentence showing the product in use?
- [ ] Is every number real and sourced from the repo or production?
- [ ] Zero banned words, zero category claims, zero "rails"?
- [ ] One concrete human image present — and only one?
- [ ] Does the install path appear within the first screen?
