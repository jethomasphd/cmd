---
layout: default
title: The Operational Paradigm
---

# The Operational Paradigm

*How to run CMD. The deployment, the loop, the roles, the cadence, the failure table.*

This document is written to be *used*, not admired. If you have a real boundary
problem, you should be able to start work before you finish reading it.

---

## 0. Before you start: is this a CMD problem?

Run the three-question gate. CMD applies only if you answer **yes** to all three.

1. **Boundary.** Does the work span two or more frames that do not share a working
   language? — disciplines (science ↔ engineering ↔ product), or registers inside one
   discipline (formalism ↔ practice, code ↔ product, spec ↔ deploy).
2. **Loss.** Has value already been lost at that boundary — decisions misremembered,
   load-bearing requirements silently dropped, the same argument rederived for the
   third time — or is that loss clearly likely?
3. **Sovereignty.** Does each frame have its own legitimate definition of *done* that
   the others cannot simply overrule?

Any "no" → **use Agile.** See [`docs/04-cmd-vs-agile.md`](04-cmd-vs-agile.md). CMD is
not a general methodology, and applying it where it does not belong is itself a failure
mode.

---

## 1. The deployment — what running CMD literally looks like

CMD has no installs. The methodology runs in a **chamber** — any LLM context window —
and produces **artifacts** — `.md` files you keep wherever you keep `.md` files (an
Obsidian vault, a Git repo, a `decisions/` folder, a personal wiki).

The full deployment, end to end:

```
   YOUR EDITOR                  THE CHAMBER (any LLM)              YOUR LEDGER
   (write the                   (paste COMPANION foundation        (commit the
    matter as .md)               + calibration cards, then          emitted artifact
        │                        the matter, then summon)               .md file)
        │                                  │                                ▲
        └─── paste ────────────────────────┤                                │
                                           │                                │
                                       symposium                            │
                                           │                                │
                                           └─── render artifact ────────────┘
                                                (release personas;
                                                 close chamber)
```

The kit is five files. You already have all of them in this repo:

| File | Where it goes | What it does |
|---|---|---|
| `enrichment_grimoire.json` | pasted into chamber, message 1 | the COMPANION calibration covenant |
| `initiation_rite.md` | pasted into chamber, message 2 | the summoning rite |
| `templates/feynman-calibration.md` | pasted into chamber, message 3 *(optional)* | pre-aims Feynman at formalism ↔ practice |
| `templates/jobs-calibration.md` | pasted into chamber, message 4 *(optional)* | pre-aims Jobs at focus ↔ scope |
| your `matter.md` | pasted into chamber, last | the boundary you need to cross |

For a copy-paste walkthrough: [`quickstart.md`](../quickstart.md).

---

## 2. The roles

CMD has exactly three roles. They are not job titles; one person may hold more than one
(usually does), and the personas are not people at all.

### The Orchestrator
A **human**. The single seat of judgment in the system. By default, you — running CMD
as a personal intellectual hub. The Orchestrator:

- decides which boundaries need an instrument, and which persona to place there;
- routes claims between the Domain, Translation, and Artifact layers;
- makes **every decision** — personas never do;
- maintains the artifact ledger and audits it for the failure modes (§6).

This role is **non-delegable.** It cannot be given to a persona. If a persona ever
appears to be orchestrating, you have a failure (*decision leakage*), not a shortcut.

### The Domain Holders
The humans who own each frame — and *you*, when you are crossing a boundary inside your
own head (the manager-as-engineer, the engineer-as-product). A Domain Holder:

- has **epistemic sovereignty** over their frame — defines its evidence and its *done*;
- supplies claims in their **native register** and never has it overwritten;
- **verifies translations** of their claims against the preserved source register;
- scores incoming translations for fidelity (this is the translation-loss measurement).

In solo working, the Orchestrator is also every Domain Holder, in writing. The
discipline still applies: write the source register *before* the translation, in your
own register, without aiming at an answer.

### The Personas
Calibrated RPLA instruments, summoned via the COMPANION protocol
([`initiation_rite.md`](../initiation_rite.md)). A persona:

- **translates** a claim from one frame's register into another's;
- preserves its **Shadow** — it disagrees, it pushes back, it does not flatter;
- **never decides, prioritizes, approves, or rejects.**

The default pair is **Feynman + Jobs**:
- [`templates/feynman-calibration.md`](../templates/feynman-calibration.md) — formalism ↔ practice
- [`templates/jobs-calibration.md`](../templates/jobs-calibration.md) — focus ↔ scope

Choose another persona to fit the *boundary it must cross*, not for fame. See
[`templates/persona-calibration-card.md`](../templates/persona-calibration-card.md).

---

## 3. The CMD loop

CMD replaces the sprint with a loop driven by **artifacts**, not by the calendar.
One pass:

```
   ┌──────────────────────────────────────────────────────────┐
   │                                                          │
   ▼                                                          │
 (1) CAPTURE      A Domain Holder writes a claim as a         │
                  matter.md, in their native register.        │
   │                                                          │
   ▼                                                          │
 (2) ROUTE        The Orchestrator names the boundary the     │
                  claim must cross and selects the            │
                  calibrated persona(s) to place there.       │
   │                                                          │
   ▼                                                          │
 (3) TRANSLATE    The persona renders the claim into the      │
                  receiving frame's register. The source      │
                  register is preserved, not replaced.        │
   │                                                          │
   ▼                                                          │
 (4) VERIFY       The receiving Domain Holder restates the    │
                  claim in their own words; the sending       │
                  Holder scores fidelity (0–1).               │
                  Loss = 1 − fidelity. Logged on the artifact.│
   │                                                          │
   ▼                                                          │
 (5) DECIDE       The Orchestrator — and only the             │
                  Orchestrator — acts on the artifact:        │
                  accept, revise, hold as Shadow, escalate.   │
   │                                                          │
   ▼                                                          │
 (6) SHIP / VERSION  The artifact advances a version and      │
                  enters the ledger. If unresolved, it is     │
                  recorded as a Shadow artifact, not forced.  │
   │                                                          │
   └──────────────────────────────────────────────────────────┘
```

The loop has no fixed clock. It turns when an artifact is ready to advance. **Velocity
is measured in artifacts translated and shipped** — never in summonings performed,
meetings held, or threads answered.

For the loop run end to end on a real engineering decision (Mark and Priya's
notifications-service debate, twelve months of brainstorm replaced by twenty-five
minutes at a laptop), see [`docs/03-worked-example.md`](03-worked-example.md).

---

## 4. The cadence

CMD is **artifact-paced**, not ceremony-paced. There are no sprints, stand-ups, or
retrospectives by default. There are exactly three recurring events, and two of them
are asynchronous.

| Event | Frequency | Synchronous? | Purpose |
|-------|-----------|--------------|---------|
| **Ledger review** | Weekly | No (async) | Orchestrator audits the artifact ledger for the four failure modes (§6). |
| **Loss review** | Per artifact | No (async) | Translation-loss scores are checked; high-loss crossings get a recalibration or a re-route. |
| **The Exception** (a meeting) | As needed | Yes | Called *only* when no artifact can carry the load — irreducible value conflict, novel boundary, a decision the Orchestrator cannot make from artifacts alone. |

**The meeting is the exception, and it is logged like one.** Every synchronous meeting
produces an artifact recording *why no artifact could have done its job.* If meetings
stop being exceptional, CMD has decayed back into the method it was written to replace.

A useful test: at the end of the week, count meetings held vs. artifacts shipped. If
meetings > artifacts, you are no longer running CMD. You are performing it.

---

## 5. The Symposium

When a claim must cross more than one boundary, or when a problem is genuinely
multi-frame, the Orchestrator may convene a **Symposium** — multiple personas present
at once (COMPANION permits up to five; in practice, two — Feynman and Jobs — handles
most engineering decisions).

In a Symposium the personas engage *each other*, not only the claim. Disagreement is
the point: an insight neither persona could reach alone is the Symposium's gift. The
Orchestrator moderates and decides; the personas collide and translate.

The default working is logged with [`templates/symposium-log.md`](../templates/symposium-log.md),
and the log is itself an artifact with provenance. This repository's
[`docs/05-the-summoning.md`](05-the-summoning.md) is a worked example: CMD was used
to build CMD, with Jobs and Feynman in symposium.

---

## 6. The failure table — read this like a warning label

A real instrument ships with its known failure modes. So does CMD. Audit for these
every ledger review.

| Failure | Tell — what you will literally see | Countermeasure |
|---------|-----------------------------------|----------------|
| **Confident fabrication** | A translated artifact has a claim with no support in its source register. | Source register is a mandatory field; the receiving Domain Holder checks every translation against it before VERIFY can pass. |
| **Register capture** | One frame's artifacts stop changing; one persona authored most recent artifacts; one register has gone quiet. | Rotate personas across boundaries. Audit the ledger for source-frame balance. Re-confirm each Domain Holder's *done* still stands. |
| **Ritual substitution** (cargo cult) | The ledger is full of symposiums and logs; product metrics are flat. The form is perfect; no planes land. | Velocity = artifacts *shipped*, not summonings performed. If shipped-artifact count is flat, stop and diagnose before logging one more working. |
| **Decision leakage** | An artifact's `decision` field names a persona, or a persona is quoted approving/rejecting/prioritizing. | Personas translate only. The template forbids a persona in the decision field. The Orchestrator re-takes the decision. |

If you cannot honestly say you have checked for all four this week, you are not running
CMD. You are performing it.

---

## 7. Adopting CMD without breaking what works

You do not rewrite your whole process to try CMD. Start at **one** boundary — the one
that hurts most, the argument that has been rederived three times. Place one
calibrated persona there (or the canonical pair, if it is an engineering decision).
Run the loop for that boundary only. Measure translation loss with and without the
instrument (see [`docs/01-conceptual-model.md`](01-conceptual-model.md) §2). Keep the
rest of the team on whatever works.

If the loss does not drop, CMD has not earned that boundary, and you should say so
out loud. If it does, expand to the next boundary.

CMD is a claim that must keep proving itself, one boundary at a time. That is not a
weakness of the methodology. It is the methodology.

---

## 8. The solo working — running CMD as a personal hub

CMD's default is single-orchestrator. One human, one artifact ledger, one chamber per
working. You can run an entire crossing in twenty-five minutes at your desk, with no
one else's calendar consulted, and walk away with one durable, versioned `.md` file
that carries the decision, its provenance, and the contradictions you declined to
flatten.

This is the deployment that makes CMD a **countertechnology** to the information
flood. The flood happens because every channel is shared, ambient, and infinite —
Slack, email, the meeting that begets the meeting. CMD's chamber is closed, the
working is finite, and the output is one file. You leave the chamber with *less*
than you brought in. What you leave with is durable.

The team version is the same operation, run by each member in their own chamber,
pooling the artifacts that need to travel. There is no team install. There is no
shared CMD server. The artifact is portable; the methodology is private practice;
the protocol is the same in every chamber.

---

*Continue to [`docs/03-worked-example.md`](03-worked-example.md) — the loop run end
to end on a real engineering decision, with Jobs and Feynman in symposium.*
