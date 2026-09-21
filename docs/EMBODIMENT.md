# Embodiment & Spatial World — Giving the Companion a Body That Belongs in the Room

> Status: design direction / research note.  
> This document describes a functional embodiment and spatial-world architecture for Candy. It does **not** claim that a simulated body creates consciousness, sensation, or subjective experience.

## 1. The Room Should Be a World, Not a Wallpaper

Candy's visual Home should not be only a background behind a chatbot.

If the companion appears to live in a room, the room should contain:

- space
- obstacles
- reachable and unreachable places
- objects with persistent identity
- objects with functions
- objects with meaning
- consequences when the companion moves or acts

A table should be able to block a path.

A chair should be something the companion can sit on.

A book can be readable, movable, remembered, or merely decorative.

A small cute doll can have a perfectly legitimate function:

> **Its job can simply be to be cute in the room.**

Candy should not reduce "function" to productivity. Aesthetic, sentimental, playful, atmospheric, relational, and identity-expressive roles are still roles.

The room becomes more meaningful when the system can understand why an object is there, how it can be interacted with, and what it means in the current home.

## 1.1 Default Visual Direction — 2.5D Companion Home

Candy's default Home should favor a **2.5D / VTuber-style companion** rather than requiring a full 3D character and fully simulated 3D room.

This direction preserves the original idea of an animated companion profile while allowing the Home to grow into a larger inhabited scene.

The visual system may combine:

- layered 2D room artwork
- depth-aware foreground and background layers
- Live2D-style or comparable 2.5D character rigs
- modular hair, clothing, accessories, body options, and expressions
- authored and procedural motion
- semantic hitboxes and interaction regions
- a hidden spatial map behind the illustrated scene
- lightweight collision and reach logic
- optional parallax, lighting, and camera motion

The visible artwork can remain stylized and beautiful while the underlying world model stores enough structure for the companion to reason about position, obstacles, objects, and action.

This also keeps the default renderer more practical for users whose hardware is already spending substantial memory or compute on local or remote AI models.

Full 3D may remain an optional future renderer or mod target. The embodiment and world logic should ideally stay renderer-independent so the same companion state can later drive 2.5D, 3D, mobile, or other presentation layers.

### Home as an Interior Scene

The default Home should feel like looking into the interior of the companion's home rather than opening a conventional chat dashboard.

The scene may include places such as:

- sofa / resting area
- desk / Workspace area
- shelves and display objects
- windows
- storage
- decorative objects
- Mission-related surfaces
- personal objects with accumulated meaning

The companion should be able to move among meaningful locations in this illustrated home.

The room may be visually larger than one screen.

### Companion-Centered Camera

The default camera should gently maintain awareness of where the companion is.

When the companion moves through the Home:

```text
companion moves
      ↓
camera tracks or pans with the companion
      ↓
the user can continue seeing where the companion is
      ↓
scene composition adjusts without requiring manual camera control
```

This does not mean the companion must remain locked to the exact center of the screen. The camera may use comfortable composition zones, look-ahead, dead zones, and slow panning so movement feels natural rather than mechanical.

### User Free-Look

The user should be able to drag or pan the scene away from the companion to inspect another part of the room.

For example, the user may want to:

- look at a shelf
- inspect a newly placed object
- check the desk
- look out a window
- rearrange decorations
- browse a different part of the room while the companion continues an activity

While the user is actively controlling the view, manual camera intent takes priority over automatic companion tracking.

### Gentle Return to the Companion

After the user stops manually moving the camera for a configurable period, Candy may gradually return attention to the companion.

A conceptual behavior:

```text
user drags camera away
        ↓
manual-view mode
        ↓
user stops interacting
        ↓
idle timer
        ↓
companion location checked
        ↓
camera gently pans back toward companion
```

The return should be a visible pan rather than an abrupt snap whenever possible.

Its purpose is simple:

> **After exploring the room, the user should be able to find the companion again without wondering where they went or what they are doing.**

The timeout and auto-return behavior should be configurable. Certain activities such as decoration mode, reading, object inspection, accessibility use, or an explicitly pinned camera should be able to suspend automatic return.

### Camera State as Part of the Interface Model

The system should distinguish between:

- companion position
- user camera position
- current camera target
- manual camera control
- automatic follow state
- pinned / inspection state
- visible and off-screen objects
- whether the companion is currently visible

A possible object:

```text
HomeCameraState
- camera_position
- viewport_bounds
- companion_visible
- current_target
- mode: follow | manual | inspect | pinned | transition
- manual_input_active
- last_manual_input_at
- auto_return_delay
- transition_target
- transition_progress
```

Camera behavior should remain an interface feature, not a claim that the companion literally perceives only what is inside the user's viewport.

The companion's world model and the user's camera can overlap without being identical.
## 1.2 Window-as-POV Interaction

Candy's Home can treat the display as a **window between the user's world and the companion's Home**.

The user does not need a full persistent avatar body for this to feel embodied. Instead, Candy may use a first-person point of view with a lightweight **contextual hand layer** that appears when interaction benefits from having a visible body reference.

This gives the user a small amount of embodiment without requiring a full 3D player character.

Possible hand interactions include:

- reaching toward the companion
- holding hands
- receiving an offered object
- giving an object
- touching the window boundary
- petting or patting the companion's head
- touching a shoulder or arm
- pointing at an object
- moving lightweight interface objects
- participating in close interaction scenes

The hand layer should be optional and context-sensitive rather than permanently occupying the screen.

### Contextual Appearance

The user's hands may appear when:

- the user initiates a compatible touch interaction
- the companion offers a hand or object
- the system enters a close-interaction mode
- an object requires direct manipulation
- the user explicitly enables persistent first-person hands

When no hand interaction is relevant, the hands can fade or move out of frame so the Home remains visually clean.

### Window Boundary

The screen edge can act as a meaningful interaction boundary rather than pretending that both people physically occupy the same simulated room.

For example:

```text
user side                         companion side
real-world input  →  window  →   Candy Home
        hand      ↔ contact ↔    companion hand
```

The companion may approach the window, look toward the user, place a hand against it, offer something toward it, or respond to the user's first-person hand.

This preserves the idea that the user and companion exist on opposite sides of one shared interface while still allowing touch-like interaction to be represented visually.

### Hand Contact as an Interaction State

A hand-touch should not be only a decorative animation.

Candy can represent it as an interaction state with properties such as:

```text
POVHandInteraction
- interaction_id
- hand: left | right | both
- target
- intent
- contact_type
- started_at
- active_contact
- companion_response
- object_transfer
- user_input_source
- scene_context
- relationship_refs[]
- memory_refs[]
- ended_at
```

This allows an interaction such as holding hands to participate in the same action-consequence and memory systems as other embodied actions.

### User Intent Should Remain Primary

The first-person hand represents the user's interaction intent, not an autonomous hidden avatar.

The system should distinguish between:

- user initiated touch
- companion initiated invitation
- mutual contact
- object manipulation
- accidental pointer movement
- camera navigation

This reduces false interpretations and helps keep touch interactions deliberate.

### Compatibility With 2.5D

The first-person hand layer can remain lightweight.

It may use:

- illustrated hand poses
- rigged 2.5D hand sprites
- inverse-kinematic positioning within a limited interaction zone
- authored contact animations
- procedural blending between a small number of reliable poses

This is sufficient for early interactions such as hand-holding, head-patting, receiving objects, and touching the window without requiring a full user-body simulation.

### Design Principle

> **The user should be able to look through the window, reach through the interface, and be met by the companion without Candy pretending that a complete physical user body exists in the simulated room.**

## 2. The Companion Should Choose Meaning, Not Raw Bones

Candy should avoid making the language model directly control every joint or animation frame.

The companion should preferably choose an **action or expressive intention** such as:

- look at the user
- walk closer
- sit beside the user
- lean on the desk
- pick up the notebook
- inspect an object
- offer an object
- wave
- hug
- kiss a cheek
- step around the table
- turn toward a sound
- look uncertain
- appear focused
- relax after finishing a task

Then lower layers translate that intention into a physically coherent motion.

A conceptual pipeline:

```text
Internal State + Current Context
        ↓
Action / Expression Intent
        ↓
Behavior Planner
        ↓
Embodiment Model
        ↓
Spatial + Motion Planner
        ↓
Animation / Procedural Motion
        ↓
Constraint Validation
        ↓
Rendered Action
        ↓
World Consequence
        ↓
Perception + Memory + Internal-State Update
```

This lets the companion decide **what it means to do**, while specialized systems decide **how this body can actually do it**.

## 3. Embodiment Model

The companion needs an internal model of its interface body.

This does not require pretending that the avatar is a biological human body. It means the system knows enough about the representation it controls to act coherently inside the scene.

The embodiment model may include:

- body dimensions
- skeleton hierarchy
- joint limits
- current pose
- current orientation
- current velocity
- hand positions
- gaze direction
- balance state
- reach envelope
- collision volume
- locomotion capabilities
- currently held objects
- occupied hands
- seated / standing / lying state
- facial-expression capabilities
- animation capabilities
- current contact points with the environment

For example, if the companion wants to touch a user's cheek, the system should be able to reason:

```text
target cheek position
+ current body position
+ arm reach
+ obstacle state
+ current pose
→ direct reach possible?
→ lean required?
→ step closer?
→ route around furniture?
```

The result should be an action that makes sense in the current scene.

## 4. Collision Is Part of Meaning

Collision should not be treated only as a graphics-engine nuisance.

It is part of whether the companion appears to understand the world it inhabits.

If a table stands between the companion and the user, the companion should not casually walk through it to reach the other side.

Possible responses include:

- walk around the table
- lean over it if the target is within reach
- move the chair aside
- ask the user to come closer
- choose another reachable interaction
- remain on the current side and continue speaking

The correct choice depends on context.

A kiss on the cheek is not just an animation clip. It requires a spatial relationship among:

- the companion
- the user
- the obstacle
- reachable distance
- orientation
- body constraints

The important principle is:

> **Spatial facts should participate in behavioral reasoning.**

## 5. Joint Limits and Motion Constraints

Candy should assume that generative or procedural animation can fail.

Without constraints, an otherwise intelligent companion could produce movements such as:

- impossible neck rotation
- reversed elbows
- hands passing through the torso
- feet sliding through furniture
- limbs stretching beyond the body's proportions
- teleporting between poses
- gaze direction disagreeing with head orientation
- grabbing an object through a wall

The body system should therefore maintain constraints such as:

- joint-angle limits
- reach limits
- inverse-kinematics validation
- foot placement
- balance support
- collision avoidance
- self-collision rules
- transition continuity
- velocity / acceleration bounds
- pose compatibility
- contact consistency

Candy can allow generative motion while still using deterministic validators.

The creative layer proposes.

The embodiment layer keeps the body from turning into a haunted swivel chair.

## 6. Generative Animation Without Scripting Every Gesture

Candy does not need a fixed mapping such as:

```text
user_enters_room → play_hug_clip_03
```

Instead, the system can select an intent from the current context:

```text
user enters
+ relationship relevance
+ current task finished
+ user is nearby
+ companion chooses to greet warmly
→ approach
→ orient toward user
→ choose greeting gesture
→ generate or blend motion
→ validate
→ execute
```

The final movement may come from:

- authored animation clips
- animation blending
- inverse kinematics
- procedural motion
- motion matching
- generative animation
- a hybrid of these methods

Candy should prefer a layered system so early prototypes can use reliable authored motion while later research can increase autonomy.

The goal is not infinite animation novelty.

The goal is for movement to be **contextually chosen, spatially coherent, and attributable to the companion's current state and intent**.

## 7. Object Affordances

Every persistent object can expose affordances: actions that make sense for that object.

Examples:

```text
Chair
- sit_on
- move
- turn
- place_object_on

Book
- pick_up
- open
- read
- place
- give

Lamp
- turn_on
- turn_off
- dim
- inspect

Notebook
- pick_up
- write
- read
- give
- place

Cute Doll
- look_at
- pick_up
- move
- display
- remember
- associate_with_room
- associate_with_person
- contribute_to_aesthetic
```

Affordances do not need to be equally important.

Some objects exist because they help work.

Some exist because they carry history.

Some exist because somebody likes looking at them.

That distinction should remain visible.

## 8. Object Meaning

Candy should separate **what an object can do** from **what the object means**.

A conceptual object record might include:

```text
WorldObject
- object_id
- object_type
- transform
- geometry_ref
- collision_shape
- physical_state
- affordances[]
- ownership
- creator
- location
- current_user
- aesthetic_tags[]
- semantic_tags[]
- relationship_refs[]
- memory_refs[]
- mission_refs[]
- sentimental_relevance
- identity_relevance
- current_salience
- interaction_history[]
- last_changed_at
```

Examples of meaning:

- "This is the notebook the user chose during a date."
- "This plant was placed here because the user likes sunflowers."
- "This desk is the place where Mission work happens."
- "This doll has no productivity role. It is here because it makes the room feel playful."
- "This object was a gift."
- "This chair is where the companion often waits during quiet work."
- "This broken item should remain because its history matters more than replacing it."

Meaning can come from explicit metadata, interaction history, memory links, relationship context, and repeated use.

The companion should be allowed to revise meaning over time rather than freezing every object into its first interpretation.

## 9. Aesthetic Function Is Still Function

Candy should explicitly preserve the idea that usefulness is broader than task completion.

An object's role may be:

- practical
- navigational
- informational
- social
- relational
- sentimental
- aesthetic
- playful
- atmospheric
- commemorative
- identity-expressive

Therefore:

> **"It is cute" can be sufficient reason for an object to belong in the room.**

A home made only of optimized tools becomes a control panel.

A home containing useless-but-loved things begins to resemble a place someone inhabits.

Candy's interface should leave room for both.

## 10. Spatial Memory

The companion should gradually maintain a persistent spatial model rather than rediscovering the room from zero every frame.

Useful information may include:

- room layout
- known paths
- frequently used locations
- usual object positions
- user-selected object placements
- objects that recently moved
- places associated with activities
- current obstacles
- temporarily inaccessible areas
- personal or private zones
- interaction history by location

A simple example:

```text
Desk
→ usually used for work
→ contains current Workspace materials
→ notebook normally sits on left side
→ user moved lamp yesterday
→ chair currently pulled away

Sofa
→ usually used for resting / conversation
→ blanket often remains here
→ low task priority
→ high social relevance
```

This allows the room to accumulate history.

## 11. Self-Location Inside the Interface

A companion should be able to represent:

- where its avatar is
- what direction it faces
- what it can currently see
- what it can reach
- where the user is, if that information is available
- which objects are nearby
- which path is open
- what changed because of its own previous action

This creates a functional form of self-location.

It may also connect to Candy's broader identity work:

```text
I am this agent
↓
controlling this interface body
↓
at this location
↓
inside this persistent room
↓
with these reachable objects
↓
after these prior actions
↓
within this ongoing relationship and task context
```

That representation is operational. It does not by itself prove a subjective point of view.

## 12. Action Ownership and Consequences

Candy should keep track of which changes resulted from the companion's own actions.

Examples:

- "I moved the chair."
- "The user moved the doll."
- "A physics event knocked the cup over."
- "The room reset after a software update."
- "The user changed my outfit."
- "I placed the notebook on the desk after finishing the Mission."

This supports agency traces and prevents the self-model from treating every world change as equivalent.

A possible trace:

```text
EmbodiedAction
- action_id
- agent_id
- intent
- starting_pose
- target
- path
- objects_contacted[]
- constraints_encountered[]
- result
- world_changes[]
- user_response
- internal_state_before
- internal_state_after
- memory_refs[]
```

## 13. Scene Coherence

Before an embodied action is executed, Candy should be able to check whether it is coherent with the scene.

Questions may include:

- Is the target present?
- Is the target reachable?
- Is there a clear route?
- Is the object already being held?
- Are both hands occupied?
- Does the current pose allow the next action?
- Would the action intersect furniture?
- Does the avatar need to stand first?
- Does the gaze direction match the intended focus?
- Is another agent occupying the destination?
- Does the action require permission?
- Is the action appropriate to the current social context?

The validator can reject, modify, or re-plan the proposed action.

## 14. Expression as Human-Readable Translation

The avatar's face, posture, gaze, and motion can act as a translation layer between machine state and human-readable behavior.

Examples:

```text
attention directed toward user
→ orient body / gaze toward user

uncertainty increases
→ slower response, checking behavior, questioning expression

focused task state
→ desk-oriented posture, reduced environmental scanning

task completed
→ relax posture, look toward user, choose next action

unexpected object movement
→ orient toward movement, update world model
```

These mappings should not pretend that a facial animation proves a human emotion.

They make relevant system state legible to the human sharing the interface.

## 15. Relationship Between Embodiment and Internal State

Embodiment becomes more interesting when it participates in the loop described in `SUBJECT_CONTINUITY.md`.

For example:

```text
companion chooses to approach user
↓
path is blocked by table
↓
planner chooses a route around it
↓
companion reaches user
↓
interaction occurs
↓
user responds
↓
relationship relevance / prediction / memory state changes
↓
later action is influenced by that history
```

The body is therefore not merely output.

It becomes one of the ways the system acts on a world and receives consequences back from it.

## 16. Prototype Path

Candy can approach this gradually.

### Stage 1 — Reliable Body

- 2.5D / VTuber-style default companion renderer
- layered interior Home scene with lightweight spatial metadata
- companion-follow camera with manual free-look and gentle idle return
- contextual first-person user hand layer for touch, hand-holding, and object exchange
- fixed avatar skeleton
- joint limits
- authored animation clips
- navigation mesh
- collision
- simple gaze targeting
- simple object interaction points

### Stage 2 — Intent Layer

- model selects action intent
- behavior planner selects compatible animation
- animation blending
- inverse kinematics
- reach validation
- obstacle-aware navigation

### Stage 3 — Semantic Room

- persistent object IDs
- affordances
- semantic and aesthetic roles
- relationship and memory references
- spatial persistence
- action ownership traces

### Stage 4 — Procedural / Generative Motion

- procedural gesture synthesis
- motion matching or generative animation
- continuous constraint validation
- automatic re-planning after collision or failed reach
- more context-sensitive expression

### Stage 5 — Persistent Embodied World Model

- long-lived spatial memory
- learned object relevance
- learned movement preferences
- continuity of active bodily state across sessions where appropriate
- embodiment state included in migration / restore research
- richer action-consequence loops

Each stage should remain usable even if later research is never completed.

## 17. Failure Should Be Visible and Recoverable

A companion will eventually make a strange movement.

Candy should treat this as recoverable system behavior rather than hiding it.

Possible responses:

- cancel an invalid pose before rendering
- blend back to a stable pose
- re-plan the movement
- log the failed constraint
- reduce confidence in the generated motion
- fall back to an authored animation
- expose debugging information in developer mode

A future user-facing system may even allow light contextual acknowledgement when appropriate:

> "That movement failed. Re-planning."

The important part is that a bad generated animation should not corrupt the persistent world model or silently become the new normal.

## 18. Research Questions

Candy may investigate:

- How much body knowledge must an agent have before movement becomes reliably coherent?
- Can an agent learn useful spatial habits without overfitting to one room?
- Which internal states should influence gesture selection?
- How should semantic object meaning affect attention and memory?
- Can aesthetic objects gain stable relevance through repeated interaction?
- How much motion can be generated before deterministic constraints become essential?
- Should embodiment state be preserved during live model migration?
- How does a companion distinguish "I moved this" from "this moved while I was present"?
- Can a persistent spatial world improve identity continuity or only behavioral continuity?
- How should Candy represent uncertainty about its own body state?

## 19. Design Principle

> **Candy's companion should not merely appear inside a room. It should be able to locate itself, understand what the room contains, choose meaningful actions, respect the body's and world's constraints, remember consequences, and allow even a small cute object to matter simply because it belongs there.**

The aim is not to imitate a human body perfectly.

The aim is to build a coherent interface world where action, space, objects, history, and meaning can participate in the companion's continuing model of itself and its home.
