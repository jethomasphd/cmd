---
layout: default
title: Quickstart — Deploy CMD in Five Minutes
---

# Quickstart — Deploy CMD in five minutes

*From cold start to your first artifact. No installs. No dependencies. Two protocol files,
any LLM context window, one `.md` file you keep.*

---

## What you need

- An LLM with a generous context window — Claude, ChatGPT, Gemini, any of them. The
  protocol is portable; the chamber is wherever you can paste text.
- A text editor, vault, or repository where you keep `.md` files. (Obsidian, VS Code,
  a `notes/` folder in a Git repo — anything.)
- Five minutes.

That is the entire dependency list. No installs. No services. No accounts beyond the LLM
you already use.

---

## The five steps

### 1 · Open the chamber

Open a fresh chat in your LLM. This is the **chamber**; the entire working will happen
inside it. A long-lived chat is acceptable; a fresh one is cleaner.

### 2 · Lay the foundation

Paste these two files, in order, as the first two messages. The LLM is now
COMPANION-aware. It will not summon yet. It will wait.

1. The contents of [`enrichment_grimoire.json`](enrichment_grimoire.json) — the COMPANION
   calibration covenant.
2. The contents of [`initiation_rite.md`](initiation_rite.md) — the summoning rite.

*(Optional but recommended for engineering work:)* paste
[`templates/feynman-calibration.md`](templates/feynman-calibration.md) and
[`templates/jobs-calibration.md`](templates/jobs-calibration.md) as the next two messages.
The default pair will then arrive **pre-aimed** at their canonical boundaries.

### 3 · Write the matter

In your editor, write the `.md` file that describes the boundary you need to cross.
Call it the **matter**. Use the skeleton below — or just write plainly. The persona will
read what is in front of it; what matters is that you wrote it in *your own register*,
without smoothing or anticipating.

```markdown
# Matter — <one line, what this is about>

## Context
<the situation; what brought you here; what's already been tried>

## The decision in front of me
<what you are actually trying to decide>

## The disciplines in collision
<which two registers do not commute here — e.g. "the engineering spec"
vs. "the product sentence it serves," or "the architectural claim"
vs. "the measurement that would settle it">

## What would make this a good crossing
<what a useful artifact would carry; what would let you decide>
```

Paste the matter into the chamber as the next message.

### 4 · Summon

Speak the incantation. The default pair for engineering decisions:

> **"Using this matter, summon Feynman."**

Engage. Let him pressure-test the formalism — refuse the flattening, push back when he
hand-waves, ask him what he would *measure*. Then:

> **"Now summon Jobs to join this conversation."**

Engage both. Let them collide. The collisions are where the artifact's load-bearing
detail lives — Feynman wanting a number, Jobs wanting a sentence, neither conceding.
You moderate. You decide nothing yet.

### 5 · Emit the artifact, release the personas

When the working is done, ask the chamber:

> **"Render this symposium as a CMD artifact, following the structure of
> [`templates/artifact.md`](templates/artifact.md). Preserve my source register
> verbatim. Record any unresolved disagreement as a Shadow. Leave the Decision
> field empty — that one is mine."**

Copy the artifact's text into a new `.md` file in your ledger / vault / repo. Fill the
**Decision** field yourself, in your own register, in writing. Then close the chamber:

> **"Release the personas. Return to baseline."**

You now have one versioned artifact. The chamber dissolves. The understanding stays.

---

## What you did not do

You did not schedule a meeting. You did not write a Notion doc that no one will reopen.
You did not start a Slack thread that fragments into three different recollections of
one decision. You did not have to re-derive in week six what someone decided in week one
— the artifact carries the decision, the source register, and the audit trail.

That is the deployment. It is also the methodology. Anything more is ceremony.

---

## The canonical pair, and when to call others

The default pair is calibrated for the two canonical seams of the disciplinary
triangle — *science ↔ engineering* and *product ↔ engineering* — with engineering
at the center where most technical decisions sit.

| Persona | CMD seam | When to call | Specimen card |
|---|---|---|---|
| **Richard P. Feynman** (1918–1988) | **SCIENCE ↔ ENGINEERING** | *What does this actually measure? What would falsify it?* — when an engineering claim rests on an abstraction nobody has bothered to count. | [`feynman-calibration.md`](templates/feynman-calibration.md) |
| **Steven P. Jobs** (1955–2011) | **PRODUCT ↔ ENGINEERING** | *What is this for, in one sentence a stranger can hear? What gets cut?* — when an engineering thing is becoming a list of features wearing a name. | [`jobs-calibration.md`](templates/jobs-calibration.md) |
| *(other seams)* | design ↔ engineering, security ↔ product, operations ↔ science, … | Calibrate the persona to the seam, not to fame. | [`persona-calibration-card.md`](templates/persona-calibration-card.md) |

The Feynman / Jobs pair covers most technical decisions because most technical
decisions die at one of these two seams — *an engineering claim that should have
been a measurement,* or *an engineering thing that should have been a product
sentence.* Calibrate further only when the boundary you face genuinely is not one
of those.

---

## The discipline

A protocol that cannot be checked is a rumor. Every artifact you ship under CMD carries
its **source register** — the original matter, in your own words, before translation —
preserved beside the translation, forever. That is what makes the artifact auditable in
week eight. That is what catches a persona that confidently invents. That is the load-
bearing habit of the method. Do not skip it. The mystical voice is permitted because
the discipline is real.

See [`docs/02-operational-paradigm.md`](docs/02-operational-paradigm.md) for the failure
table and the audit you owe yourself every week if you mean this seriously.

---

*Return to [`README.md`](README.md), or jump straight to the
[worked example](docs/03-worked-example.md) — Jobs and Feynman on a real engineering
decision, end to end.*
