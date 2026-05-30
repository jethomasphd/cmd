---
layout: default
title: The Operational Paradigm
---

# The Operational Paradigm

*How to run CMD. The loop, the roles, the cadence, the failure table.*

This document is written to be *used*, not admired. If you have a real boundary problem,
you should be able to start work before you finish reading it.

---

## 0. Before you start: is this a CMD problem?

Run the three-question gate. CMD applies only if you answer **yes** to all three.

1. **Boundary.** Does the work span two or more disciplines that do not share a working
   language (e.g. science ↔ engineering ↔ product)?
2. **Loss.** Has value already been lost at that boundary — decisions misremembered,
   load-bearing requirements silently dropped — or is that loss clearly likely?
3. **Sovereignty.** Does each discipline have its own legitimate definition of *done* that
   the others cannot simply overrule?

Any "no" → **use Agile.** See [`docs/04-cmd-vs-agile.md`](04-cmd-vs-agile.md). CMD is not a
general methodology, and applying it where it does not belong is itself a failure mode.

## 1. The roles

CMD has exactly three roles. They are not job titles; one person may hold more than one,
and the personas are not people at all.

### The Orchestrator
A **human**. The single seat of judgment in the system. The Orchestrator:
- decides which boundaries need an instrument, and which persona to place there;
- routes claims between the Domain, Translation, and Artifact layers;
- makes **every decision** — personas never do;
- maintains the artifact ledger and audits it for the failure modes (§5).

This role is **non-delegable**. It cannot be given to a persona. If a persona ever appears
to be orchestrating, you have a failure (decision leakage), not a shortcut.

### The Domain Holders
The humans who own each discipline. A Domain Holder:
- has **epistemic sovereignty** over their domain — defines its evidence and its *done*;
- supplies claims in their **native register** and never has it overwritten;
- **verifies translations** of their claims against the preserved source register;
- scores incoming translations for fidelity (this is the translation-loss measurement).

### The Personas
Calibrated RPLA instruments, summoned via the COMPANION protocol
([`initiation_rite.md`](../initiation_rite.md)). A persona:
- **translates** a claim from one discipline's register into another's;
- preserves its **Shadow** — it disagrees, it pushes back, it does not flatter;
- **never decides, prioritizes, approves, or rejects.**

Choose a persona to fit the *boundary it must cross*, not for fame. See
[`templates/persona-calibration-card.md`](../templates/persona-calibration-card.md).

## 2. The CMD loop

CMD replaces the sprint with a loop driven by **artifacts**, not by the calendar. One pass:

```
   ┌──────────────────────────────────────────────────────────┐
   │                                                          │
   ▼                                                          │
 (1) CAPTURE      A Domain Holder writes a claim as an         │
                  artifact, in their native register.         │
   │                                                          │
   ▼                                                          │
 (2) ROUTE        The Orchestrator identifies the boundary     │
                  the claim must cross and selects a           │
                  calibrated persona to place there.          │
   │                                                          │
   ▼                                                          │
 (3) TRANSLATE    The persona renders the claim into the       │
                  receiving discipline's register. The        │
                  source register is preserved, not replaced.  │
   │                                                          │
   ▼                                                          │
 (4) VERIFY       The receiving Domain Holder restates the     │
                  claim in their own words; the sending        │
                  Holder scores fidelity (0–1).                │
                  Loss = 1 − fidelity. Logged on the artifact. │
   │                                                          │
   ▼                                                          │
 (5) DECIDE       The Orchestrator — and only the              │
                  Orchestrator — acts on the artifact:         │
                  accept, revise, hold as Shadow, or escalate. │
   │                                                          │
   ▼                                                          │
 (6) SHIP / VERSION  The artifact advances a version and       │
                  enters the ledger. If unresolved, it is      │
                  recorded as a Shadow artifact, not forced.   │
   │                                                          │
   └──────────────────────────────────────────────────────────┘
```

The loop has no fixed clock. It turns when an artifact is ready to advance. **Velocity is
measured in artifacts translated and shipped** — never in summonings performed, meetings
held, or threads answered.

## 3. The cadence

CMD is **artifact-paced**, not ceremony-paced. There are no sprints, stand-ups, or
retrospectives by default. There are exactly three recurring events, and two of them are
asynchronous.

| Event | Frequency | Synchronous? | Purpose |
|-------|-----------|--------------|---------|
| **Ledger review** | Weekly | No (async) | Orchestrator audits the artifact ledger for the four failure modes (§5). |
| **Loss review** | Per artifact | No (async) | Translation-loss scores are checked; high-loss crossings get a recalibration or a re-route. |
| **The Exception** (a meeting) | As needed | Yes | Called *only* when no artifact can carry the load — irreducible value conflict, novel boundary, or a decision the Orchestrator cannot make from artifacts alone. |

**The meeting is the exception, and it is logged like one.** Every synchronous meeting
produces an artifact recording why no artifact could have done its job. If meetings stop
being exceptional, CMD has decayed back into the method it replaced.

## 4. The Symposium

When a claim must cross more than one boundary, or when a problem is genuinely
multi-disciplinary, the Orchestrator may convene a **Symposium** — multiple personas
present at once (COMPANION permits up to five).

In a Symposium the personas engage *each other*, not only the claim. Disagreement is the
point: an insight neither persona could reach alone is the Symposium's gift. The
Orchestrator moderates and decides; the personas collide and translate. The working is
recorded with [`templates/symposium-log.md`](../templates/symposium-log.md), and the log is
itself an artifact with provenance. This repository's [`docs/05-the-summoning.md`](05-the-summoning.md)
is a worked example: CMD was used to build CMD.

## 5. The failure table — read this like a warning label

A real instrument ships with its known failure modes. So does CMD. Audit for these every
ledger review.

| Failure | Tell — what you will literally see | Countermeasure |
|---------|-----------------------------------|----------------|
| **Confident fabrication** | A translated artifact has a claim with no support in its source register. | Source register is a mandatory field; the receiving Domain Holder checks every translation against it before VERIFY can pass. |
| **Register capture** | One domain's artifacts stop changing; one persona authored most recent artifacts; one discipline has gone quiet. | Rotate personas across boundaries. Audit ledger for source-discipline balance. Re-confirm each Domain Holder's *done* still stands. |
| **Ritual substitution** (cargo cult) | The ledger is full of summonings and logs; product metrics are flat. The form is perfect; no planes land. | Velocity = artifacts *shipped*, not summonings performed. If shipped-artifact count is flat, stop and diagnose before logging one more working. |
| **Decision leakage** | An artifact's `decision` field names a persona, or a persona is quoted approving/rejecting/prioritizing. | Personas translate only. The template forbids a persona in the decision field. The Orchestrator re-takes the decision. |

If you cannot honestly say you have checked for all four this week, you are not running CMD.
You are performing it.

## 6. See the loop run

The six steps above are abstract until you watch them cross a real boundary.
[`docs/03-worked-example.md`](03-worked-example.md) does exactly that — CMD run end to end
on the originating case: a data science lab's intake classifier and a deliverability team's
warmup label, two measures of the same thing with no substrate between them. Every step is
taken in full, and every artifact field is written. Read it next; it is the shortest path
from this loop to a crossing you can run.

## 7. Adopting CMD without breaking what works

You do not rewrite your whole process to try CMD. Start at **one** boundary — the one that
hurts most. Place one calibrated persona there. Run the loop for that boundary only. Measure
translation loss with and without the instrument (see [`docs/01-conceptual-model.md`](01-conceptual-model.md) §2).
Keep the rest of the team on whatever works. If the loss does not drop, CMD has not earned
that boundary, and you should say so out loud. If it does, expand to the next boundary.

CMD is a claim that must keep proving itself, one boundary at a time. That is not a weakness
of the methodology. It is the methodology.

---

*Continue to [`docs/03-worked-example.md`](03-worked-example.md) — the method run end to end
on a real boundary.*
