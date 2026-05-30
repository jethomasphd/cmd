---
layout: default
title: CMD and Agile
---

# CMD and Agile

*What CMD keeps, what it rejects, and the projects where Agile still wins.*

CMD does not arrive as Agile's enemy. Agile solved a real problem and solved it well for a
quarter century. CMD claims only that Agile solved the *wrong* problem for one specific
class of work — and that this class is large enough, and painful enough, to deserve its own
method. This page is written to be fair to Agile, because a methodology that can only beat
a strawman has beaten nothing.

---

## 1. The disagreement, stated precisely

| | **Agile** | **CMD** |
|---|-----------|---------|
| Names the bottleneck as… | Coordination — specialists are out of sync. | Translation — specialists' languages do not commute. |
| So the fix is… | Put specialists in a room; iterate fast; coordinate often. | Put a calibrated instrument *at the boundary*; translate with provenance. |
| The medium of work is… | The increment of working software, surfaced in ceremonies. | The versioned, provenance-bearing artifact. |
| Meetings are… | The heartbeat (stand-up, planning, review, retro). | The exception, called only when no artifact can carry the load. |
| Velocity is… | Story points completed per sprint. | Artifacts translated and shipped. |
| Consensus is… | A goal — the team aligns. | Often a trap — false synthesis destroys load-bearing detail. |
| Disagreement is… | Resolved before moving on. | Preserved as a Shadow artifact when it is real. |
| Decision authority… | Distributed across a self-organizing team. | Held by a single human Orchestrator; never by an instrument. |

## 2. What CMD keeps from Agile

CMD is a descendant, not a repudiation. It inherits:

- **The manifesto form.** A short statement of values over a long process spec. CMD's
  manifesto is deliberately built in Agile's mold — values on the left, "while there is
  value in the items on the right" — as an act of acknowledged lineage.
- **Iteration over big-design-up-front.** The CMD loop turns continuously; artifacts are
  versioned and revised.
- **Working output over documentation theater.** CMD's artifact is not a Word document
  nobody reads; it is the live medium of the work.
- **Empiricism.** Agile insisted on inspecting reality at the end of each sprint. CMD
  insists on measuring translation loss at every boundary crossing. Same instinct, different
  instrument.
- **Cheap to try.** Agile won because you could run one sprint and see. CMD is adoptable one
  boundary at a time, with a measurement attached. (See
  [`docs/02-operational-paradigm.md`](02-operational-paradigm.md) §7.)

## 3. What CMD rejects

- **The room as the fix.** Adding people and meetings to a translation gap widens the gap;
  it does not close it.
- **Ceremony as cadence.** Stand-ups, planning, and retros pace the work by the calendar.
  CMD paces the work by the artifact.
- **Consensus as a default good.** Agile drives toward team alignment. CMD holds that when
  disciplines genuinely disagree, a manufactured consensus usually deletes the one detail
  that mattered. CMD preserves the contradiction instead.
- **Distributed decision authority for cross-disciplinary calls.** A self-organizing team is
  excellent within a discipline. Across disciplines, it produces the three-different-accounts
  failure. CMD names one human Orchestrator and makes the seat of judgment explicit.

## 4. Where Agile still wins — use it, not CMD

This section is not a courtesy. It is a load-bearing part of the methodology. CMD is for one
situation; everywhere else, **Agile is the better tool and CMD should stay home.**

Use Agile, not CMD, when:

- **The work is single-discipline.** Two engineers building an API share a language. There
  is no boundary to translate across. CMD would only add overhead.
- **The disciplines already share a working language.** Some teams have, over years, built
  a genuine shared vocabulary. They have already solved the translation problem socially.
  CMD's instrument would be redundant.
- **The work is well-understood and repeatable.** Shipping the next variant of a known
  feature does not stress a boundary. Sprint it.
- **Speed of throughput dominates.** Agile's ceremony overhead is low and predictable. CMD's
  provenance discipline is real work. For high-volume, low-ambiguity delivery, Agile's
  economics win.
- **You cannot or will not measure translation loss.** CMD without its measurement is a
  cargo cult. If the measurement is impossible in your context, do not adopt CMD; you would
  only get the ritual.

A methodology that claims everything has claimed nothing. CMD claims one thing, and turns
the rest of the world's projects away at the door on purpose.

## 5. Can they coexist?

Yes — and in most organizations they should. CMD operates at the **seams** between
disciplines; Agile operates **within** a discipline's delivery. A realistic shop runs Agile
inside engineering, inside the data-science team, inside product delivery — and runs CMD on
the three or four boundaries where those teams must hand load-bearing claims to one another.

CMD is not a replacement for how you build. It is a replacement for how you *translate while
you build*. Adopt it exactly that narrowly, and it will earn its place. Adopt it wider than
that, and it will become the thing it was written to replace.

---

*Continue to [`docs/05-the-summoning.md`](05-the-summoning.md) — the working that built this
repository.*
