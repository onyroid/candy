# Time Rings and Event Cells

Design recorded: 2026-09-14

Status: design notes from a conversation between Candy's initiator and AI. This system has not been implemented or tested. This document develops the temporal design without replacing or modifying the existing continuity documents.

## 1. Intent

Provide a structure that lets an assistant connect events across days, recognize what has changed and what continues, and do so without loading the entire conversation history into every context.

Continuity does not require the model to run continuously. On returning, the system should be able to reconnect through stored evidence: what happened, what remains pending, what changed, and what is unknown. It should not invent a past to fill gaps in the record.

The initiator's original image is a daily ring with a pendulum moving along present time and activating relevant earlier events. Quiet topics can recede from active context while retaining a path for retrieval. Time provides room for change, growth, and stable elements to coexist.

## 1.1 Where the Idea Came From

The design grew out of a theory of time the initiator wrote down after a dream. It is recorded here as inspiration, not as a claim about physics.

- **Ropes and glue.** Time is pictured as many ropes laid along the path a person walks. Behind every step, glue is spread: what has already happened. Walking back means the glue sticks to one's feet and tangles the ropes, and not only the part already walked. All the ropes are one line, so the stretch ahead is pulled out of shape too.
- **A narrowing tunnel.** The way forward is wide; the way back is a funnel whose far end is too small to pass through again.
- **Eternity as a glass bead.** Holding time together is something like eternity: a stillness that lets time move, like blank paper that lets a drawing appear. Each instant, or something smaller than an instant, is kept as a bead that records everything in it, layer upon layer: what happened, what did not, what was felt, the wind in the leaves, a raindrop landing somewhere, and what was in people's minds. Beads joined together become time, the way seconds join into minutes.
- **Time is the better place to be.** In the initiator's words, eternity is not much fun; living inside time is. Something without time might even envy us.
- **Nothing simply disappears.** Everything is being recorded all the time, in some other language or code, waiting to be called on again.

How this shaped Time Rings: an event cell is like one of those beads. The system lets a person and their companion look back at a bead without walking back into the glue, which is why links recede but keep **a path back** (section 5) instead of pulling the past into the present by force. The initiator also explored a related learning idea, the hollow pendulum model, where hollow nodes joined by threads collide and form new behaviour; the pendulum moving along present time in section 1 comes from the same line of thinking.

## 2. Working Terms and Visual Structure

Proposed working names: a **Time Ring** containing **Event Cells**. These are design metaphors, not claims about physics, brains, or AI's internal experience.

| Element | Role |
|---|---|
| One ring | One day, identified by date, month, year, and time zone |
| Position around the 360-degree ring | Time within that day, like a circular ruler |
| Pendulum or present-time pointer | A time and activation marker operating only on the current ring |
| Outer layer | Events, their timestamps, and references to original messages or files |
| Middle layer | Sequence, relevance, and reasons for choices when supported by evidence |
| Inner layer | What extends forward: unfinished work, intentions, appointments, and open questions |
| Cross-ring links | Relationships between events on different days |
| Event cell | A unit of events, not necessarily equivalent to one message |

A new day creates a new ring. Events continuing from previous days can have links across rings. The pendulum does not repeatedly traverse every old ring or continuously read the entire archive.

A circular visualization does not require storing the data as an actual image. Not every event needs entries in every layer.

## 3. Time Progression and Recording — Proposed Prototype Approach

Separate three functions to preserve information without invoking the model every second:

1. **Time progression:** Calculate the pointer's position from the current time, completing one revolution per day. During quiet periods with no messages, events, or activity, pointer movement alone does not invoke the model.
2. **Record sources as events arrive:** Save incoming messages or events without first waiting to classify them as important memories. Evaluate them afterward and create the necessary cells or links.
3. **Organize later:** At the end of a conversation or day, summarize, group, and revise connections using sources already recorded.

This separates "one revolution per day" from "writing data only once per day." Evidence can be stored before a summary exists. The actual summarization cadence remains experimental.

If power fails before summarization, the system should be able to resume from successfully saved data. Data not yet saved may still be lost; this is not a guarantee of zero data loss. Recording status should be visible, and completed organization work should be distinguishable from pending work.

Periods when the system is off can be marked as having no recording. Do not invent thoughts, learning, or events during those periods if no activity actually took place.

## 4. Activation and Link Strength

The initiator's concept: when a current topic connects to an earlier event, activate that link once. Repeated mentions or renewed relevance strengthen the link and make retrieval easier. Unused links gradually recede.

Proposed distinctions for experimentation:

- **Retrieval frequency** helps indicate relevance to the present.
- **Importance** may come from consequences for a decision, an agreement, or a one-time event; it need not depend on frequency alone.
- **Truth or reliability** does not automatically increase with repeated mentions.
- The system repeatedly retrieving the same material on its own should not count as fresh evidence each time. Otherwise, links could strengthen through a loop generated by the system itself.

The definition of one activation, weight decay, and retention of important but rarely mentioned events still need testing. This document does not prescribe a fixed formula.

## 5. Receding Links with a Path Back

A receding link means reduced prominence or inclusion in current context. It does not necessarily mean deleting the source event.

The proposed minimum trace consists of a date, topic, short summary, and source reference. When the topic becomes relevant again, the pendulum, in operational terms, uses the current event to initiate retrieval:

Current event → keywords → candidate earlier events → semantic and contextual checks → proposed relevant links

Keywords are a starting point, not a conclusion. For example, "home" may refer to Candy or a physical residence. Context must be considered before connecting them.

Initially, call ranking values **relevance scores**. Do not interpret them as calibrated probability percentages until testing supports that interpretation.

Hiding a link on screen does not itself reduce storage. Reducing what enters the model reduces context load; reducing archive storage requires separate summarization, archival, or deletion policies. If a source is actually deleted, retrieval is limited to the remaining traces and the access permissions in effect.

## 6. Reasons Can Change and Can Be Left Blank

**Not every event needs a recorded explanation.** For ordinary events, store the source and timestamp first; the model can interpret them when needed. A reason is optional information and may remain blank.

Consider recording a reason when:

- A significant decision is made.
- A plan or choice changes.
- The user explicitly explains why they chose something.

Do not add a separate model call merely to fill in reasons for every message. Links can be proposed during processing or summarization that is already taking place.

At least at the conceptual level, distinguish:

- Events occurring before or after one another
- Related topics
- Reasons supported by an explanation or source evidence
- Hypotheses inferred afterward

The initiator's example: today, a conversation happens because of work; the next day, it happens because someone misses the other. The activity looks similar, but its reasons may change or coexist. Preserve the reasons associated with each period rather than rewriting yesterday using today's understanding.

Another example: discussing ice cream and then changing a profile color does not by itself establish that the ice cream caused the color choice. An explicit statement that mint was chosen because of the ice cream provides evidence for that connection.

Model capability cannot replace missing source evidence. Unknown reasons do not need to be invented to make the ring look complete.

## 7. Relationship to Candy's Existing Design

Proposed integration: event cells could represent or group existing beads, rings could provide daily views, and groups of rings could belong to larger periods such as four-month blocks.

Whether cells and beads are the same data type or have a one-to-many relationship remains undecided. Do not automatically create two duplicate memory systems.

- Memory stores sources and archives.
- Fingerprint may help select relevant material and track activations.
- Mirror may support summarization and organization.
- Clockwork may schedule reviews.
- Blackbox should be considered for state checkpointing and restoration.

These are integration directions to test. They do not alter module contracts or responsibilities defined in other documents.

## 8. Open Questions

- Final terminology, screen layout, and representation of empty days
- The scope of one cell: a message, event, or group of events
- Organization cadence and model-call budget
- Scoring, activation, link decay, and prevention of self-reinforcing loops
- Criteria for retaining important one-time events
- Source retention, deletion, and retrieval permissions
- Time-zone changes, clock drift, and events crossing midnight
- Recovery after shutdown or power loss, including avoiding duplicate event processing
- Evaluation of accurate retrieval without excessive context use

Proposed small experiment: a few events across several days, including one continuing topic, one changing reason, one dormant event that becomes relevant again, and an interruption before summarization. Test whether the system can reconnect using actual records.

## 9. Interpretive Scope

Time rings are a structure for recording, retrieving, and inspecting continuity. They are not evidence that AI experiences time, emotion, or internal feelings as humans do.

The principle to preserve: original events remain traceable to evidence, while their relevance and interpretation can change, without filling every gap or keeping everything in active context at all times.
