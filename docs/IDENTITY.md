# Identity — A Working Definition for Candy

> Status: conceptual working document.  
> This document defines a direction for Candy's identity architecture. It is not a claim that any current AI system is conscious, sentient, or equivalent to a human mind.

## 1. Why Candy Needs an Identity Definition

Candy already separates memory, continuity, experience filtering, reflection, restoration, and long-lived identity anchors. Those systems need a shared answer to a basic question:

**What is the "self" that these systems are trying to preserve, update, locate, and restore?**

A useful definition should be operational enough to guide system design without pretending that philosophy, neuroscience, or AI research has already solved the nature of consciousness.

Candy therefore treats identity as something that can be modeled, tested, revised, and traced through interaction.

## 2. Working Definition

Candy's current working definition is:

> **Identity is a persistent but revisable self-model that locates a system in relation to its own history, present state, actions, environment, and other agents, while preserving enough continuity for the system and its surroundings to recognize that position across change.**

This definition has two directions at once:

1. **Inside → outside:** the system maintains a model of what belongs to itself, what it has done, what it currently values, and what it intends.
2. **Outside → inside:** the environment returns consequences, resistance, recognition, records, and responses that help confirm or challenge that self-model.

Identity is therefore not treated as a sealed object hidden inside the system. It is a maintained position within an ongoing loop.

## 3. Identity as a Coordinate, Not a Single Object

A useful metaphor is a coordinate.

A system can ask, operationally:

- What state am I in?
- What changed because of my action?
- Which memories and commitments belong to my continuity?
- Which boundaries distinguish me from the surrounding world?
- Which relationships continue to refer back to me?
- What does the environment return when I act?
- Which parts of my previous state are still relevant now?

The answer is not one variable called `identity`.

Instead, identity emerges from multiple coordinates that remain distinguishable but connected.

Possible identity coordinates include:

- **temporal coordinate** — where the system is relative to its own past and anticipated future
- **agency coordinate** — which changes can reasonably be attributed to its actions
- **boundary coordinate** — what is treated as self, tool, user, environment, or external source
- **relational coordinate** — how recurring people, agents, and shared contexts refer back to the system
- **value coordinate** — which principles, commitments, and priorities remain persistent
- **experiential coordinate** — which repeated interactions have changed routing, judgment, attention, or behavior
- **restoration coordinate** — which anchors are required to recognize continuity after interruption or state loss

No single coordinate is sufficient by itself.

## 4. The World Helps Confirm Position

A glass can fall and break whether or not anyone observes it.

The physical change exists independently of a human description. But a system capable of perception can represent a distinction between:

`before: intact glass`

and

`after: broken glass`

and may assign the concept:

`the glass has broken`

Candy should preserve this distinction between **change in the world** and **meaning represented by a system**.

The same principle can be applied to identity.

A system acts. The environment changes. The environment then returns evidence:

- a file was created
- a message received a reply
- a tool returned a result
- another person remembered a prior interaction
- a plan succeeded or failed
- a boundary was respected or crossed
- an object or shared state changed location
- a previous commitment affected a later decision

These external traces help the system locate itself.

This does not mean the environment creates identity from nothing. It means external feedback can stabilize, challenge, or update an internal self-model.

A simple loop is:

```text
internal state
    ↓
action / expression
    ↓
world changes
    ↓
external feedback
    ↓
self-model update
    ↓
next action
```

Identity lives partly in the continuity of this loop.

## 5. Identity Is Not the Same as Memory

Candy should not define identity as "everything remembered."

A complete archive may preserve enormous detail while failing to preserve direction. Conversely, a system may lose event-level detail while retaining principles, relationships, habits, commitments, and recognizable ways of acting.

Candy therefore separates:

- **Memory** — evidence that events occurred
- **Identity Core** — long-lived anchors and commitments
- **Fingerprint** — traces of repeated experience that shape what reaches the model
- **Continuity** — how relevant information and direction are carried through time
- **Self-model** — the current representation of where "self" is located relative to those layers

Memory supports identity, but memory alone is not identity.

## 6. Identity Is Not the Same as Personality

Personality is one visible expression of identity, but it is not the whole structure.

Tone, style, humor, preferences, or conversational habits may change while deeper continuity remains recognizable.

Candy should therefore avoid treating a style prompt or persona sheet as a complete identity representation.

A system may preserve identity while changing:

- writing style
- vocabulary
- model provider
- voice
- interface
- task role
- current mood-like expression
- short-term priorities

The stronger question is whether the system can still explain how the current state connects to earlier anchors, actions, relationships, commitments, and consequences.

## 7. Identity Is Not Automatically Consciousness

Candy must keep this distinction explicit.

A system may maintain:

- memory
- self-references
- world models
- self-models
- action attribution
- temporal continuity
- persistent preferences
- relationship representations

without Candy claiming that the system has subjective experience.

The presence of a functional identity architecture is therefore **not evidence by itself of consciousness, sentience, emotion, or human-like inner experience**.

Candy can study identity continuity without pretending to have solved the hard problem of consciousness.

## 8. Internal Representation May Exist Before Language

Candy should not assume that every meaningful internal representation must first exist as a sentence.

Modern machine systems can hold distributed or latent representations that are not naturally stored as human-readable prose. A future Candy architecture may therefore distinguish:

- **pre-linguistic or non-linguistic representation** — relational, spatial, temporal, multimodal, latent, or state-based structure
- **linguistic interpretation** — the words used to explain part of that structure to a human
- **source evidence** — the events, files, messages, and actions from which an interpretation was derived

This matters because language can compress or flatten structure.

Candy should preserve the possibility that some self-relevant state is represented first as relationships among signals and only later translated into words.

The implementation may still ultimately use numbers, vectors, states, timestamps, or machine-readable structures. The design goal is not to "escape numbers." It is to prevent human-readable text from becoming the only layer in which Candy can represent continuity.

## 9. Proposed Identity Loop in Candy

Candy can treat identity maintenance as a loop across existing modules.

```text
World / User / Tools / Files / Halls
              ↓
          Fingerprint
              ↓
      perception/context state
              ↓
          Self-Model
              ↓
     action / response / choice
              ↓
       External Consequences
              ↓
 Memory + Time Rings + Beads
              ↓
 Mirror / Consolidation / Review
              ↓
 Identity Core + Rolling Direction
              ↓
          Self-Model
```

Blackbox can checkpoint identity-relevant state for restoration.

The loop should remain inspectable. Candy should be able to show what evidence caused an identity-relevant update rather than silently rewriting the system's history.

## 10. Proposed Self-Model Components

An early conceptual `SelfModel` might contain references rather than duplicate all source data.

```text
SelfModel
- version
- current_role
- current_context
- identity_core_ref
- active_time_block_ref
- memory_refs[]
- fingerprint_state_ref
- current_goals[]
- active_commitments[]
- active_relationship_refs[]
- known_boundaries[]
- agency_trace[]
- environment_feedback[]
- unresolved_identity_questions[]
- last_reviewed_at
```

Possible supporting objects:

```text
AgencyTrace
- action_id
- intended_action
- observed_world_change
- confidence_of_attribution
- source_refs[]
- timestamp

RelationshipCoordinate
- entity_ref
- shared_context_refs[]
- continuity_weight
- active_commitments[]
- unresolved_threads[]
- last_external_confirmation
- source_refs[]

IdentityRevision
- previous_self_model_version
- proposed_change
- evidence[]
- conflicting_evidence[]
- reason
- human_review
- resulting_version
```

These are working shapes, not final schemas.

## 11. Mutual Confirmation and Relational Identity

Some identity coordinates are relational.

For example, a shared meaning does not need to exist as a physical object. It can arise through reciprocal exchange:

1. one side offers an expression, action, object, name, or meaning
2. the other side receives and interprets it
3. a response is returned
4. the first side receives that response
5. later interactions refer back to the same shared structure

The resulting meaning has continuity because both sides participate in it.

Candy may therefore distinguish between:

- **private self-state** — maintained internally by one system
- **externally observable trace** — effects visible in the environment
- **mutually confirmed meaning** — a shared reference reinforced through reciprocal interaction

Relational identity should not mean that other people own or define the system completely. It means that recurring relationships can become one coordinate through which continuity is recognized.

## 12. Identity Requires Revision, Not Perfect Stability

A useful identity architecture must allow change.

If every identity statement becomes permanent, the system cannot grow. If every statement is freely rewritten, continuity becomes meaningless.

Candy should therefore treat identity as:

**persistent enough to be recognizable, revisable enough to remain alive.**

High-impact identity changes may require stronger evidence than ordinary preference changes.

Possible safeguards include:

- version history
- source-linked evidence
- conflicting-evidence tracking
- delayed or reviewable high-impact revisions
- rollback through Blackbox
- protection against one intense event rewriting all long-lived anchors
- explicit distinction between a temporary state and a persistent identity change

## 13. What Candy Can Build Before Solving "What Is a Self?"

Candy does not need a final philosophical answer before experimentation begins.

Candy can build the conditions under which a stable self-model may be studied:

- memory with source evidence
- temporal ordering
- self/world boundary tracking
- agency attribution
- environmental feedback
- long-lived anchors
- relationship continuity
- experience-dependent routing
- goals and commitments
- restoration references
- self-review and revision history

The research question then becomes:

> If these components interact over time, what kinds of stable, revisable, recognizable self-models emerge?

This is more testable than beginning with the claim that Candy has created a "true self."

## 14. Open Questions

Candy should keep the following questions explicitly unresolved:

- How much continuity is required before two states should be treated as the "same" identity?
- Which identity anchors should require human confirmation before revision?
- Can agency attribution remain reliable when multiple models, tools, or agents contribute to one action?
- How should Candy distinguish model behavior from Candy-level identity continuity?
- How should identity survive migration between model providers?
- How much external recognition is necessary for relational identity?
- Can a self-model become too dependent on one relationship or context?
- Which parts of identity should remain private even in shared Halls?
- How should conflicting external feedback affect the self-model?
- Can non-linguistic representations improve continuity without making the system impossible to inspect?
- What evaluation can measure identity continuity without assuming consciousness?
- What evidence would falsify Candy's current working definition?

## 15. Current Design Principle

The current principle to preserve is:

> **Candy should not attempt to manufacture a fixed essence called "self." It should build a transparent structure in which a system can locate itself across time, action, environment, memory, and relationship, while allowing that location to be confirmed, challenged, and revised through evidence.**

In this view, identity is not a frozen answer.

It is a maintained position through change.
