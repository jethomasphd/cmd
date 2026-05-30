---
layout: default
title: CMD and Agile
---

# CMD and Agile

*What CMD keeps, what it rejects, and the projects where Agile still wins. Read this
before you adopt CMD — and read it with attention if you suspect, as many engineering
managers now do, that the synchronous brainstorm is the wrong primitive.*

CMD does not arrive as Agile's enemy. Agile solved a real problem and solved it well
for a quarter century. CMD claims only that Agile solved the *wrong* problem for one
specific class of work — and that this class is large enough, and painful enough, to
deserve its own method.

---

## 1. The brainstorm critique — read this first

The synchronous brainstorm is Agile's most-used and least-examined ceremony. Watch one
honestly:

- **Five engineers, ninety minutes, one decision in front of them.** Cost on the
  calendar: 7.5 person-hours, plus context-switch cost on either side, plus the
  decision having to wait for the next available joint slot — usually mid-week.
- **The output is volatile.** No artifact leaves the room with the load preserved.
  What leaves is three different recollections, a Slack recap that smooths what was
  actually unresolved, and one Jira ticket whose title is the only thing anyone
  agrees on.
- **The strongest voice wins by default.** Not because the strongest voice was right
  — because the room is a real-time medium and real-time media favor confidence over
  correctness. The quiet engineer whose objection was load-bearing did not get her
  sentence out, and the team will rederive her objection in three weeks, expensively.
- **Disagreement is treated as a problem to dissolve.** The room is uncomfortable
  with preserved contradiction, so it manufactures a consensus the disagreement did
  not have. The load-bearing detail — the contradiction itself — is exactly what is
  smoothed away.
- **The decision rots by Friday.** Nothing carries it. By next month the team is
  having the meeting again, and nobody is sure what was decided the first time.

The brainstorm is not a bad meeting because the people are bad. It is a bad
*instrument*. Real-time, synchronous, volatile-output, consensus-seeking, low-quorum-
threshold — every property is wrong for cross-frame decisions where preserved
disagreement is the load-bearing thing.

**CMD's answer is not a better meeting. It is a different instrument.** A `.md` matter,
a chamber, a calibrated pair of summoned minds, a single durable artifact emitted.
Twenty-five minutes at one person's desk. The disagreement preserved on purpose. The
artifact auditable in week eight.

The brainstorm was the wrong primitive. CMD names this directly and replaces it.

---

## 2. The disagreement, stated precisely

| | **Agile** | **CMD** |
|---|-----------|---------|
| Names the bottleneck as… | Coordination — specialists are out of sync. | Translation — frames' languages do not commute. |
| So the fix is… | Put specialists in a room; iterate fast; coordinate often. | Put a calibrated instrument *at the boundary*; translate with provenance. |
| The medium of work is… | The increment of working software, surfaced in ceremonies. | The versioned, provenance-bearing `.md` artifact. |
| Meetings are… | The heartbeat (stand-up, planning, review, retro, the brainstorm). | The exception, called only when no artifact can carry the load. |
| Velocity is… | Story points completed per sprint. | Artifacts translated and shipped. |
| Consensus is… | A goal — the team aligns. | Often a trap — false synthesis destroys load-bearing detail. |
| Disagreement is… | Resolved before moving on. | Preserved as a Shadow artifact when it is real. |
| Decision authority… | Distributed across a self-organizing team. | Held by a single human Orchestrator; never by an instrument. |
| Failure to ship is… | A retro item — process to tune. | A measurement — translation loss to count and lower. |

---

## 3. What CMD keeps from Agile

CMD is a descendant, not a repudiation. It inherits:

- **The manifesto form.** A short statement of values over a long process spec. CMD's
  manifesto is deliberately built in Agile's mold — values on the left, *"while there
  is value in the items on the right"* — as an act of acknowledged lineage.
- **Iteration over big-design-up-front.** The CMD loop turns continuously; artifacts
  are versioned and revised.
- **Working output over documentation theater.** CMD's artifact is not a Word
  document nobody reads; it is the live, audited medium of the work.
- **Empiricism.** Agile insisted on inspecting reality at the end of each sprint. CMD
  insists on measuring translation loss at every boundary crossing. Same instinct,
  different instrument.
- **Cheap to try.** Agile won because you could run one sprint and see. CMD is
  adoptable one boundary at a time, with a measurement attached. (See
  [`docs/02-operational-paradigm.md`](02-operational-paradigm.md) §7.)

---

## 4. What CMD rejects

- **The room as the fix.** Adding people and meetings to a translation gap widens the
  gap; it does not close it. A brainstorm is the wrong instrument for cross-frame
  work.
- **Ceremony as cadence.** Stand-ups, planning, and retros pace the work by the
  calendar. CMD paces the work by the artifact. The calendar is not a metric.
- **Consensus as a default good.** Agile drives toward team alignment. CMD holds
  that when frames genuinely disagree, a manufactured consensus usually deletes the
  one detail that mattered. CMD preserves the contradiction instead.
- **Distributed decision authority for cross-frame calls.** A self-organizing team
  is excellent within a frame. Across frames it produces the three-different-accounts
  failure. CMD names **one** human Orchestrator and makes the seat of judgment
  explicit and non-delegable.
- **Time-boxing translation.** A translation that takes the time it takes. Forcing
  it into a sprint produces a translation that misses the load-bearing thing.

---

## 5. Where Agile still wins — use it, not CMD

This section is not a courtesy. It is a load-bearing part of the methodology. CMD is
for one situation; everywhere else, **Agile is the better tool and CMD should stay
home.**

Use Agile, not CMD, when:

- **The work is single-frame.** Two engineers building a CRUD endpoint share a
  language. There is no boundary to translate across. CMD would only add overhead.
- **The frames already share a working language.** Some teams have, over years,
  built a genuine shared vocabulary. They have already solved the translation problem
  socially. CMD's instrument would be redundant.
- **The work is well-understood and repeatable.** Shipping the next variant of a
  known feature does not stress a boundary. Sprint it.
- **Speed of throughput dominates.** Agile's ceremony overhead is low and
  predictable. CMD's provenance discipline is real work. For high-volume, low-ambiguity
  delivery, Agile's economics win.
- **You cannot or will not measure translation loss.** CMD without its measurement
  is a cargo cult. If the measurement is impossible in your context, do not adopt CMD;
  you would only get the ritual.

A methodology that claims everything has claimed nothing. CMD claims one thing, and
turns the rest of the world's projects away at the door on purpose.

---

## 6. Can they coexist?

Yes — and in most organizations they should. CMD operates at the **seams** between
frames; Agile operates **within** a frame's delivery. A realistic shop runs Agile
inside engineering, inside the data-science team, inside product delivery — and runs
CMD on the three or four boundaries where those teams must hand load-bearing claims
to one another.

The personal-hub variant of CMD goes further: a single engineer or engineering manager
can run CMD as their own private practice — a chamber on their laptop, an artifact
ledger in their vault — while the rest of the team runs its Agile cadence unchanged.
The artifacts they emit travel back into the team's medium as `.md` decision records
that the team can read, contest, and version. Adoption does not require permission. It
requires one boundary, one matter, twenty-five minutes, and the willingness to keep
the source register beside the translation.

CMD is not a replacement for how you build. It is a replacement for how you *translate
while you build* — and a replacement for the brainstorm that was supposed to do that
translation and could not.

---

*Continue to [`docs/05-the-summoning.md`](05-the-summoning.md) — the working that built
this repository, with Jobs and Feynman in symposium.*
