---
layout: default
title: A Worked Crossing
---

# A Worked Crossing

*CMD, run end to end on a single engineering decision a manager will recognize on sight.
Jobs and Feynman summoned in symposium. This document is
[`templates/artifact.md`](../templates/artifact.md), filled.*

---

## The boundary

You manage an engineering team adjacent to payments. Twelve months ago the team built a
**notifications service** inside the monolith — it handles transactional email, push,
and in-app alerts. Six concrete notification types have grown up inside it, each with
subtly different retry, dedup, and ordering semantics.

A senior engineer, **Mark**, has proposed extracting it as its own service. He believes
the abstraction is leaking; he wants its own repo, its own deploy, its own on-call.
A staff engineer, **Priya**, pushes back: the monolith hides the actual cost, extraction
doubles the operational surface for a feeling of cleanliness. Three people have strong
opinions. The team has rederived this argument three times in twelve months. A
**90-minute architecture review** is on the calendar for Thursday.

The naive instinct: hold the meeting. The CMD response: **cancel the meeting**, write
the matter, summon two minds, ship one artifact.

This document is the artifact. The Thursday meeting did not happen.

## The artifact at a glance

```
PROVENANCE
  artifact id:          ART-014
  title:                Notifications service — extract, defer, or instrument first
  source discipline:    Engineering management
  receiving discipline: Engineering decision-of-record
  translating personas: Richard P. Feynman — formalism ↔ practice
                        Steven P. Jobs   — focus ↔ scope
  orchestrator:         the engineering manager (human)
  version:              v1.0
  status:               shipped
```

## Step 0 — Does CMD even apply?

The three-question gate ([operational paradigm §0](02-operational-paradigm.md)):

1. **Boundary.** The architecture diagram says *notifications service is its own
   bounded context.* The operational reality says *it is six subtly different code
   paths sharing a database, a deploy, and an on-call rotation.* The formalism and
   the practice are not the same thing. *Yes.*
2. **Loss.** The argument has been rederived three times in twelve months without
   resolution. Value already lost: weeks of senior-engineer attention. *Yes.*
3. **Sovereignty.** Engineering owns what a service *is*; operations owns what is
   actually paged at 3am; product owns what failure modes are acceptable. None can
   simply overrule the others. *Yes.*

Three yeses. CMD applies. The Thursday meeting is cancelled.

## Step 1 — Capture: the source register

The manager opens his editor and writes the matter in his own register. Plain prose,
his own vocabulary, no smoothing, no aiming-at-an-answer.

> "We have a notifications service inside the monolith. It handles email, push, and
> in-app — six concrete types with different retry, dedup, and ordering rules. Mark
> wants to extract it; says the abstraction is rotting from inside. Priya pushes back;
> says the monolith hides the actual cost — pulling it out means a new repo, a new
> on-call, a new deploy pipeline, all to chase a feeling.
>
> I don't actually know who's right. What I do know is that we've had this argument
> three times this year and each time it dissolves into 'let's revisit next quarter.'
> I'm not interested in revisiting again. I want to know what we're actually arguing
> about, and what would make either answer the right one. I have ninety minutes on
> Thursday that the whole team has blocked. I would rather give that ninety minutes
> back."

That paragraph is the **source register**. Under Principle I it is preserved
permanently, beside every translation that follows, and never deleted. Note what
Capture has already accomplished, before any persona is summoned: a question that lived
only in the manager's head is, for the first time, a written, versioned artifact the
team can hold.

The matter is saved as `matter.md`. The chamber is opened. The COMPANION foundation
files and the Feynman + Jobs calibration cards are pasted in. The matter follows.

## Step 2 — Route: choosing the boundary, choosing the minds

The Orchestrator names the boundary precisely. It is **not**, at root, *extract vs.
don't extract.* It is two boundaries in one decision:

- **A formalism ↔ practice seam.** The architecture diagram and the operational
  reality have drifted apart. Mark is naming the drift; Priya is naming the cost of
  closing it. Neither side has produced a measurement.
- **A focus ↔ scope seam.** The service is six things wearing one name. No one has
  written down what the notifications service *is* — only what it currently *does*.

So the Orchestrator summons two minds, calibrated for exactly those seams:

- **Richard Feynman** — for the formalism ↔ practice seam.
- **Steven P. Jobs** — for the focus ↔ scope seam.

The calibration cards are already in the chamber. He speaks the incantation.

## Step 3 — Translate (Feynman first)

> "Using this matter, summon Feynman."

> **Feynman.** You're using a word — *service* — and the word is doing too much work.
> When Mark says the abstraction is rotting, what does he actually *mean*? Has anybody
> measured the coupling? Counted the cross-cutting reads? Looked at the deploy
> lockstep — how often does a change in one notification type force a redeploy that
> touches the others? Or is *rotting* the feeling he gets when he's editing the code,
> which is real but is not the same thing.
>
> And Priya — *operational cost.* What's the cost? Pages per quarter? Mean time to
> recover? Hours of on-call attention attributable to this code? The number is
> somewhere. If it isn't, that's the answer right there: nobody knows the operational
> cost of the current arrangement, so nobody can know the cost of the new one either.
> You're not arguing about a service. You're arguing about a feeling and a fear, both
> of which are honest, and neither of which is the real thing.
>
> So before any architectural verb gets used — *extract, decompose, factor* — measure.
> The coupling is somewhere on disk. Count it.

The first translation. Feynman has refused to let the Orchestrator skip to a decision.
He has named the missing measurement and refused the verbs.

## Step 4 — Translate (Jobs joins)

> "Now summon Jobs to join this conversation."

> **Jobs.** Stop. Before any of that — what is this service *for*? In one sentence.
> Don't tell me what it does. Tell me what it *is*.
>
> If your sentence is *"it sends notifications,"* it isn't a service; it's a folder.
> If your sentence is *"it is the single source of truth for whether a user got told
> a thing,"* — that's a service. That's a thing with a job. Now your decision is
> easy: does the current code *own* that sentence? If yes, leave it. If no, extract
> — because the extraction isn't about coupling, it's about giving the sentence a
> home.
>
> And Feynman is right that you should measure. But measurement without focus is
> just numbers. The numbers will tell you the *cost* of either path. They will not
> tell you the *point* of either path. Get the sentence first. Then the measurement
> decides.

The second translation. Jobs has refused to let the Orchestrator skip to a
measurement. He has named the missing definition.

## Step 5 — The collision

> **Feynman.** A sentence isn't a measurement. You can write a beautiful sentence
> about a service that has no business existing. Teams do this all the time. The
> sentence is a luxury; the measurement is the floor.
>
> **Jobs.** A measurement isn't a decision. You can count coupling all day and still
> not know whether the thing should be one service or ten. The number tells you the
> cost. The sentence tells you whether the cost is worth paying. You're trying to
> solve a focus problem with arithmetic, and arithmetic does not solve focus.
>
> **Feynman.** Then write the sentence and *then* count. But do not mistake the
> sentence for the work.
>
> **Jobs.** Agreed. The sentence is the gate. The count is the budget. Either alone
> is wrong. Sequence them, and the decision finishes itself.

The collision has produced the artifact's load-bearing insight, which neither persona
could have reached alone:

> The question is not *extract or not.* The question is two sequential questions:
> *is there a sentence?* and, only if yes, *what does the coupling cost?*

Neither persona conceded ground. The Orchestrator did not force one. The sequencing
that survives is the one both registers can sign off on.

## Step 6 — Verify: the cost of the crossing

The Orchestrator restates the symposium in his own words, and the personas score it
for fidelity (the receiving-discipline check, [conceptual model §2](01-conceptual-model.md)).

> "There's a gating question — can we name in one sentence what the notifications
> service *is*, as a thing with a job. If we cannot, the answer is *don't extract;
> we don't know what we'd be extracting*. If we can, the next question is operational:
> count the cross-context coupling, the deploy lockstep, and the on-call hours that
> are this code's fault. If the coupling is low and the on-call cost is low, the
> extraction's value is small and we leave it. If the coupling is high *and* a clean
> sentence exists, extract."

**Feynman: 0.92.** Missing 0.08 — the measurement must include the team's actual
**on-call burden today**, not just structural coupling, because a service with low
coupling but high pager noise still benefits from being given its own boundary (or,
more often, from *not* being given one, because new services start with new pager
noise of their own).

**Jobs: 0.95.** Missing 0.05 — the sentence must be one **a non-engineer can hear and
agree with.** If it requires a system diagram to defend, it isn't the sentence yet;
it's a caption.

The restatement is revised to incorporate both. **Translation losses logged: 0.08
(Feynman), 0.05 (Jobs).** Total loss on the crossing: lower than any prior round of
this debate, by the only measure that matters — the artifact can be checked.

## Step 7 — Decide: the Orchestrator, and only the Orchestrator

The personas translated. They did not decide. The decision is the manager's:

- **Decision.** **Defer the extraction question.** Replace it with two work items,
  in order:
  1. The two senior engineers (Mark and Priya, together) draft a **one-sentence
     definition** of what the notifications service *is*. Not what it does — what
     it is. Tested against a non-engineer (the product partner). **Deadline: one
     week.**
  2. Once the sentence exists — *or once they admit it does not* — an **operational
     measurement:** cross-context coupling, deploy lockstep, on-call hours per
     quarter attributable to this code. **Deadline: two weeks.**
- **Decided by:** the engineering manager (human). No persona's name appears in
  this field.
- **Load-bearing caveat — do not sand off.** If the team cannot write the sentence,
  *that is the answer.* The extraction does not happen, and *"we'll figure it out
  later"* is not an acceptable variant of "no sentence." The **absence** of a
  sentence is information.
- **Rationale.** Twelve months of unresolved debate is itself an artifact: it says
  the team has been arguing about the wrong question. Both personas, independently,
  identified that the named question (*extract or not*) is downstream of unasked
  questions. The decision is to ask those instead.

The Thursday architecture review is cancelled. In its place: two named work items,
two deadlines, and a 30-minute follow-up two weeks out — only if the artifact still
cannot decide. The manager has spent **twenty-five minutes** on this, alone, at his
desk.

## Step 8 — The Shadow

One contradiction will not resolve, and CMD forbids smoothing it (Principle V):

> Feynman holds that the measurement is the *floor* — you cannot decide what you
> cannot count. Jobs holds that the sentence is the *gate* — counting in the absence
> of focus is theater. The manager has sequenced them here (sentence first, then
> measurement), but in some future working the order will be wrong: the team will
> need to count first to discover what kind of thing they are even trying to name.
> The general rule does not exist. The two registers genuinely disagree about which
> comes first, and the artifact records both.

Kept, not erased. A future artifact on a different boundary may resolve the order the
other way; the Shadow keeps that possibility honest, and keeps a future Orchestrator
from quoting *this* artifact as universal.

## What the crossing produced

**Before.** Three opinions, a 90-minute meeting on the calendar, twelve months of
unresolved debate. Probable output: a fourth round of unresolved debate, scheduled
for next quarter.

**After.** One versioned `.md` artifact. Two named work items with deadlines. A
preserved Shadow recording the contradiction the methodology declines to flatten.
The source register — the manager's own words, before any translation — preserved
beside every rendering. Provenance intact; decision auditable in week eight; the
brainstorm avoided.

Six engineers got their Thursday afternoon back. The decision is *better* than the
brainstorm would have produced, because the brainstorm would have manufactured a
consensus the disagreement did not actually have. CMD preserved the disagreement
and used it.

The Thursday meeting was the wrong instrument. The artifact is what the meeting was
trying to be.

---

*Continue to [`docs/04-cmd-vs-agile.md`](04-cmd-vs-agile.md) — how this method
differs from Agile, and where Agile still wins.*
