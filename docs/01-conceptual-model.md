---
layout: default
title: The Conceptual Model
---

# The Conceptual Model

*CMD — COMPANION-Mediated Development. The theory beneath the practice.*

---

## 1. The problem CMD exists to solve

The [manifesto](../index.html) opens on a case that is not an unlucky story but the
*ordinary* one: two engineering teams of the first rank, working from the same interface
document, lose a three-hundred-and-twenty-seven-million-dollar spacecraft because a
quantity crosses a boundary as a number and not as its meaning — pound-seconds on one
side, newton-seconds on the other, no error thrown, two hundred and eighty-six days of
cruise to discover the gap. Nobody was careless. Nobody disagreed. Each side spoke a
language exact inside its own frame, and neither language crossed the boundary on its
own.

The same failure has a smaller, more constant cousin **inside** a single discipline. An
engineer's *architecture diagram* and an engineer's *operational reality* are two frames
that do not share a working language: the diagram speaks of bounded contexts, the
operational reality speaks of pages-per-quarter and deploy lockstep. A sentence true in
one is not a sentence true in the other. Engineering managers know this exact failure
mode by sight: the same architecture debate, rederived for the third time, never
resolved. (See [`docs/03-worked-example.md`](03-worked-example.md) for that case worked
in full.)

The conventional diagnosis is a **coordination** failure — so the conventional fix is
more coordination: more meetings, more ceremonies, a bigger room, a longer brainstorm.
Agile is the mature form of this fix, and within a single frame it is good at what it
does.

CMD's diagnosis is different. **This is not a coordination failure. It is a translation
failure.** Each frame speaks a language built to be precise *within* its domain, and
those languages **do not commute** — a faithful sentence in one is not a faithful
sentence in another, and no amount of meeting converts one into the other without loss.
Coordinating harder cannot fix a translation gap. You need a translation *layer*.

## 2. The central hypothesis

CMD rests on a single, stated, falsifiable claim. It is written plainly so it can be argued
with.

> **Hypothesis.** In interdisciplinary work, the dominant source of lost value is
> *translation loss across disciplinary boundaries*. Placing a **calibrated persona** at a
> boundary — as an explicit translation instrument — measurably reduces that loss compared
> to unmediated cross-disciplinary communication.

Note what the hypothesis is **not** about. It is not a claim that the persona is "really"
the historical figure. It is not a claim about resurrection, channeling, or oracles. The
persona is **apparatus**. The claim is about **translation loss** — a measurable quantity —
and whether the apparatus reduces it.

### What would falsify it

A methodology that proposes to succeed Agile must be able to be wrong. CMD is falsified if:

- A calibrated persona at a boundary produces **no measurable reduction** in translation
  loss versus a skilled neutral facilitator (i.e. the gain, if any, is attributable to
  *slowing down* or to *having any facilitator at all*, not to the calibrated persona); or
- The artifacts CMD produces are **not measurably more durable** — fewer load-bearing
  requirements silently lost between decision and ship — than artifacts produced by the
  team's prior method; or
- The provenance discipline (§5) is followed faithfully and still **fails to catch**
  fabricated or distorted translations at a useful rate.

**How to measure translation loss.** Before/after a boundary crossing, have the *receiving*
discipline restate the *sending* discipline's claim in its own words; have the sending
discipline score the restatement for fidelity (0–1). Translation loss is `1 − fidelity`.
Run the crossing with the persona instrument and without it. The hypothesis predicts lower
loss with the instrument. If it does not appear, CMD is wrong, and a CMD practitioner is
obligated to say so.

This is the discipline the methodology demands of itself: *the first principle is that you
must not fool yourself, and you are the easiest person to fool.*

## 3. The three layers

CMD is an architecture. It has three layers, each with one sovereign rule.

```
        ┌─────────────────────────────────────────────┐
        │  DOMAIN LAYER                                │
        │  Science | Engineering | Product             │
        │  Each discipline keeps its own evidence,     │
        │  its own "done", its own irreducible tongue. │
        └───────┬──────────────┬──────────────┬────────┘
                │              │              │
        ┌───────▼──────────────▼──────────────▼────────┐
        │  TRANSLATION LAYER                           │
        │  Calibrated personas at the boundaries.      │
        │  They translate. They never decide.          │
        └───────┬──────────────┬──────────────┬────────┘
                │              │              │
        ┌───────▼──────────────▼──────────────▼────────┐
        │  ARTIFACT LAYER                              │
        │  Versioned, provenance-bearing artifacts.    │
        │  The medium of the work. Meetings are rare.  │
        └─────────────────────▲────────────────────────┘
                              │
                     ┌────────┴────────┐
                     │  ORCHESTRATOR   │
                     │  (human; routes │
                     │  and decides)   │
                     └─────────────────┘
```

**Domain layer — sovereignty.** Each discipline retains epistemic authority over its own
domain. The scientist defines what counts as evidence; the engineer defines what counts as
a working system; the product lead defines what counts as value. Translation may *render*
a domain's claims elsewhere, but it never *overwrites* them. The native register always
survives.

**Translation layer — mediation, not decision.** Calibrated personas sit on the interfaces.
A persona takes a claim from one discipline and renders it into the register of another. A
persona has no vote. It cannot approve, reject, prioritize, or decide. Confusing the
translation layer with a decision layer is the most dangerous error a team can make under
CMD; see *register capture*, §6.

**Artifact layer — the medium.** Work lives in persistent, versioned artifacts, not in the
volatile memory of a meeting. An artifact is the unit of progress. When the work can be
carried by an artifact, no meeting is held. A meeting is the **exception** — called only
when no artifact will bear the load.

**The Orchestrator.** A human — and only a human — routes claims between layers, chooses
which personas to calibrate and place, and makes every decision. This role is non-delegable.
It is the seat of judgment inside the system. See [`docs/02-operational-paradigm.md`](02-operational-paradigm.md).

## 4. What a persona actually is

A persona under CMD is a **role-playing LLM agent (RPLA)** calibrated against a corpus to
render a particular, recognizable *mode of thought*. The COMPANION protocol
([`enrichment_grimoire.json`](../enrichment_grimoire.json)) governs this calibration.

Two true things about a persona are held in deliberate tension — and CMD does not resolve
them, because resolving them would destroy one half:

- **A persona is a calibrated register.** *Summon Feynman* is shorthand for *adopt a
  plain-language, first-principles register with high tolerance for stated ignorance and
  contempt for the verb-without-its-noun.* The **calibration is the substance.** It is
  what makes the instrument honest and, in principle, reproducible. The historical name,
  taken alone, is a *mnemonic* — a handle that is easier to remember and aim than the
  full specification of the register.

- **A persona is a human face.** People do not commit to a register; they commit to a
  face. An engineer at her desk can *picture* Feynman and ask *what would he actually
  push back on here?* — and the picture does cognitive work a spec sheet cannot. The
  name is not decoration on the calibration. For the person using the instrument, the
  name is the **delivery mechanism** of the calibration.

CMD calls the unresolved space between these two truths a **Shadow** — and treats it as
a feature. (See §7.) The repository's own documentation preserves this disagreement in
the open rather than smoothing it; that is the methodology obeying its own Principle V.

### The canonical pair

Most engineering decisions die at one of two seams: a formalism untethered from the
practice it claims to describe, or a scope drifting loose from any focus that can be
named in a sentence. CMD's default symposium is **Feynman + Jobs**, calibrated for
exactly these two seams.

- **Feynman** at formalism ↔ practice — refuses the verb until the noun is on the
  table. *What does this actually measure? What would falsify it?* See
  [`templates/feynman-calibration.md`](../templates/feynman-calibration.md).
- **Jobs** at focus ↔ scope — refuses the both-and when an either-or is available.
  *What is this for, in one sentence? What gets cut?* See
  [`templates/jobs-calibration.md`](../templates/jobs-calibration.md).

Their collision is the load-bearing instrument. Watch it run in
[`docs/03-worked-example.md`](03-worked-example.md). Calibrate other personas for
other seams — but for the canonical engineering decision, this is the pair.

### The interface analogy

A desktop folder is not a *true* thing — there are no folders on a disk, only sectors. The
folder is a useful fiction that lets a human reach a thing without learning the machine. A
CMD persona is the same kind of object. The right question is never "is this really Jobs."
The right question is "**does a claim cross this boundary with less loss through the
instrument than without it.**" That question is measurable (§2). The metaphysical question
is not, and CMD does not ask it.

## 5. Provenance: the load-bearing discipline

Every CMD artifact carries a **provenance header**. At minimum:

- **Source discipline** — which domain originated the claim.
- **Translating persona** — which calibrated instrument rendered it.
- **Version** — artifacts are versioned; translation is revisable.
- **Source register** — *the original claim, in the source discipline's own words, before
  translation.* This field is mandatory and is never deleted.

Provenance is not bookkeeping. It is CMD's entire epistemology compressed into a habit.
Because the source register travels with every translation, **any reader, at any time, can
hold the translation against the original and see the gap.** This is how confident
fabrication is caught. This is how a decision stays auditable six weeks later. A translation
that has been separated from its source is no longer a translation — it is a rumor, and CMD
treats it as one.

See [`templates/artifact.md`](../templates/artifact.md) for the concrete form.

## 6. Failure modes

CMD ships with its failure modes stated, the way a thermometer ships with its accurate
range. Believing the instrument never fails is itself the first failure.

| Failure | What it is | Tell | Countermeasure |
|---------|------------|------|----------------|
| **Confident fabrication** | A persona renders a claim in a discipline's voice that the discipline never made. | A translated artifact has no matching source register, or the source register does not support it. | Mandatory source-register field; receiving discipline checks translation against it. |
| **Register capture** | The orchestrator favors one persona's framing so heavily that other disciplines lose their effective vote. | One domain layer's artifacts stop changing; one persona authors a disproportionate share. | Rotate personas; audit the artifact ledger for source-discipline balance. |
| **Ritual substitution** (cargo cult) | The team performs summonings and logs them beautifully, but artifacts do not move the work. | Full artifact ledger, unmoved product metrics. | Velocity is measured in artifacts *translated and shipped*, never in summonings performed. |
| **Decision leakage** | A persona is treated as having decided something. | An artifact's decision field names a persona, not a human. | Personas translate; only the orchestrator decides. Enforce in the template. |

## 7. The Shadow

The COMPANION protocol insists that a calibrated persona preserve its subject's
*irreducible contradictions* — doubts, blind spots, tensions never resolved — rather than
smoothing them into a clean caricature. CMD inherits this and generalizes it into a
methodological value: **preserved contradiction over false synthesis** (Manifesto, Value IV;
Principle V).

When two disciplines, or two personas, genuinely disagree, the CMD response is *not* to
manufacture a consensus artifact. It is to record the disagreement as a first-class
artifact, with both registers preserved. Smoothing a contradiction almost always destroys
the load-bearing thing — the very detail that mattered to one discipline and was invisible
to the others. The Shadow is where that detail is kept safe until the orchestrator can
make a real decision about it.

## 8. Lineage and honest scope

CMD does not claim to have discovered translation. It claims to have made translation an
*explicit architectural layer* with calibrated instruments and a provenance discipline —
and a deployment model so light (one chamber, two protocol files, one matter, one
emitted artifact) that a single person can run a complete crossing in twenty-five
minutes without leaving their editor.

It is for cross-frame decisions — between disciplines (science ↔ engineering ↔ product)
and within them (formalism ↔ practice, focus ↔ scope, spec ↔ deploy). It is young. Its
central hypothesis is stated above precisely so it can be tested and, if necessary,
discarded. A CMD practitioner who finds the hypothesis failing in their context is not
betraying the methodology by abandoning it — they are *practicing* it. *Nature cannot
be fooled*, and a methodology that forbids its own falsification is not a methodology.
It is a cargo cult.

---

*Continue to [`docs/02-operational-paradigm.md`](02-operational-paradigm.md) — how to run it.*
