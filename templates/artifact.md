---
layout: default
title: CMD Artifact Template
---

# CMD Artifact

*Copy this file for every unit of cross-boundary work. One artifact, one claim, one
boundary crossed. This is the medium of CMD — the meeting is the exception; this is the rule.*

---

```
PROVENANCE
  artifact id:        <short stable id, e.g. ART-014>
  title:              <one line — what this artifact carries>
  source discipline:  <science | engineering | product | ...>
  receiving discipline: <the discipline this is being translated FOR>
  translating persona:  <the calibrated persona placed at this boundary>
  orchestrator:       <the human who routed and will decide — never a persona>
  version:            <v1.0, v1.1, ... — artifacts are versioned>
  status:             <captured | translated | verified | shipped | shadow>
  created / updated:  <date>
```

---

## 1. Source register — *the original claim, in the source discipline's own words*

> **Mandatory. Never deleted. Never overwritten by translation.**
> This is the field that makes a translation checkable. Without it you have a rumor.

<State the claim exactly as the source discipline states it — its own vocabulary, its own
units, its own caveats. Do not simplify it here. Simplification belongs in §2.>

## 2. Translation — *the claim rendered into the receiving discipline's register*

> Produced by the translating persona named above. The persona translates; it does not
> decide. If this section contains an approval, a rejection, or a priority call, that is
> **decision leakage** — remove it.

<The claim, rendered so the receiving discipline can act on it. Preserve every load-bearing
caveat from §1; translation may change the language, never the load.>

## 3. Verification — *translation loss*

> The receiving discipline restates §2 in its own words; the source discipline scores the
> restatement for fidelity (0–1). Loss = 1 − fidelity.

- **Receiving discipline's restatement:** <…>
- **Fidelity score (0–1):** <…>  →  **Translation loss:** <1 − score>
- **What was lost or distorted, if anything:** <…>
- If loss is high: <re-translate | recalibrate the persona | escalate to The Exception>

## 4. Decision — *Orchestrator only*

> Only the human Orchestrator may fill this section. A persona's name must never appear
> here. The available decisions: **accept · revise · hold as Shadow · escalate.**

- **Decision:** <…>
- **Decided by (human):** <…>
- **Load-bearing caveats that must not be sanded off later:** <…>
- **Rationale:** <…>

## 5. Shadow — *preserved contradiction, if any*

> If two disciplines or two personas genuinely disagree, do not manufacture consensus.
> Record the disagreement here, with both registers intact, and let the Orchestrator carry
> it forward as a real open question.

<The unresolved tension, both sides in their own registers — or "none.">

## 6. History

| Version | Date | Change | By |
|---------|------|--------|-----|
| v1.0 | <date> | Created. | <…> |

---

*A CMD artifact is done when it is **shipped** or honestly recorded as a **Shadow** — never
when it is merely discussed. Velocity is counted here, in shipped artifacts.*
