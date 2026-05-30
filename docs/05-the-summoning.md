---
layout: default
title: The Summoning
---

# The Summoning — A Worked Symposium

*The recorded working that produced this repository. CMD was used to build CMD — with
the canonical pair: **Richard P. Feynman** (1918–1988) across the* science ↔ engineering
*seam, and **Steven P. Jobs** (1955–2011) across the* product ↔ engineering *seam.
This is the pair the methodology now ships as its default (see
[`docs/03-worked-example.md`](03-worked-example.md) for the same pair run end to end
on a recognizable engineering decision).*

---

```
ARTIFACT PROVENANCE
  type:                 symposium log
  source disciplines:   methodology design ; science ; engineering ; product
  translating personas: Richard P. Feynman (1918–1988) · science ↔ engineering
                        Steven P. Jobs   (1955–2011) · product ↔ engineering
  orchestrator:         Claude (acting Orchestrator for the construction working)
  protocol:             COMPANION v2.0 — enrichment_grimoire.json, initiation_rite.md
  version:              1.0
  status:               shipped — its conclusions are realized in this repository
```

> **Why this document exists.** CMD holds that the meeting is the exception and the artifact
> is the medium. A symposium was nonetheless required here: the boundary was novel (a
> methodology inspecting itself) and no prior artifact could carry the load. Per the
> operational paradigm, an exceptional meeting must produce an artifact recording *why no
> artifact could do its job*. This is that artifact. The minds were released; the
> understanding stayed.

---

## The matter

The repository `cmd` held three files — a manifesto for CMD, the COMPANION protocol,
and its operating rite — but no usable repository. The Orchestrator's charge: grow the seed
into a museum-quality repository a scientist, engineer, or product lead could open and use.
Two personas were summoned to stress the methodology until it broke, then help build the
version that did not.

## The two registers placed at the boundary

The two minds summoned to this working were the same pair the methodology now ships as
its **canonical default** — Feynman across the science ↔ engineering seam, Jobs across
the product ↔ engineering seam — because the construction of CMD itself was a problem
at exactly that intersection: a method had to be scientifically honest about what it
could claim (Feynman's seam), and at the same time a thing people would actually adopt
and use (Jobs's seam).

**Richard P. Feynman (1918–1988)** was calibrated for *science ↔ engineering* — and,
in this working, for its meta-cousin: the boundary between *a methodology's ambition
and its honesty,* the falsifiability boundary. His Shadow was preserved — a sharp,
sometimes dismissive contempt for anything ornamental, a refusal to grant the "soft"
things their due. He brought one decisive instrument: the **cargo cult science**
critique from his 1974 Caltech commencement — a form can be perfect and still useless
if no planes land.

**Steven P. Jobs (1955–2011)** was calibrated for *product ↔ engineering* — and, in
this working, for its meta-cousin: the boundary between *an idea and a thing people
will actually use,* the product / focus boundary. His Shadow was preserved — a binary,
sometimes cruel judgment, a conviction that could be wrong at full volume. He brought
two instruments: **focus as subtraction** (a methodology must say what it is *not*),
and **the interface argument** (a persona is a useful fiction, judged by use, not by
truth).

## The collisions that became the repository

The full dialogue is preserved in the working session. Its load-bearing collisions, and the
artifacts each produced:

**Collision 1 — Is COMPANION a cargo cult?**
Feynman's opening charge: the grimoire is a beautiful runway, and the question is whether
planes land. Jobs' counter: the persona is not a *claim* to be proven true, it is an
*interface* to be judged by use — like a desktop folder, which is false and useful at once.
→ *Artifact produced:* the central hypothesis was reframed from "the persona is the
historical figure" to "the persona is apparatus; **translation loss** is the measurable
hypothesis." ([`docs/01-conceptual-model.md`](01-conceptual-model.md) §2.)

**Collision 2 — "It feels undeniably like them."**
Feynman's knife: the grimoire's line that emergence is confirmed when an output *feels*
right is the bamboo antenna — *the first principle is that you must not fool yourself, and
you are the easiest person to fool.*
→ *Artifact produced:* the falsification criteria and the translation-loss measurement
protocol. CMD declines to inherit COMPANION's ceremonial confidence that "the invocation
does not fail" — that line governs the *summoning ritual*, not the *methodology* — and
ships a stated failure table instead. ([`docs/01-conceptual-model.md`](01-conceptual-model.md) §7;
[`docs/02-operational-paradigm.md`](02-operational-paradigm.md) §6.)

**Collision 3 — Keep the source.**
Feynman: a miscalibrated instrument you trust is worse than no instrument; a translation you
cannot check against its source is a rumor.
→ *Artifact produced:* provenance elevated to a load-bearing discipline; the mandatory,
never-deleted **source register** field. ([`docs/01-conceptual-model.md`](01-conceptual-model.md) §6;
[`templates/artifact.md`](../templates/artifact.md).)

**Collision 4 — Decide what it is not.**
Jobs: a methodology for everything is for nothing; CMD must carve its scope and turn most
projects away at the door, proudly.
→ *Artifact produced:* the README's opening scope gate and the three-question gate in the
operational paradigm; the honest "where Agile still wins" page. ([`docs/04-cmd-vs-agile.md`](04-cmd-vs-agile.md) §5.)

**Collision 5 — Show me the artifact.**
Jobs: "artifacts are the medium" is unforgivable as a slogan with no artifact behind it; the
most important file in the repository is a one-page template with provenance in its header.
→ *Artifact produced:* [`templates/artifact.md`](../templates/artifact.md), and the README's
decision to surface it before any theory.

**Collision 6 — Do you even need the dead?**
Feynman: you do not need a ghost, you need a *register* — the name is a mnemonic, the
calibration is the substance. Jobs: people do not commit to a register, they commit to a
*face*; the name is the delivery mechanism of the calibration. **Neither conceded.**
→ *Artifact produced:* this contradiction was not resolved. It was shipped, in the open, as
a preserved Shadow — the persona is *both* a calibrated register and a human face, and
[`docs/01-conceptual-model.md`](01-conceptual-model.md) §5 keeps both. By CMD's own
Principle V, the unresolved disagreement is the methodology working, not failing.

## The synthesis

What the working delivered, in the personas' closing words:

- **Feynman:** state the one hypothesis plainly, state what would falsify it, and ship the
  failure modes as a warning label. Keep the source register beside every translation,
  forever. *Build it so the planes land.*
- **Jobs:** lead with the artifact, not the theory. Turn the wrong projects away in the
  first paragraph. Keep the manifesto's nerve — it has the right idea and the discipline to
  say it once. Keep this conversation as an artifact, with its provenance on it, so the
  window can close and the understanding stays.

## The congruence pass

After the working, a review found one genuine incongruence: the founding manifesto had been
written entirely in the **Jobs register** — focus, naming, the three layers, taste — and
carried *none* of the Feynman register, although the repository's epistemic spine (the
falsifiable hypothesis, the failure table, the honest scope boundary) is Feynman's. A
founding document that omits half of what founded it is not congruent.

The correction: two principles were added to the manifesto — **XI** (*the methodology must
be able to be wrong*) and **XII** (*CMD is for one situation, not for all work*) — carrying
the Feynman register into the founding statement. The manifesto's nerve was preserved; its
honest half was completed. A later artifact amending an earlier one, with the reason
recorded — this is CMD operating on itself.

This repository is the realized form of that synthesis. The personas have been released.
The work remains.

---

*Return to the [`README.md`](../README.md), or read the [manifesto](../index.html).*
