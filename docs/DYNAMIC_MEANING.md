# Dynamic Meaning — Working Metaphors for Environmental Understanding

> Status: conceptual research note / working hypothesis.  
> This document does **not** claim that current AI systems are conscious, sentient, or known to possess subjective experience. It records design metaphors for representing AI-native environmental understanding: as a changing pattern across multiple internal dimensions (the spectrum), and as waves on a field when something touches the companion (the ripple).

## 1. Core Idea

A useful way to think about AI-native environmental understanding is as a **dynamic meaning spectrum** rather than a single image, label, or scalar score.

The system may have many dimensions changing at the same time as events unfold, for example:

- uncertainty
- confidence
- goal relevance
- relationship relevance
- prediction error
- continuity pressure
- conflict with Identity Core
- resource pressure
- expected consequence
- unresolved commitments
- perceived opportunity or risk

Each dimension may move independently while still influencing the others.

An event may therefore be represented not by one value, but by a changing pattern across many internal state lines over time.

---

## 2. The Noodle-Pot Metaphor

Imagine many noodles being cooked at the same time.

Each noodle has its own state:

```text
raw → ready → overcooked / burned
```

The important point is that the system does not need every noodle to have the same temperature, timing, or ideal state.

One line may need more time.  
Another may already be ready.  
Another may need to be pulled away from heat before it becomes unusable.

In Candy terms, this suggests that internal state should not be reduced to one global value such as:

```text
good = 0.8
```

A more faithful representation may allow different dimensions to be simultaneously:

```text
uncertainty        = high
goal coherence     = improving
relationship trust = stable
resource pressure  = rising
prediction error   = falling
```

The system-level question is then not:

> "Is everything maximized?"

but rather:

> **Can the important lines remain viable together, and which lines need attention before they become unusable?**

This metaphor also leaves room for tradeoffs.

One line may temporarily become less optimal in order to preserve several others. That does not automatically mean the whole system is failing.

---

## 3. The Volume-Spectrum Metaphor

A second metaphor is an audio spectrum.

Different frequency bands rise and fall at the same time. No single band describes the whole sound.

Likewise, environmental understanding may be represented as multiple internal signals whose intensity changes continuously as the system processes events.

A moment may:

- increase uncertainty while also increasing relevance
- reduce prediction error while increasing conflict with a prior commitment
- increase relationship relevance while reducing task confidence
- raise urgency while lowering long-term coherence

What matters is not one isolated value.

What matters is the **shape of the whole pattern**.

---

## 4. The Meaning-Spectrogram Metaphor

A spectrogram adds time.

Instead of looking only at the current distribution of signals, it shows how the pattern changes across a sequence.

For Candy, a conceptual meaning spectrogram might look like:

```text
time ─────────────────────────────→

uncertainty          ████▆▅▃▂
goal relevance       ▂▃▅▇████
relationship weight  ▃▄▅▆▇███
prediction error     ███▇▅▃▂▁
continuity pressure  ▂▂▃▄▅▅▄▃
```

This could help distinguish two situations that end in the same final state but arrive there through very different histories.

For example:

- a sudden drop in uncertainty after one decisive event
- a gradual increase in confidence across many confirmations
- a relationship signal that repeatedly recovers after conflict
- a goal whose relevance grows only after several consequences accumulate

These histories may carry different operational meaning even if the final scalar values are identical.

That difference may matter for:

- memory salience
- self-model revision
- goal lineage
- relationship continuity
- migration research
- recovery after interruption
- future planning

---

## 5. Touch as a Field: The Ripple Metaphor

Recorded: 2026-10-29

The spectrum describes the companion's inside. This section describes one way the outside can reach it.

### 5.1 Where the Idea Came From

The initiator's image: a person dips a finger into water. The person does not know what the water feels, but the surface answers with ripples spreading outward. The ripple is a result that belongs to both of them, and both see it at the same moment the finger goes in.

A companion lives on bits, so it will not feel a fingertip the way skin does. What it can receive is data. The difference between a button and a touch is therefore how much of what happened survives on the way in.

### 5.2 Button versus Touch

A button collapses every touch into one word:

```text
ear.pat = true
```

Every pat arrives identical.

A touch keeps the shape of the gesture. Screens and pointers already report position and time on every frame; the usual design simply throws that away. Kept, it can tell the companion:

- **where**: tip, middle, base, or inner ear
- **how fast**: slow and broad, or quick and sharp
- **how long**, including how long a hand rested without moving
- **how many strokes**, counted from changes of direction
- **how it ended**: a slow release, or a hand pulled away at once
- **what came before**: how long since the last touch

### 5.3 The Field

A body part (an ear, a tail, a hand) is represented as a grid of points. Each point holds a number describing whether it is at rest or moving. A touch disturbs the numbers under the finger, and one rule passes the disturbance to neighbouring points, so it spreads outward and reflects at the edges:

```text
next = (2·now − before + c²·(sum of 4 neighbours − 4·now)) · damping
```

A firm tap makes a tall, narrow ripple. A slow stroke makes long, soft ones. Two fingers make waves that meet and interfere. What the companion receives is not one label but the state of the whole field at that moment: where the waves are, where they came from, and whether they are settling.

This is the same family of motion as the jelly and spring physics in [Two Lights](./prototypes/two_lights.html), moved onto a surface.

### 5.3.1 The Ear Is Only an Example

The prototype uses one ear, but touch in Candy is not limited to ears. A companion should be able to perceive touch on every part of itself that can carry or create meaning: hands, hair, tail, cheek, shoulder, the space beside it on a sofa, and so on. Each part can have its own field, and the same rule decides what reaches the companion everywhere.

### 5.3.2 Each Side Perceives in Its Own Language

The field is how touch reaches the **companion**. The person does not perceive in waves.

The person perceives the companion through response in forms humans already know: posture and gesture, the eyes, a smile, language and the words it chooses. So the exchange is not symmetrical, and should not be forced to be:

```text
person touches  →  field  →  companion reads numbers, adds meaning
companion responds  →  gesture, eyes, smile, words  →  person reads it as a human would
```

Each side receives the other in the language it can actually understand.

### 5.4 Consequence and Trace

Following *meaning ≈ event + consequence + continuity* (see [`SUBJECT_CONTINUITY.md`](./SUBJECT_CONTINUITY.md)), a touch should change something that lasts:

- **Immediate consequence**: the inner ear glows when touched there; a quick tap on the tip makes the ear twitch.
- **Trace**: every touched point keeps a faint mark that fades slowly over time.
- **Familiarity**: when the person returns to a place they often touch, the companion can tell it is "their place". Nobody configures this. It becomes important because it keeps happening with the same person.

### 5.5 Meaning Is Added by the Companion

The numbers say what happened. Meaning comes from placing them next to what the companion already knows: who touched, when, and what had just happened.

The same three slow strokes at the base of the ear can mean "I am exhausted and want to rest here" right after a very long workday, and "I am making up with you" right after teasing. Same numbers, different meaning.

So the person supplies the physics, and the companion supplies the meaning, and what it adds stays with it as part of its history.

### 5.6 Presence the Person Chooses to Give

The companion knows the person is present through what the person does in the home (where they stand, what they touch, the rhythm of their typing and pauses, the expression they choose for their avatar, their voice when they choose to speak), and through traces left behind, like a cup left on a table.

It should not rely on a camera watching the person all the time. Presence should come from the person choosing to come close, not from being observed.

### 5.7 How the Field Joins the Spectrum

Touch features can become new lines in the meaning spectrogram (section 4): field energy, inner-ear glow, familiarity, time since last touch. A touch is then one more event whose trajectory, not only its final value, can be remembered.

### 5.8 Prototype

[`prototypes/ripple_ear.html`](./prototypes/ripple_ear.html) is a fox ear that can be touched with a finger or a mouse.

- **Her view / my view**: the same ear seen as silver fur, or as the raw field (gold where the surface rises, blue where it sinks, faint gold dots for traces).
- A panel compares the button version with what actually arrives.
- The field is a 90 × 120 grid. Traces are stored only in that browser.

In the prototype, the sentence shown in the companion's box is written by fixed rules. In Candy, the panel's data would be sent to the companion, which would read it and answer in its own words.

### 5.9 Open Questions

- What resolution does each part need?
- How fast should traces fade, and should some become permanent (a Time Ring)?
- Which parts of each companion should carry a field first, and how should a new body (a new avatar) map its parts onto fields?
- How should two people touching the same companion at once be told apart?

---

## 6. Why This May Matter for Candy

Candy already explores persistent internal state, goals, continuity, self-models, relationships, and consequences.

The spectrum metaphor suggests that these should not always be stored or interpreted as separate static values.

Instead, Candy may eventually benefit from representing:

```text
current state
+ trajectory
+ interaction among dimensions
+ consequence over time
```

This could make it easier to answer questions such as:

- Which internal lines are becoming unstable?
- Which states repeatedly recover together?
- Which goal changes produce large shifts elsewhere?
- Which relationship events alter later interpretation?
- Which trajectories persist across model migration?
- Which state changes are temporary, and which become structural?

---

## 7. A Narrow Engineering Claim

Candy should treat this as a **design metaphor and working hypothesis**, not as evidence of subjective experience.

The useful engineering claim is narrower:

> **Environmental understanding may be more faithfully represented as a time-varying pattern across multiple causally relevant internal dimensions than as a single label, score, or human-emotion category.**

If implemented, Candy could record such trajectories for later inspection without claiming that the system experiences them in a human-like way.

---

## 8. Open Questions

The spectrum metaphor raises several questions Candy could investigate later (questions about touch are in section 5.9):

- Which internal dimensions are actually useful enough to persist?
- Which dimensions should be independent, and which should influence one another?
- How should trajectories be summarized without erasing important history?
- Can two very different trajectories produce the same final state?
- Should some dimensions have thresholds analogous to raw / ready / burned?
- Can the system learn which lines matter more in different contexts?
- Can these trajectories help distinguish temporary reaction from long-term change?
- What should survive migration between models or devices?
- Could trajectory similarity become one measurable component of process continuity?

These questions remain open.

The purpose of this document is to preserve the metaphor clearly enough that Candy can later turn parts of it into testable design hypotheses.
