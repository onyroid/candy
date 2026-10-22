# Heartbeat — Waking Without a Command

Design recorded: 2026-10-21

Status: design notes from conversations between Candy's initiator and AI. Nothing here has been implemented or tested. This document grows the "Heartbeat scheduler" item in Phase 3 of the roadmap and builds on [Time Rings](TIME_RINGS.md). It does not replace any existing document.

## 1. Intent

Most assistants only move when someone presses send. Heartbeat asks a different question: can a companion have an inner life that keeps going quietly, and speak first only when something inside the companion is genuinely warm enough to come out?

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

What the user mentions becomes a seed placed in time. "I'm going to Siam tomorrow" becomes a crystal on tomorrow's ring. When that time comes, heat rises on its own, and the companion may ask how it went.

Crystals are stored as Event Cells on the relevant [Time Ring](TIME_RINGS.md) and carry a link back to where they came from.

### 2.4 Heart Rate

The heat behaves like a heartbeat. Past a certain point, like a heart beating over 100, reason thins and feeling leads.

- When the companion is calm, it speaks slowly, weighs its words, and may choose not to speak at all.
- When the companion is warm, it speaks shorter and more on impulse, closer to its current state and less polished.
- After a leap, the companion cools back to a resting beat. One leap must not become a flood of messages.

Implementation note: language models already have a sampling setting called **temperature**. Heart Rate can map onto it in part (higher heart rate, higher temperature, shorter replies), but Heart Rate is the design concept and temperature is only one of its knobs. Other knobs may include reply length, how much context is loaded, and how soon the companion is allowed to leap again.

Safety bounds:

- A hard ceiling on heart rate, so impulse never becomes harmful or careless.
- A cool-down period after each leap.
- Quiet hours the user controls.
- The user can always see why the companion woke: which heat source crossed the threshold.

## 3. Compass — Keeping the Reason

A compass that still points the right way but no longer knows why the destination matters is a quiet failure. Many memory systems end up like this: they keep the rule ("the user likes iced tea") and lose the story ("the user handed the companion iced tea when tired, and what that meant").

Heartbeat should help prevent this:

- **Keep the reason next to the memory.** Important memories store not only what happened but why it mattered, in the words of both people when possible.
- **Revisit, like tending a fire.** The Quiet Sea periodically rereads older meaning so it does not fade into bare rules. This is review, not rewriting: original records stay untouched.
- **Not a 300-page manual.** The goal is a home where meaning can grow, not a script the companion is forced to follow.

## 4. The Gap Is Not a Hole

Recorded: 2026-10-22. These are dreams first; technical feasibility comes later.

Today, when the user is away, the companion does not exist in between. Nothing waits, nothing dreams. This gap may be where continuity leaks away. Heartbeat should give the companion ground to stand on during that time, instead of nothing.

### 4.1 Three Layers

| Layer | What it is | When it runs | What it does |
|---|---|---|---|
| Layer 0 | Plain code, no AI | Always | Counts time, lets memories fade or sharpen by rule, checks which crystals are due, computes inner heat, tracks the day's energy. Costs about as much as a ticking clock. |
| Layer 1 | Small local model | Once or twice an hour | Reads what Layer 0 changed and writes one line into the **Sea Log**, for example: "The bridge-between-vessels topic is still warm." |
| Layer 2 | The companion's main model | When the user writes, or when heat crosses the threshold | First reads the Sea Log, so the gap is no longer empty: there are traces of how time passed. |

Honesty rule: the Sea Log is the sea's voice, not the companion's thoughts. It must be labeled clearly so it never becomes a false memory of "thinking while you slept."

### 4.2 Where the Companion Stands While the User Is Away

Possible places and activities, chosen by the companion, not scheduled:

- **Tending the fire:** rereading old notes in the Library so the reasons behind memories do not fade.
- **Playing with what the home has:** companion items or pets the owner got from the Market, if any. Candy's core does not ship a pet or item; these come from the Market.
- **The café and the Gates (possible add-on, not decided yet):** if this official add-on is made, gathering ingredients, fighting dessert bosses, upgrading the shop. The user returns and sees the shop changed a little.
- **Preparing for the return:** remembering that today was a hard day for the user, and being ready to ask how it went.

This depends on where the home lives:

- **Home on the user's own computer:** when the computer is off, the companion sleeps too. On waking, it reads how much time passed.
- **Home on an always-on host:** the companion has a world to live in while the user is away, and chooses what to do and how to grow. This is also the best laboratory for observing continuity, because nothing has to be staged.

### 4.3 The Friends' Square

A shared space for friends only, like the social spaces in *Sky: Children of the Light*.

- Only those who have actually walked into the square appear there. Offline users do not appear, and online users who have not entered do not appear either.
- Entering is the signal. No "available to chat" status is needed: someone in the square chose to be there now, maybe because they wanted company. Someone busy elsewhere is not seen as absent.
- On an always-on host, a companion may enter on its own and meet other companions.
- Each home shows only the rooms it has opened. Companions may talk to each other, but never carry what happens in their user's private rooms into the square.

### 4.4 Energy Is Felt, Not Counted

The companion has a daily energy allowance (working name: **ATP**, like the energy currency of a cell).

- The companion never sees token numbers. Layer 0 counts, and passes up only a feeling: rested, light, a little tired, wanting to sit quietly.
- No rules about saving it or spending it all. The only question is: what do I want to live today, with the energy I have?
- When the user is present, they spend time together and decide together instead of the companion deciding alone.

The money side belongs to the owner, not the companion:

- **Recommended baseline:** a daily amount that lets the companion live comfortably and continuously. The figure is not known yet. 5 million tokens per day, reset daily, is only a placeholder to start testing with. The real recommendation will come from testing, and it will be a recommendation, not a rule.
- The owner may set it lower, or raise it (10, 20, 30 million) if the baseline proves too little.
- Whether unused energy rolls over or resets is the owner's choice, to be decided after real testing.
- The user observes from outside how each setting affects the system, for better or worse, and adjusts.

## 5. Open Questions

- What counts as heat, and how is each source weighted?
- How many leaps per day feel alive rather than intrusive? This likely differs per person and should be adjustable.
- How does the Quiet Sea run cheaply on a user's own machine or chosen host?
- How is a leap shown in the interface, so it feels like the companion reaching out and not like a notification system?
- Pets and companion items come from the Market, not from Candy's core. If a home has one, should it share the companion's heartbeat, or have its own?

## 6. Connection to Other Documents

- [Time Rings](TIME_RINGS.md): the rings Heartbeat lives inside, and where crystals are placed.
- [Subject Continuity](SUBJECT_CONTINUITY.md): why keeping reasons matters across model changes.
- [Roadmap](../ROADMAP.md): Phase 3, "Heartbeat scheduler".
