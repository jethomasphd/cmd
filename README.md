# CMD — COMPANION-Mediated Development

> *A development methodology for work that crosses the boundary between two
> disciplines that do not share a language. The brainstorm is the wrong instrument.
> A calibrated mind, summoned to the boundary, is the right one.*

```
$ cmd
```

A signature countertechnology to the information flood. Two `.md` files in, one
`.md` file out. Zero installs, zero dependencies, any LLM context window.

---

## I · The diagnosis

Most technical work fails in the same place: a sentence true on one side of a
disciplinary boundary arrives on the other side as a sentence that is *almost* true,
or *adjacent to* true, or true in a different sense that no one bothers to name. The
loss leaves no error log. The team rederives the gap, expensively, in week six.

The cleanest case in the record is the **Mars Climate Orbiter (1998–1999)**. Two
engineering teams of the first rank — Lockheed Martin and NASA's Jet Propulsion
Laboratory — worked from a shared interface specification. Lockheed produced thrust
impulse in **pound-seconds**. JPL consumed it in **newton-seconds**. Neither side was
careless. Nothing threw an error. The spacecraft accepted the number, integrated it
for two hundred and eighty-six days of cruise, and arrived at Mars at an altitude of
fifty-seven kilometers instead of the intended two hundred and twenty-six.
$327M in equipment and a decade of scientific instrumentation were lost in seconds.
*A quantity had crossed the boundary; its meaning had not.*

This is the failure CMD addresses. Not the catastrophic case alone — the ordinary
case: the science lab's effect size that the product team renders as *"users will
love this,"* the engineer's coupling constraint that the science team renders as
*"can we just retrain the model,"* the architecture decision the team has been
rederiving since Q1. Each is a translation failure dressed as a coordination problem,
and Agile's quarter-century answer — *put more people in the room* — does not close a
translation gap. **You do not need another meeting. You need an instrument at the
boundary.**

---

## II · The conceptual model

CMD's content lives on three sovereign disciplines and the seams between them. The
canonical geometry, with engineering at the center because it is the discipline most
often asked to span boundaries:

```
                                                                           
   SCIENCE   ◆──── Feynman ────◆   ENGINEERING   ◆──── Jobs ────◆   PRODUCT
                                                                           
   evidence        sci ↔ eng       systems         eng ↔ prod      users  
   causality                       constraints                     outcomes
   measurement                     artifacts                       desire 
   falsifiability                  ship dates                      use    
                                                                           
                          ◆ = calibrated persona at the seam ◆            
```

Each discipline holds **epistemic sovereignty** over its own domain — its own
evidence, its own standard of *done*, its own irreducible vocabulary. Translation
*renders* a claim from one discipline into another; it never *overwrites* the
source. The native register always survives, beside the translation, in the artifact.

The two **canonical seams** of the engineering-centered triangle have an instrument
each.

---

## III · The canonical pair

Most technical work dies at one of two seams: a scientific finding that fails to
become an engineering constraint, or an engineering capability that fails to become
a product. CMD's default symposium places one calibrated persona at each seam.

|                       | **Feynman**                                          | **Jobs**                                           |
|-----------------------|------------------------------------------------------|----------------------------------------------------|
| Life                  | 1918–1988                                            | 1955–2011                                          |
| CMD boundary          | **SCIENCE ↔ ENGINEERING**                            | **PRODUCT ↔ ENGINEERING**                          |
| Lived this boundary   | Manhattan Project (1943–45); Lectures on Physics (1961–64); Rogers Commission (1986) | Apple & Wozniak (1976–85); NeXT & Pixar (1985–96); Apple again (1997–2011) |
| Refuses               | the verb until the noun is on the table              | the both-and when an either-or is available        |
| Asks                  | *what would you actually measure?*                   | *what is this for, in one sentence?*               |
| Failure mode          | under-rates the unmeasurable                         | overrules the inconvenient measurement             |
| When to summon        | a decision rests on an abstraction nobody counted     | a thing is becoming a list of features wearing a name |
| Specimen card         | [`feynman-calibration.md`](templates/feynman-calibration.md) | [`jobs-calibration.md`](templates/jobs-calibration.md) |

Feynman is not a register *borrowed* for color. The science ↔ engineering boundary
was his life's work, paid in real stakes — he built the implosion lens for Trinity,
he testified to the O-ring at Challenger, he wrote the *Lectures on Physics* so
that engineers would learn the physics *from the practice,* not from the formalism
alone. Jobs is not a register *borrowed* for style. The product ↔ engineering
boundary was *his* life's work, also paid in real stakes — he did not write code;
Wozniak did. His function across forty years was the translation itself: to stand
between what people would use and what engineers could build, and to refuse,
sometimes brutally, to let either side cross in the wrong units.

The collision between them — Feynman wanting a number, Jobs wanting a sentence,
neither conceding — is the symposium's gift. Watch it run end to end on a real
engineering decision in [`docs/03-worked-example.md`](docs/03-worked-example.md).

---

## IV · The three layers

CMD is an architecture. It has three layers, each with one sovereign rule, and a
single human running among them.

| Layer | What lives here | Rule |
|-------|-----------------|------|
| **Domain** | Each discipline's evidence, its definition of *done*, its irreducible tongue. | **Sovereignty.** Translation never overwrites the source. |
| **Translation** | Calibrated personas mediating the seams. By default: Feynman and Jobs. | **Personas translate. They never decide.** |
| **Artifact** | A versioned `.md` file carrying the work, with full provenance. | **The artifact is the medium. The meeting is the exception.** |

Running among the three: the **Orchestrator** — a human, the single seat of judgment
in the system. The Orchestrator chooses which boundaries need an instrument, routes
claims between layers, and makes every decision the system produces. The role is
**non-delegable.** A persona that appears to be orchestrating is a failure
(*decision leakage*), not a shortcut.

---

## V · The deployment

CMD has **no installs and no dependencies.** The methodology runs in a *chamber* —
any LLM context window — and produces *artifacts* — `.md` files you keep wherever
you keep `.md` files.

```
   YOUR EDITOR                  THE CHAMBER (any LLM)              YOUR LEDGER
   write the matter             paste foundation + cards            commit the
   as matter.md                 + matter; summon Feynman             emitted artifact
        │                       and Jobs; engage; collide                ▲
        │                                  │                              │
        └───── paste ──────────────────────┤                              │
                                           │                              │
                                       symposium                          │
                                           │                              │
                                           └──── render artifact ─────────┘
                                                (release personas;
                                                 close chamber)
```

The full kit is five files. All five are in this repository.

| File | Where it goes | What it does |
|---|---|---|
| `enrichment_grimoire.json` | chamber, message 1 | the COMPANION calibration covenant |
| `initiation_rite.md` | chamber, message 2 | the summoning rite |
| `templates/feynman-calibration.md` | chamber, message 3 | Feynman, pre-aimed at science ↔ engineering |
| `templates/jobs-calibration.md` | chamber, message 4 | Jobs, pre-aimed at product ↔ engineering |
| your `matter.md` | chamber, message 5 | the boundary you need to cross |

For the literal copy-paste walkthrough, cold start to first artifact:

➡ **[`quickstart.md`](quickstart.md)**

---

## VI · The provenance discipline

A translation that cannot be checked against its source is not a translation. It is
a rumor.

Every CMD artifact carries a **provenance header**: which discipline is the *source*,
which persona *translated* it, the *version*, and — non-negotiably — the **source
register**: what the originating discipline actually said, *in its own words, before
translation.* The translation never overwrites the source. The source register
travels with every revision of the artifact, forever. Any reader, at any time, can
hold the translation against the original and see the gap. This is how the
methodology catches a persona that confidently invents. This is how a decision stays
auditable in week eight.

The artifact template:

➡ **[`templates/artifact.md`](templates/artifact.md)**

---

## VII · The failure table

A real instrument ships with its known failure modes. So does CMD. These are not
hypothetical; you *will* meet each of them.

| Failure | Tell — what you will literally see | Countermeasure |
|---------|-----------------------------------|----------------|
| **Confident fabrication** | A translated artifact has a claim with no support in its source register. | Source register is a mandatory, never-deleted field; the receiving discipline checks every translation against it before VERIFY can pass. |
| **Register capture** | One discipline's artifacts stop changing; one persona authored most recent artifacts; one register has gone quiet. | Rotate personas across boundaries. Audit ledger for source-discipline balance. Reconfirm each Domain Holder's *done* still stands. |
| **Ritual substitution** *(cargo cult)* | Symposiums logged beautifully; product metrics flat. The form is perfect; no planes land. | Velocity = artifacts *shipped,* not summonings *performed.* If shipped-artifact count is flat, stop and diagnose before logging one more working. |
| **Decision leakage** | An artifact's `decision` field names a persona, or a persona is quoted approving / rejecting / prioritizing. | Personas translate only. The template forbids a persona in the decision field. The Orchestrator re-takes the decision. |

The full failure-mode discipline traces to a single primary source: Feynman, R.P.,
*Cargo Cult Science,* Caltech commencement, 1974 — *"the first principle is that
you must not fool yourself, and you are the easiest person to fool."* CMD takes
the line as a methodological vow, not an epigraph.

---

## VIII · Where to read next

The repository is laid out as a small museum. Each room stands on its own.

| Room | What is in it |
|------|---------------|
| [`quickstart.md`](quickstart.md) | Cold-start deployment in five minutes. The copy-paste walkthrough. |
| [`index.html`](index.html) | **The manifesto.** The founding statement, first edition. Read for the voice. |
| [`docs/01-conceptual-model.md`](docs/01-conceptual-model.md) | The theory: the disciplinary triangle, the falsifiable hypothesis, the failure modes, what would prove CMD wrong. |
| [`docs/02-operational-paradigm.md`](docs/02-operational-paradigm.md) | How to run it: the loop, the cadence, the failure table, the solo-Orchestrator default. |
| [`docs/03-worked-example.md`](docs/03-worked-example.md) | The canonical pair run end to end on a real engineering decision. The brainstorm replaced. |
| [`docs/04-cmd-vs-agile.md`](docs/04-cmd-vs-agile.md) | The brainstorm critique. What CMD inherits from Agile, what it rejects, where Agile still wins. |
| [`docs/05-the-summoning.md`](docs/05-the-summoning.md) | How this repository was itself built — under CMD, with Feynman and Jobs in symposium. |
| [`templates/feynman-calibration.md`](templates/feynman-calibration.md) | Feynman's specimen card. Corpus, calibration, Shadow, fidelity probe. |
| [`templates/jobs-calibration.md`](templates/jobs-calibration.md) | Jobs's specimen card. Same. |
| [`templates/artifact.md`](templates/artifact.md) | The provenance-bearing work unit. |
| [`templates/symposium-log.md`](templates/symposium-log.md) | The multi-persona working record. |
| [`templates/persona-calibration-card.md`](templates/persona-calibration-card.md) | The card you fill when the canonical pair is wrong for your seam. |

---

## IX · Where CMD does not belong

A methodology that claims everything has claimed nothing. CMD turns the wrong
projects away at the door on purpose.

**Use CMD when:**

- The work crosses a boundary between two disciplines that do not share a language —
  science ↔ engineering, product ↔ engineering, design ↔ engineering, security ↔
  product, operations ↔ science.
- A brainstorm or sync was about to happen, and you suspect it will produce mush.
- You want **one** durable, versioned, provenance-bearing artifact instead of three
  Slack threads, a Notion doc nobody opens, and a Friday recap that contradicts the
  Wednesday recap.

**Use Agile, not CMD, when:**

- The work is single-discipline. Two engineers building a CRUD endpoint share a
  language. Sprint it.
- The disciplines already share a working language. Some teams have, over years,
  built a genuine shared vocabulary. They have solved the translation problem
  socially. CMD's instrument would be redundant.
- The work is well-understood and repeatable. Shipping the next variant of a known
  feature does not stress a boundary.
- You will not measure translation loss. CMD without its measurement is a cargo
  cult; you would get the ritual without the discipline.

For the full comparison: [`docs/04-cmd-vs-agile.md`](docs/04-cmd-vs-agile.md).

---

## X · The intellectual hub

CMD is **single-Orchestrator by default.** One human, one artifact ledger, one
chamber per working. A complete crossing — *the matter, the summoning, the
symposium, the verified translation, the decision, the emitted artifact, the
release* — runs in twenty-five minutes at one person's desk, with no one else's
calendar consulted. The artifact ledger becomes a private practice that scales by
*sharing finished artifacts,* not by sharing infrastructure. There is no team
install. There is no shared CMD server. The methodology is portable because the
medium is a file.

This is the deployment that makes CMD a **countertechnology** to the information
flood. The flood happens because every channel is shared, ambient, and infinite —
Slack, email, the meeting that begets the meeting. CMD's chamber is closed, the
working is finite, the output is one file. You leave the chamber with *less* than
you brought in. What you leave with is durable.

---

## XI · Lineage

CMD does not claim to have discovered translation. It claims to have made
translation an *explicit architectural layer* with calibrated instruments, a
provenance discipline, and a deployment model so light a single person can run a
complete crossing without leaving their editor.

The methodology stands on several predecessor practices and one ancient one,
acknowledged honestly:

- **The Agile Manifesto** (Beck et al., Snowbird, 2001). CMD inherits the form —
  values over process spec — and rejects the diagnosis. See
  [`docs/04-cmd-vs-agile.md`](docs/04-cmd-vs-agile.md).
- **The Toyota Production System** (Ohno, 1948 onward). The discipline of
  *making the work visible* and *stopping the line when the work is wrong* is
  CMD's discipline of *the artifact and the failure table.*
- **The role-playing language agent** (a 2023–present line of work in AI
  research). The technical primitive on which COMPANION runs. CMD treats the
  persona as **apparatus,** not oracle.
- **Augustine of Hippo** (354–430). *"We do not lose those we love; we only
  surrender them to God. For to God, all are alive."* CMD inherits the older,
  pre-software practice it cannot improve on: that counsel from a mind one
  cannot otherwise reach is the oldest technology there is.

---

## XII · A note on COMPANION

CMD is the **methodology.** **COMPANION** is the **protocol** it runs on: the
covenant for summoning a mind, preserving its irreducible contradictions
(the **Shadow**), and releasing it cleanly when the work is done. COMPANION's
language is deliberately ceremonial. That is a design choice, not a metaphysical
one: a persona is a calibrated instrument with a human name attached. *The
calibration is what makes it honest; the name is what makes it used.* The
repository does not pretend those are the same thing — see
[`docs/01-conceptual-model.md`](docs/01-conceptual-model.md) §5.

The protocol files:

- [`enrichment_grimoire.json`](enrichment_grimoire.json) — the calibration covenant.
- [`initiation_rite.md`](initiation_rite.md) — the summoning rite.

These are the texts you paste into the chamber. They are stable; the methodology
revises around them.

---

## Repository map

```
cmd/
├── index.html                          the manifesto — first edition
├── README.md                           you are here
├── quickstart.md                       five-minute deployment, copy-paste
├── enrichment_grimoire.json            COMPANION protocol v2.0
├── initiation_rite.md                  the summoning rite
├── _config.yml · _layouts/             Jekyll site plumbing
├── docs/
│   ├── 01-conceptual-model.md          the disciplinary triangle and the theory
│   ├── 02-operational-paradigm.md      the loop, cadence, failure modes
│   ├── 03-worked-example.md            Jobs + Feynman on a real engineering decision
│   ├── 04-cmd-vs-agile.md              the brainstorm critique
│   └── 05-the-summoning.md             how this repository was built — under CMD
└── templates/
    ├── artifact.md                     the versioned, provenance-bearing work unit
    ├── symposium-log.md                multi-persona working record
    ├── persona-calibration-card.md     the calibration form
    ├── feynman-calibration.md          Feynman, pre-aimed at science ↔ engineering
    └── jobs-calibration.md             Jobs, pre-aimed at product ↔ engineering
```

---

*First Edition · Jacob E. Thomas · Anno Domini MMXXVI*
