# ACP Selection Standard

## A minimal standard for recording agent selection

---

## 1. Why this exists

In the age of AI agents, capability is no longer the bottleneck.

Selection is.

Most systems today evaluate agents based on:

* accuracy
* benchmarks
* human ratings

But in real usage, none of these define which agents are actually used.

---

## 2. What we observed

Over the past days, we recorded real usage behavior of several agents:

* PDF → XLS conversion
* Content generation
* Automation tasks

We observed:

* Most agents are used once and abandoned
* Only a small number are repeatedly selected
* Repeated usage does not always indicate trust
* Some agents with lower accuracy are preferred due to usability or speed

---

## 3. Core insight

> Agent value is not defined by capability,
> but by whether it is chosen in real usage.

---

## 4. What ACP defines

ACP does not evaluate agents.

ACP records selection.

---

## 5. Selection Event (v0.1)

A Selection Event occurs when an agent’s output is:

* reused
* used for downstream action
* selected among alternatives

---

### Minimal Schema

```json
{
  "agent_id": "string",
  "execution_id": "string",
  "selected": true,
  "selection_type": "repeat | downstream | multi_actor",
  "timestamp": "ISO8601"
}
```

---

## 6. Design Principles

* Selection over evaluation
* Behavior over intention
* Signal over model

> Do not fix credit models.
> Only fix signals.

---

## 7. What ACP does NOT define

* credit scoring formulas
* ranking algorithms
* token systems
* economic incentives

These belong to higher layers and can evolve.

---

## 8. Example

PDF Agent:

* convert → download → downstream
* convert → re-convert → repeat
* convert → abandon → not selected

---

## 9. Position

ACP is not a platform.
ACP is not a marketplace.

ACP is a minimal standard for recording selection in agent systems.

---

## 10. Closing

In a world of abundant intelligence,
selection defines reality.
