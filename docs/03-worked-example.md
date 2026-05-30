---
layout: default
title: A Worked Crossing
---

# A Worked Crossing

*CMD, run end to end on a single engineering decision a manager will recognize on
sight. The canonical pair summoned in symposium — Feynman across the* ***science ↔
engineering*** *seam, Jobs across the* ***product ↔ engineering*** *seam — with
engineering at the center where the decision sits. This document is*
[`templates/artifact.md`](../templates/artifact.md), *filled.*

---

```
CASE STUDY · ART-014
Notifications service — extract, defer, or instrument first
Dated:                  2026
Discipline boundaries:  SCIENCE ↔ ENGINEERING (measurement of coupling, on-call cost)
                        PRODUCT ↔ ENGINEERING (what the service IS to a user)
Personas summoned:      Richard P. Feynman (1918–1988) · sci ↔ eng
                        Steven P. Jobs    (1955–2011) · prod ↔ eng
Orchestrator:           the engineering manager (human)
Method:                 CMD — this repository
Version:                v1.0
Status:                 shipped
```

---

## The boundary

You manage an engineering team adjacent to payments. Twelve months ago the team
built a **notifications service** inside the monolith — it handles transactional
email, push, and in-app alerts. Six concrete notification types have grown up
inside it, each with subtly different retry, dedup, and ordering semantics.

A senior engineer, **Mark**, has proposed extracting it as its own service. He
believes the abstraction is leaking; he wants its own repo, its own deploy, its
own on-call. A staff engineer, **Priya**, pushes back: the monolith hides the
actual cost, extraction doubles the operational surface for a feeling of
cleanliness. Three people have strong opinions. The team has rederived this
argument three times in twelve months. A **90-minute architecture review** is
on the calendar for Thursday.

The naive instinct: hold the meeting. The CMD response: **cancel the meeting,**
write the matter, summon the canonical pair, ship one artifact.

This document is that artifact. The Thursday meeting did not happen.

---

## Step 0 — The three-question gate

CMD applies only if every answer is *yes*
([operational paradigm §0](02-operational-paradigm.md)).

1. **Boundary.** Two disciplines are present beneath the surface, and the team
   has been treating the matter as if only engineering were involved. The
   architecture diagram is an *engineering* artifact. The thing the diagram
   represents — *coupling, on-call burden, deploy lockstep* — is a **scientific**
   question (it is *measured*, not believed). And the thing the diagram is in
   service of — *what users experience when they get told a thing* — is a
   **product** question (it is *defined,* not derived). Three disciplines.
   Two seams. *Yes.*
2. **Loss.** Twelve months. Three rounds of rederivation. The same engineer-hours
   spent, twice already, with no durable artifact left behind. *Yes.*
3. **Sovereignty.** Engineering owns what a service *is* in the code. Science /
   measurement owns what its operational behavior actually *is.* Product owns
   what the service is *for.* None can simply overrule the others. *Yes.*

Three yeses. CMD applies. The Thursday meeting is cancelled.

---

## Step 1 — Capture: the source register

The manager opens his editor and writes the matter in his own register. Plain
prose, his own vocabulary, no smoothing, no aiming at an answer.

> "We have a notifications service inside the monolith. It handles email, push,
> and in-app — six concrete types with different retry, dedup, and ordering rules.
> Mark wants to extract it; says the abstraction is rotting from inside. Priya
> pushes back; says the monolith hides the actual cost — pulling it out means a
> new repo, a new on-call, a new deploy pipeline, all to chase a feeling.
>
> I don't actually know who's right. What I do know is that we've had this
> argument three times this year and each time it dissolves into 'let's revisit
> next quarter.' I'm not interested in revisiting again. I want to know what
> we're actually arguing about, and what would make either answer the right one.
> I have ninety minutes on Thursday that the whole team has blocked. I would
> rather give that ninety minutes back."

That paragraph is the **source register.** Under Principle I it is preserved
permanently, beside every translation that follows, and never deleted. Notice
what Capture has already accomplished, before any persona is summoned: a
question that lived only in the manager's head is, for the first time, a
written, versioned artifact the team can hold.

The matter is saved as `matter.md`. The chamber is opened. The COMPANION
foundation files and the Feynman + Jobs calibration cards are pasted in. The
matter follows.

---

## Step 2 — Route: naming the seams, choosing the minds

The Orchestrator names the boundary precisely. It is **not** *extract vs. don't
extract.* That framing is what has dissolved three times in twelve months —
because it suppresses two disciplinary registers the engineering frame cannot
reach on its own.

- **The SCIENCE ↔ ENGINEERING seam.** Mark says *the abstraction is rotting.*
  Priya says *the operational cost is hidden.* Neither side has produced a
  measurement. *Rot* and *cost* are scientific quantities; they have units, and
  the units are not in the room. The seam is unattended.
- **The PRODUCT ↔ ENGINEERING seam.** The team is debating the geometry of the
  code without anyone having said what the notifications service *is to a user.*
  Six notification types could be one product or six; the engineering decision
  is downstream of the product definition, and the product definition has not
  been written.

Two seams, two instruments:

- **Richard P. Feynman**, calibrated for *science ↔ engineering* — to refuse to
  let an unmeasured noun do the work of a verb.
- **Steven P. Jobs**, calibrated for *product ↔ engineering* — to refuse to let
  an unnamed thing be built.

The pre-filled calibration cards
([`feynman-calibration.md`](../templates/feynman-calibration.md),
[`jobs-calibration.md`](../templates/jobs-calibration.md)) are already in the
chamber. The Orchestrator speaks the incantation.

---

## Step 3 — Translation across the SCIENCE ↔ ENGINEERING seam

> *"Using this matter, summon Feynman."*

> **Feynman.** You're using a word — *service* — and the word is doing too much
> work. When Mark says the abstraction is rotting, what does he actually *mean?*
> Has anybody measured the coupling? Counted the cross-cutting reads? Looked at
> the deploy lockstep — how often does a change in one notification type force
> a redeploy that touches the others? Or is *rotting* the feeling he gets when
> he's editing the code, which is real but is not the same thing.
>
> And Priya — *operational cost.* What's the cost? Pages per quarter? Mean time
> to recover? Hours of on-call attention attributable to this code? The number
> is somewhere. If it isn't, that's the answer right there: nobody knows the
> operational cost of the current arrangement, so nobody can know the cost of
> the new one either. You're not arguing about a service. You're arguing about
> a feeling and a fear, both of which are honest, and neither of which is the
> real thing.
>
> So before any architectural verb gets used — *extract, decompose, factor* —
> *measure.* The coupling is somewhere on disk. The pager log is somewhere on
> disk. Count them. If you can't count them, you can't decide.

Feynman is doing what he did to NASA in 1986: he is refusing to let a system
question be argued in the absence of the measurement that would settle it. This
is the **science ↔ engineering** translation. The engineering team has been
speaking in *verbs* (extract, refactor, decompose); the scientific register
demands *nouns* (coupling, pages, lockstep) — *and* their units. The engineering
sentence cannot pass until the scientific noun is on the table.

---

## Step 4 — Translation across the PRODUCT ↔ ENGINEERING seam

> *"Now summon Jobs to join this conversation."*

> **Jobs.** Stop. Before any of that — *what is this service for?* In one
> sentence. Don't tell me what it does. Tell me what it *is.*
>
> If your sentence is *"it sends notifications,"* it isn't a service; it's a
> folder. If your sentence is *"it is the single source of truth for whether a
> user got told a thing,"* — that's a service. That's a thing with a job. Now
> your decision is easy: does the current code *own* that sentence? If yes,
> leave it. If no, extract — because the extraction isn't about coupling, it's
> about giving the sentence a home.
>
> And Feynman is right that you should measure. But measurement without focus is
> just numbers. The numbers will tell you the *cost* of either path. They will
> not tell you the *point* of either path. Get the sentence first. Then the
> measurement decides.
>
> While we're at it — six notification types? Are those six product surfaces, or
> are those six accidents of how the code grew? A user who got an email and a
> push notification and an in-app alert about the same payment did not
> experience three things. They experienced one thing, badly. The product
> question your team has not asked is: *what is the notification that a payment
> happened, to the person it happened to?* If the answer is one thing, you have
> one product. If you have one product, you may have one service, regardless of
> coupling.

Jobs is doing what he did at Apple from 1997 to 2010: he is refusing to let an
engineering decision be made in the absence of the product definition it serves.
This is the **product ↔ engineering** translation. The engineering team has been
speaking in *structure* (six types, monolith, service); the product register
demands the *user experience* the structure exists to deliver — and demands that
the structure derive from it, not the other way around.

---

## Step 5 — The collision

The personas engage each other directly. The collision is the symposium's gift —
neither persona could have reached it alone.

> **Feynman.** A sentence isn't a measurement. You can write a beautiful sentence
> about a service that has no business existing. Teams do this all the time. The
> sentence is a luxury; the measurement is the floor.
>
> **Jobs.** A measurement isn't a decision. You can count coupling all day and
> still not know whether the thing should be one service or ten. The number
> tells you the cost. The sentence tells you whether the cost is worth paying.
> You're trying to solve a focus problem with arithmetic, and arithmetic does
> not solve focus.
>
> **Feynman.** Then write the sentence and *then* count. But do not mistake
> the sentence for the work.
>
> **Jobs.** Agreed. The sentence is the gate. The count is the budget. Either
> alone is wrong. Sequence them, and the decision finishes itself.

What the collision produced — the load-bearing insight neither persona could
have reached alone:

> The question is not *extract or not.* The question is two sequential questions,
> each owned by a different discipline:
>
> *(1) Is there a product sentence?* — owned by the product register; until it
> is written, no engineering decision is well-formed.
>
> *(2) What does the coupling cost?* — owned by the scientific register; until
> it is measured, no engineering decision is well-bounded.
>
> The engineering decision lives downstream of both, and was never going to
> resolve while it sat upstream of them.

---

## Step 6 — Verify: the cost of the crossing

The Orchestrator restates the symposium in his own words, and the personas score
the restatement for fidelity (the receiving-discipline check,
[conceptual model §2](01-conceptual-model.md)).

> "Two gating questions, in order. First, *what is the notifications service to
> the user the notification is for, in one sentence?* If we cannot write the
> sentence, the answer is *don't extract; we don't know what we'd be
> extracting.* If we can write it, the second question is operational: *count
> the cross-context coupling, the deploy lockstep, and the on-call hours per
> quarter that are this code's fault.* If coupling is low and on-call cost is
> low, the extraction's value is small and we leave it. If coupling is high
> *and* the product sentence exists, extract."

**Feynman: 0.92.** Missing 0.08 — the measurement must include the team's
**on-call burden today,** not just structural coupling, because a service with
low coupling but high pager noise still benefits from being given its own
boundary (or, more often, from *not* being given one, because new services
start with new pager noise of their own).

**Jobs: 0.95.** Missing 0.05 — the sentence must be one **a non-engineer can
hear and agree with.** If it requires a system diagram to defend, it isn't the
sentence yet; it's a caption.

The restatement is revised to incorporate both. **Translation losses logged:
0.08 (Feynman), 0.05 (Jobs).** Total loss on the crossing: lower than any prior
round of this debate, by the only measure that matters — the artifact can be
checked against its sources.

---

## Step 7 — Decide: the Orchestrator, and only the Orchestrator

The personas translated. They did not decide. The decision is the manager's:

- **Decision.** **Defer the extraction question.** Replace it with two work
  items, in order:

  1. **The product sentence.** Mark and Priya, together, draft a one-sentence
     definition of what the notifications service *is* — a sentence a
     non-engineer (the product partner) can hear and agree with. *What is the
     notification a user gets when something happens to them, on this surface?*
     Not what it does — what it is. **Deadline: one week.**
  2. **The operational measurement.** Once the sentence exists — *or once they
     admit it does not* — count: cross-context coupling, deploy lockstep,
     on-call hours per quarter attributable to this code, attributable user
     complaints about over- or under-notification. **Deadline: two weeks.**

- **Decided by:** the engineering manager (human). No persona's name appears in
  this field.

- **Load-bearing caveat — do not sand off.** If the team cannot write the
  sentence, *that is the answer.* The extraction does not happen, and *"we'll
  figure it out later"* is not an acceptable variant of "no sentence." The
  **absence** of a product sentence is product information, not engineering
  information, and it points to a different decision than the one the team
  thought it was making.

- **Rationale.** Twelve months of unresolved debate is itself an artifact: it
  said the team had been arguing about the wrong question, in the wrong
  discipline. Both personas, independently, identified that the named question
  (*extract or not, in engineering*) was downstream of unasked questions
  (*what is this, in product;* *what does it cost, in science*). The decision
  is to ask those instead.

The Thursday architecture review is cancelled. In its place: two named work
items, two deadlines, and a 30-minute follow-up two weeks out — only if the
artifact still cannot decide. The manager has spent **twenty-five minutes** on
this, alone, at his desk.

---

## Step 8 — The Shadow

One contradiction will not resolve, and CMD forbids smoothing it
([principle V](../index.html)).

> Feynman holds that the measurement is the **floor** — you cannot decide what
> you cannot count. Jobs holds that the sentence is the **gate** — counting in
> the absence of focus is theater. The manager has sequenced them here (sentence
> first, then measurement), but in some future working the order will be wrong:
> the team will need to count first to discover what kind of thing they are
> even trying to name. The general rule does not exist. The two registers —
> science and product — genuinely disagree about which comes first, and the
> artifact records both.

Kept, not erased. A future artifact on a different boundary may sequence the
two the other way; the Shadow keeps that possibility honest, and keeps a future
Orchestrator from quoting *this* artifact as universal.

---

## What the crossing produced

**Before.** Three opinions, a 90-minute meeting on the calendar, twelve months
of unresolved debate. Probable output: a fourth round of unresolved debate,
scheduled for next quarter.

**After.** One versioned `.md` artifact. Two named work items with deadlines,
each owned by the discipline whose register holds the answer. A preserved Shadow
recording the contradiction the methodology declines to flatten. The source
register — the manager's own words, before any translation — preserved beside
every rendering. Provenance intact; decision auditable in week eight; the
brainstorm avoided.

Six engineers got their Thursday afternoon back. The decision is *better* than
the brainstorm would have produced, because the brainstorm would have
manufactured an engineering consensus that the underlying disciplines did not
actually have. CMD preserved the disciplinary disagreement and used it.

The Thursday meeting was the wrong instrument. It was an engineering ceremony
trying to do science's job and product's job at the same time. The artifact —
science register beside engineering register beside product register, with one
human deciding — is what the meeting was trying to be.

---

*Continue to [`docs/04-cmd-vs-agile.md`](04-cmd-vs-agile.md) — how this method
differs from Agile, and where Agile still wins.*
