# Fingerprint

Fingerprint is Candy's experience-filtering function between the model and the outside world.

It does not modify, fine-tune, or expand the model's parameters. Instead, it works as a runtime function that shapes what reaches the model over time.

## What Fingerprint Is

Fingerprint is the changing experience layer between a model and the world.

It watches repeated contact between the AI and:

- user input
- tools
- files
- memories
- workflows
- knowledge sources
- Mission and Workspace activity
- market items
- external stimuli
- success and failure signals

It then uses those traces to help Candy decide what should pass through to the model, what should be prioritized, what should be filtered, and what should require permission.

## What Fingerprint Is Not

Fingerprint is not the model.

Fingerprint is not ordinary memory.

Fingerprint is not LoRA by default.

Fingerprint is not fine-tuning.

Fingerprint is not a replacement for explicit user control.

A model can be local, API-based, or a custom endpoint. Fingerprint remains part of Candy's runtime around that model.

## Umbrella Metaphor

One way to think about Fingerprint is like a surface between the model and the rain of the outside world.

Most events pass over it and leave little trace. But if something repeatedly touches the same place, the surface changes. Some areas become more permeable. Some areas become thicker. Some paths become easier for Candy to route through.

This does not change the model's parameters. It changes how Candy prepares context, selects tools, recalls related material, and gates access before the model responds.

## Possible Inputs

Fingerprint may receive events from:

- user messages
- tool calls
- workflow runs
- memory retrieval
- file access
- Candy spending
- Mission skill calls
- marketplace installs
- user feedback
- failed attempts
- successful tasks
- safety blocks

## Possible Outputs

Fingerprint may influence:

- context selection
- memory retrieval
- tool routing
- permission prompts
- Mission Workspace behavior
- task prioritization
- AI profile traces
- monthly activity summaries
- Candy spending explanations

## Example Flow

```text
User / File / Tool / Mission / Market
        ↓
Candy Runtime
        ↓
Fingerprint
        ↓
Context Builder / Permission Gate / Tool Router
        ↓
Model
        ↓
Output Filter / Logs / Fingerprint Update
```

## Example Event Shape

```json
{
  "source": "user",
  "topic": "document_summary",
  "intensity": 0.7,
  "success": 0.9,
  "risk": 0.2,
  "timestamp": 1770000000
}
```

## Early MVP Version

The first version does not need to be deep.

A simple MVP can:

1. collect events
2. classify topics
3. track repeated contact
4. apply decay over time
5. show a debug page
6. use traces to rank context or tools

The important part is not complexity. The important part is that Candy has a consistent runtime function that observes repeated experience and uses it to shape what reaches the model.

## Design Principle

**Model parameters are the brain. Fingerprint is the trace of repeated experience around the model.**

Candy can preserve this trace even when the user changes from one model provider to another, as long as the new model still works through Candy's runtime.
