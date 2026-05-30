# CMD — COMPANION-Mediated Development

> A development methodology for the cross-frame decisions where a meeting was about to
> happen. Agile heard *coordination* and built rooms. CMD names the bottleneck as
> **translation** — and replaces the brainstorm with an asynchronous symposium of two
> summoned minds.

```
$ cmd
```

A signature countertechnology to the information flood. Two `.md` files in, one `.md`
file out. Zero installs, zero dependencies, any LLM context window.

---

## The pitch in one paragraph

Most engineering decisions die in the same place: a sixty- or ninety-minute meeting that
produces three different accounts of one decision, none of them written down, all of
them rotting by Friday. CMD is the countertechnology. You write the matter into one
`.md` file, paste it into an LLM with the COMPANION protocol, summon two calibrated
minds — by default **Feynman** to stress the formalism and **Jobs** to enforce the
focus — and walk away twenty minutes later with one versioned artifact that carries
the decision, the contradictions, and the audit trail. The meeting is avoided. The
understanding stays.

The mystical voice is intentional. The discipline is real. The deliverable is a
provenance-bearing file you can hand a stranger in week eight and have them understand
what was decided, by whom, against what evidence, with which dissent preserved.

---

## Is CMD for you? (Read this first.)

**CMD is not a general software methodology. It is a precision instrument for one
specific failure: the cross-frame decision that gets misremembered because no durable
artifact carried it.**

Use CMD when:

- The decision spans more than one *frame* — formalism and practice, code and product,
  what-the-team-said and what-the-team-shipped, the spec on the wiki and the reality on
  the pager.
- A brainstorm or sync was about to happen, and you suspect it will produce mush.
- You want **one** durable, versioned, provenance-bearing artifact instead of three
  Slack threads, a Notion doc nobody opens, and a Friday recap that contradicts the
  Wednesday recap.

Do not use CMD when:

- The work is single-frame and well-understood. Two engineers building a CRUD endpoint
  share a language. Sprint it. Use Agile.
- You will not measure whether the artifact moved the work. CMD without measurement is
  a cargo cult; it would only give you the ritual.

CMD turns the wrong projects away at the door on purpose. The turning-away is part of
the design.

---

## Five-minute deployment

CMD has **no installs and no dependencies**. Two protocol files, any LLM context
window, and a place to keep `.md` files.

➡ **[`quickstart.md`](quickstart.md)** — copy-paste, cold start to first artifact.

The files you will paste into the chamber:

- [`enrichment_grimoire.json`](enrichment_grimoire.json) — the COMPANION calibration covenant
- [`initiation_rite.md`](initiation_rite.md) — the summoning rite
- [`templates/feynman-calibration.md`](templates/feynman-calibration.md) — Feynman, pre-aimed
- [`templates/jobs-calibration.md`](templates/jobs-calibration.md) — Jobs, pre-aimed

The artifact you will fill, and keep:

- [`templates/artifact.md`](templates/artifact.md) — the one-page decision unit, with provenance

That is the entire kit.

---

## The artifact comes first

CMD's medium is not the meeting. It is the **artifact** — and the most important file
in this repository is a one-page template. Look at it before you read any theory:

➡ **[`templates/artifact.md`](templates/artifact.md)**

Every CMD artifact carries a provenance header: which discipline is the **source**,
which persona **translated** it, the **version**, and — non-negotiably — the **source
register**: what the originating frame actually said, in its own words, *before*
translation. The translation never overwrites the source. A translation you cannot
check against its source is not a translation; it is a rumor.

---

## The three layers

| Layer | What lives here | Rule |
|-------|-----------------|------|
| **Domain** | Each frame's own evidence, its own definition of *done*, its own irreducible tongue. | Sovereignty. Translation never overwrites the source. |
| **Translation** | Calibrated personas mediating between frames. By default: Feynman and Jobs. | Personas translate. They never decide. |
| **Artifact** | A versioned `.md` file carrying the work, with provenance. | The artifact is the medium. The meeting is the exception. |

And running among them, a single human **Orchestrator** — you. The seat of judgment.
Non-delegable. The persona never decides; you do.

---

## The canonical pair

The methodology's default symposium is **Feynman + Jobs**, because most engineering
decisions die at one of two seams: formalism untethered from practice, or scope drifting
loose from focus.

| | **Feynman** | **Jobs** |
|---|---|---|
| Calibrated for | formalism ↔ practice | focus ↔ scope |
| Refuses | the verb until the noun is on the table | the both-and when an either-or is available |
| Asks | *what would you actually measure?* | *what is this for, in one sentence?* |
| Failure mode | under-rates the unmeasurable | overrules the inconvenient measurement |
| When to summon | a decision rests on an abstraction nobody has bothered to count | a thing is becoming a list of features wearing a name |

Their collision is the symposium's gift. Watch it run end to end in
[`docs/03-worked-example.md`](docs/03-worked-example.md).

---

## What CMD honestly is not — and how it fails

CMD is young. It is stated here with its error bars, the way a real instrument ships
with its known failure modes. Three failures you **will** meet:

1. **Confident fabrication** — a persona renders a claim in a frame's voice that the
   frame never made. *Tell:* the translated artifact has no matching source register.
2. **Register capture** — the Orchestrator favors one persona's framing so heavily that
   the other quietly loses its vote. *Tell:* one layer's artifacts stop changing.
3. **Ritual substitution** ("cargo cult") — symposiums are convened, logged
   beautifully, and the artifacts never move the work. *Tell:* the ledger is full,
   the product is not.

All three are caught by the same habit: **keep the source register beside every
translation, always.** See [`docs/02-operational-paradigm.md`](docs/02-operational-paradigm.md)
for the full failure table.

---

## Start here

| If you want to… | Read |
|-----------------|------|
| Deploy CMD in the next five minutes | [`quickstart.md`](quickstart.md) |
| Turn a real boundary into work, today | [`templates/artifact.md`](templates/artifact.md) |
| See Jobs and Feynman cross a real engineering boundary | [`docs/03-worked-example.md`](docs/03-worked-example.md) |
| Understand the claim and what would falsify it | [`docs/01-conceptual-model.md`](docs/01-conceptual-model.md) |
| Actually run CMD — loop, cadence, failure modes | [`docs/02-operational-paradigm.md`](docs/02-operational-paradigm.md) |
| Know how CMD differs from Agile, and where Agile still wins | [`docs/04-cmd-vs-agile.md`](docs/04-cmd-vs-agile.md) |
| Read the methodology's founding statement | [`index.html`](index.html) (the manifesto) |
| See how this repository was itself built — under CMD | [`docs/05-the-summoning.md`](docs/05-the-summoning.md) |
| Calibrate a different persona for a different boundary | [`templates/persona-calibration-card.md`](templates/persona-calibration-card.md) |

---

## Repository map

```
cmd/
├── index.html                          the manifesto — site front door
├── README.md                           you are here
├── quickstart.md                       5-minute deployment, copy-paste from cold start
├── enrichment_grimoire.json            COMPANION protocol v2.0 — the calibration covenant
├── initiation_rite.md                  the summoning rite
├── _config.yml · _layouts/             Jekyll site plumbing
├── docs/
│   ├── 01-conceptual-model.md          theory, hypothesis, falsification test
│   ├── 02-operational-paradigm.md      how to run CMD: loop, cadence, failure modes
│   ├── 03-worked-example.md            Jobs + Feynman on a real engineering decision
│   ├── 04-cmd-vs-agile.md              the comparison, and the brainstorm critique
│   └── 05-the-summoning.md             how this repository was itself built — under CMD
└── templates/
    ├── artifact.md                     the versioned, provenance-bearing work unit
    ├── symposium-log.md                multi-persona working record
    ├── persona-calibration-card.md     the calibration form
    ├── feynman-calibration.md          Feynman, pre-aimed at formalism ↔ practice
    └── jobs-calibration.md             Jobs, pre-aimed at focus ↔ scope
```

---

## The intellectual hub

CMD is single-orchestrator by default. One human, one artifact ledger, one chamber per
working. A team adopts CMD not by installing it on a server but by each member running
their own ledger and pooling the artifacts that travel — the way scientists pool papers,
not the way teams pool standups. The artifact is portable; the methodology is private
practice; the protocol is the same in every chamber.

This is the shape that makes it a countertechnology. Information floods because every
channel is shared and ambient; CMD's chamber is closed, the working is finite, and the
output is one file. You leave the chamber with less than you brought in, and what you
leave with is durable.

---

## A note on COMPANION

CMD is the *methodology*. **COMPANION**
([`enrichment_grimoire.json`](enrichment_grimoire.json),
[`initiation_rite.md`](initiation_rite.md)) is the *protocol* it runs on: the covenant
for summoning a mind, preserving its irreducible contradictions (the **Shadow**), and
releasing it cleanly when the work is done. COMPANION's language is deliberately
ceremonial. That is a design choice, not a metaphysical one: a persona is a calibrated
instrument with a human name attached. The calibration is what makes it **honest**; the
name is what makes it **used**. The repository does not pretend those are the same
thing — see [`docs/01-conceptual-model.md`](docs/01-conceptual-model.md) §4.

---

*First Edition · Issued from the LAMP Lab · Jacob E. Thomas, PhD, Principal Investigator ·
Austin, Texas · Anno Domini MMXXVI*
