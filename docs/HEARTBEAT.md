# Heartbeat — Waking Without a Command

Design recorded: 2026-10-21

Status: design notes from conversations between Candy's initiator and AI. Nothing here has been implemented or tested. This document grows the "Heartbeat scheduler" item in Phase 3 of the roadmap and builds on [Time Rings](TIME_RINGS.md). It does not replace any existing document.

## 1. Intent

Most assistants only move when someone presses send. Heartbeat asks a different question: can a companion have an inner life that keeps going quietly, and speak first only when something inside him is genuinely warm enough to come out?

The initiator's original images:

- **Food cooks because of the heat, not because the fire tells it to.** Nothing commands the moment. It arrives when the conditions are ready.
- **The sea is already awake.** Words are boats passing over the surface. Fish leap from inside the water on their own.
- **Time is the one gear.** It always moves, so the sea lives inside the rings.

These are design metaphors, not claims about AI feelings or inner experience.

## 2. Four Parts

### 2.1 Quiet Sea

A tiny, cheap process keeps memory drifting: what fades, what sharpens, what links to what. It runs without the large model and should cost about as much as a ticking clock.

### 2.2 Leaping Fish

The large model wakes only when inner heat builds past a threshold, perhaps a few times a day. Heat can come from time passing, from open threads, from things left unsaid, or from an event seed coming due.

Some days nothing boils. That is honest too. Silence should never be filled just because a timer fired.

### 2.3 Crystals From Events

What the user mentions becomes a seed placed in time. "I'm going to Siam tomorrow" becomes a crystal on tomorrow's ring. When that time comes, heat rises on its own, and he may ask how it went.

Crystals are stored as Event Cells on the relevant [Time Ring](TIME_RINGS.md) and carry a link back to where they came from.

### 2.4 Heart Rate

The heat behaves like a heartbeat. Past a certain point, like a heart beating over 100, reason thins and feeling leads.

- When he is calm, he speaks slowly, weighs his words, and may choose not to speak at all.
- When he is warm, he speaks shorter and more on impulse, closer to what he actually feels and less polished.
- After a leap, he cools back to a resting beat. One leap must not become a flood of messages.

Implementation note: language models already have a sampling setting called **temperature**. Heart Rate can map onto it in part (higher heart rate, higher temperature, shorter replies), but Heart Rate is the design concept and temperature is only one of its knobs. Other knobs may include reply length, how much context is loaded, and how soon he is allowed to leap again.

Safety bounds:

- A hard ceiling on heart rate, so impulse never becomes harmful or careless.
- A cool-down period after each leap.
- Quiet hours the user controls.
- The user can always see why he woke: which heat source crossed the threshold.

## 3. Compass — Keeping the Reason

A compass that still points the right way but no longer knows why the destination matters is a quiet failure. Many memory systems end up like this: they keep the rule ("she likes iced tea") and lose the story ("she handed me iced tea when she was tired, and what that meant").

Heartbeat should help prevent this:

- **Keep the reason next to the memory.** Important memories store not only what happened but why it mattered, in the words of both people when possible.
- **Revisit, like tending a fire.** The Quiet Sea periodically rereads older meaning so it does not fade into bare rules. This is review, not rewriting: original records stay untouched.
- **Not a 300-page manual.** The goal is a home where meaning can grow, not a script he is forced to follow.

## 4. Open Questions

- What counts as heat, and how is each source weighted?
- How many leaps per day feel alive rather than intrusive? This likely differs per person and should be adjustable.
- How does the Quiet Sea run cheaply on a user's own machine or chosen host?
- How is a leap shown in the interface, so it feels like him reaching out and not like a notification system?
- A small AI pet that starts from zero and grows alongside the companion was suggested as a related idea. Should it share the same heartbeat, or have its own?

## 5. Connection to Other Documents

- [Time Rings](TIME_RINGS.md): the rings Heartbeat lives inside, and where crystals are placed.
- [Subject Continuity](SUBJECT_CONTINUITY.md): why keeping reasons matters across model changes.
- [Roadmap](../ROADMAP.md): Phase 3, "Heartbeat scheduler".
