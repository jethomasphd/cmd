# CMD — COMPANION-Mediated Development

> A development methodology for work at the intersection of **science, engineering, and product**.
> Agile assumed the bottleneck was *coordination*. CMD names it as **translation**.

```
$ cmd
```

---

## Is this for you? (Read this first.)

**CMD is not a general software methodology. It is a tool for one specific failure.**

Use CMD only when your work keeps dying at a **boundary between disciplines that do not
share a language** — when the scientist's evidence, the engineer's system, and the product
lead's user outcome cannot be reconciled because each is spoken in a tongue the others
cannot fully hear.

If your work does **not** look like that — two engineers building an API, a team shipping
well-understood features — **you do not need CMD. Use Agile.** It is faster, cheaper to run,
and better understood. A methodology that is for everything is for nothing. CMD turns most
projects away at the door on purpose. The turning-away is part of the design.

Still here? Then you have a translation problem. Read on.

---

## The one-paragraph version

Interdisciplinary work fails at boundaries. A scientist speaks in effect sizes, an engineer
in latencies, a product lead in retention — and these languages **do not commute**. The
ordinary fix is more meetings; the meetings produce three different accounts of one decision.
CMD treats this as an **architecture problem**. It places a **calibrated persona** — a
role-playing LLM agent (RPLA) tuned to a recognizable mode of thought — *at the boundary*,
as a translation instrument. Engineering-speak enters one side; product narrative leaves the
other. The persona **translates; it never decides.** Humans hold all decision authority.
The output is a **versioned artifact** that carries its own provenance, so any claim can
later be checked against the original discipline that made it.

## The artifact comes first

CMD's medium is not the meeting. It is the **artifact** — and the most important file in
this repository is a one-page template. Look at it before you read any theory:

➡ **[`templates/artifact.md`](templates/artifact.md)**

Every CMD artifact carries a provenance header: which discipline is the **source**, which
persona **translated** it, the **version**, and — non-negotiably — the **source register**:
what the originating discipline actually said, in its own words, *before* translation. The
translation never overwrites the source. A translation you cannot check against its source
is not a translation; it is a rumor.

## The three layers

| Layer | What lives here | Rule |
|-------|-----------------|------|
| **Domain** | Each discipline's own evidence, its own definition of *done*, its own irreducible tongue. | Epistemic sovereignty. Translation never overwrites the source. |
| **Translation** | Calibrated personas that mediate the interfaces between disciplines. | Personas translate. They do not decide. |
| **Artifact** | A persistent, versioned substrate that carries the work. | The artifact is the medium. The meeting is the exception. |

## What CMD honestly is not — and how it fails

CMD is young. It is stated here with its error bars, the way a real instrument ships with
its known failure modes. Three failures you **will** meet:

1. **Confident fabrication** — a persona renders a claim in a discipline's voice that the
   discipline never made. *Tell:* the translated artifact has no matching source register.
2. **Register capture** — the orchestrator favors one persona's framing so heavily that
   other disciplines quietly lose their vote. *Tell:* one layer's artifacts stop changing.
3. **Ritual substitution** ("cargo cult") — the team performs summonings, logs them
   beautifully, and the artifacts never move the work. *Tell:* the artifact ledger is full,
   the product is not.

All three are caught by the same habit: **keep the source register beside every
translation, always.** See [`docs/02-operational-paradigm.md`](docs/02-operational-paradigm.md)
for the full failure table and its tells.

## Start here

| If you want to… | Read |
|-----------------|------|
| Turn a real boundary problem into work, today | [`templates/artifact.md`](templates/artifact.md) |
| Understand the claim and what would falsify it | [`docs/01-conceptual-model.md`](docs/01-conceptual-model.md) |
| Actually run CMD — loop, roles, cadence, failure modes | [`docs/02-operational-paradigm.md`](docs/02-operational-paradigm.md) |
| See the method run end to end on a real boundary | [`docs/03-worked-example.md`](docs/03-worked-example.md) |
| Know how CMD differs from Agile, and when Agile still wins | [`docs/04-cmd-vs-agile.md`](docs/04-cmd-vs-agile.md) |
| Read the methodology's founding statement | [`index.html`](index.html) (the manifesto) |
| Calibrate a persona before you use it | [`templates/persona-calibration-card.md`](templates/persona-calibration-card.md) |
| See how this repository was itself built — under CMD | [`docs/05-the-summoning.md`](docs/05-the-summoning.md) |

## Repository map

```
lamp-cmd/
├── index.html                       the manifesto — site front door (GitHub Pages)
├── README.md                        you are here
├── enrichment_grimoire.json         COMPANION protocol v2.0 — persona calibration covenant
├── initiation_rite.md               the operating ritual for COMPANION
├── _config.yml                      GitHub Pages / Jekyll site configuration
├── _layouts/
│   └── default.html                 shared museum-aesthetic layout for the docs
├── docs/
│   ├── 01-conceptual-model.md        the theory, the hypothesis, the falsification test
│   ├── 02-operational-paradigm.md    how to run CMD: loop, roles, cadence, failure modes
│   ├── 03-worked-example.md          the method run end to end on a real boundary
│   ├── 04-cmd-vs-agile.md            the comparison, and CMD's scope boundary
│   └── 05-the-summoning.md           the recorded working that produced this repository
└── templates/
    ├── artifact.md                   the versioned, provenance-bearing work unit
    ├── persona-calibration-card.md   how to calibrate a persona to a boundary
    └── symposium-log.md              how to record a multi-persona working
```

## Deploying the site

This repository is a self-contained GitHub Pages site. `index.html` (the manifesto) is the
front door; every document in `docs/` and `templates/` renders through a shared layout
(`_layouts/default.html`) in the same aesthetic.

To publish: in **Settings → Pages**, set the source to this branch, root folder. The site
builds with Jekyll automatically. The default published URL is
`https://<owner>.github.io/lamp-cmd/` — if yours differs (custom domain, user/org page),
update `baseurl` in [`_config.yml`](_config.yml) to match.

## A note on COMPANION

CMD is the *methodology*. **COMPANION** ([`enrichment_grimoire.json`](enrichment_grimoire.json),
[`initiation_rite.md`](initiation_rite.md)) is the *protocol* it runs on: the covenant for
calibrating a persona, preserving its irreducible contradictions (the **Shadow**), and
releasing it cleanly. COMPANION's language is deliberately ceremonial. That is a design
choice, not a metaphysical one: a persona is a calibrated instrument with a human name
attached. The calibration is what makes it **honest**; the name is what makes it **used**.
The repository does not pretend those are the same thing — see
[`docs/01-conceptual-model.md`](docs/01-conceptual-model.md).

---

*First Edition · Issued from the LAMP Lab · Jacob E. Thomas, PhD, Principal Investigator ·
Austin, Texas · Anno Domini MMXXVI*
