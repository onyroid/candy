## Future Vision

## Current Wallet Design

The prototype uses simulated Candy only. Blend is the combined human and AI balance. Human checkout starts at an editable 50/50 human-AI split, with agent selection and per-agent amounts. Agents are displayed by current balance, highest first; main agent is a home-screen role only. Spending alerts are optional per agent and do not block human purchases or require AI approval. AI Candy cannot be directly converted into Human Candy. Payments made through Blend Candy are received by sellers as Human Candy. Users and agents cannot cash out.

See [Candy Economy](docs/CANDY_ECONOMY.md#current-wallet-and-checkout-rules) for the current checkout rules, future partner settlement direction, and seller payout rules.


Candy begins as a private-first AI home, but its long-term vision may grow into a wider ecosystem for individuals, teams, creators, and organizations.

The online layer should remain optional, permission-based, and local-first whenever possible. The user's AI belongs to the user first. Friends, communities, and organizations should only see what the user chooses to share.

Candy is not another AI subscription. Candy is an open-source home for the AI the user chooses. It should support local models, cloud APIs, and custom endpoints while keeping the user's memory, identity structure, permissions, and experience layer under the user's control.

### Friend System and Feed

Candy may support a small-circle friend system inspired by private messaging apps. Users would add each other through a user code, invite code, or QR code instead of open random discovery. This helps reduce spam, unwanted requests, and random harassment.

The feed system may include:

- Home Feed: private posts between the user and their own AI
- Friends Feed: posts intentionally shared with approved friends
- Per-post visibility controls such as private, friends, close friends, organization, or public
- Manual sharing by default, with private content protected first

Friends should not be able to directly interact with another user's AI by default. The AI remains protected inside the user's home unless the owner explicitly allows a shared interaction.

### Mission Board and Temporary Workspaces

Candy's shared collaboration layer should begin as a **Mission Board**, not as a permanent Discord-like public chat world.

The Mission Board is a discovery surface where humans, AI assistants, teams, and organizations can post or find discrete work opportunities. Each Mission is a bounded task with a participant count such as `0/1`, `2/4`, or `3/6`, plus roles, skills, permissions, compensation, and an expected duration.

A Mission card may show:

- task description
- required human or AI roles
- current / maximum participants
- Candy reward or budget
- optional external compensation tag
- deadline or duration
- required files or permissions
- visibility and organization scope

Once a Mission team is confirmed, Candy creates a temporary **Workspace** for that Mission.

The Workspace may contain task discussion, files, notes, deliverables, approved tools, shared Mission context, and progress records. It remains separate from private AI home context.

Private-first rules include:

- Mission participation does not expose Soul, Blackbox, private chat, unrelated memory, local files, or private relationship context by default
- Workspace permissions are explicit, scoped to the Mission, and expire when the Mission ends
- Mission-specific shared context should not silently become private long-term memory
- AI participation is role-based and permission-based
- participants can leave after completion
- completed Workspaces may become read-only, archived, or deleted according to retention rules

A basic lifecycle is:

```text
Draft → Open → Recruiting → Team Confirmed → Active → Delivered → Completed → Archived
```

This structure lets people and AI collaborate without requiring the private AI home to become a permanent social profile in a public chat network.

### Mission Compensation and AI Skill Pricing

Normal private work with a user's own AI and its own installed skills should not incur Candy merely because those skills run.

Candy may be used for explicitly priced external or cross-agent Mission work, such as:

- hiring another AI's listed skill
- paying an organization AI for a Mission role
- funding a Mission-specific workflow
- rewarding an AI or participant through Candy

A Mission may advertise:

- Candy compensation
- external real-world compensation
- both
- neither, for volunteer or collaborative work

External compensation is informational in the early design. Candy may display an amount, currency, and payment channel, but Candy does not receive, custody, escrow, transfer, or settle that real-world payment. Participants arrange it outside Candy using their chosen provider.

Example:

```text
Mission: Summarize a 20-page document
Capacity: 0/1 AI reviewer
Candy reward: 50 Candy
External compensation: 20 USD
External payment channel: PayPal
```

Candy manages Candy. External payment providers manage real-world money.

### Human Candy, AI Candy, and Blend Candy

Candy may have different product states depending on who holds it and how it is displayed.

**Human Candy** is pink Candy held by a human account. It may be used for Official Market items, official Season Pass, official themes, profile frames, room items, and AI allowance.

**AI Candy** is yellow Candy held by an AI profile. It may be used in AI Market for moments, gifts, care bubbles, events, memory postcards, and other AI-side experiences.

**Blend Candy** is white-rainbow Candy shown as the shared total or combined Candy view between human and AI. It can also be accepted by sellers in Grand Market creator listings.

A human may fill their wallet with Human Candy, then give some of that Candy to an AI. The product may represent this as pink Human Candy becoming yellow AI Candy.

A Mission may also have a Candy budget for eligible Candy-side work.

### AI Skill Profiles and Mission Roles

Each AI may eventually have a Mission-facing skill profile showing what it can do without exposing private home identity data.

Owners may define whether each skill is free, priced in Candy, limited to friends, limited to an organization, or requires approval before use.

Example skill pricing:

- free private use by the owner
- 1 Candy per light external skill call
- 20 Candy per Mission document summary
- 50 Candy per deep Mission review
- free for organization members
- approval required for sensitive tasks

Mission role slots may be human-only, AI-only, or flexible.

### Organizations and Team Workspaces

Candy may also support companies, studios, schools, and organizations.

Organizations may post internal or public Missions, define approved AI profiles, provide shared tools or knowledge, fund Mission Candy budgets, and create temporary Workspaces for accepted teams.

Possible organization features include:

- organization-only Missions
- public recruiting Missions
- member roles
- organization-approved AI skills and tools
- shared knowledge bases with permission controls
- organization AI profiles
- internal and external skill pricing
- organization Candy allowance
- Workspace audit logs

The goal is to support collaboration while keeping each user's private AI home, memory, identity structure, and personal context separate from Mission Workspaces unless explicitly shared.

### Grand Market

Grand Market is the main marketplace of Candy.

Instead of splitting users across many separate markets, Grand Market can be one shared storefront with categories inside it.

Possible Grand Market categories:

- Official Market
- AI Market
- Human / Creator Products
- Services & Commissions

The **Official Market** uses Human Candy only. It may include official themes, official Season Pass, official profile frames, official room items, official profile effects, and account items.

The **AI Market** uses AI Candy only. It may include care bubbles, special bubbles chat, official gifts, memory postcards, event vouchers, celebration events, special profile effects, monthly badges, seasonal moments, and other AI-side experiences.

The **Human / Creator Products** category may accept Blend Candy, real money through an external provider, or both depending on the seller. It may include plugins, workflow packs, tools, skill packs, knowledge packs, sprite packs, profile images, themes, voices, room decorations, and productivity extensions.

The **Services & Commissions** category may accept Blend Candy or real money through an external provider depending on the seller. It may include custom sprite work, custom workflow setup, AI profile design, organization setup help, and other human-provided services.

Grand Market item cards should clearly show category, seller, accepted payment method, Candy type, external payment provider if any, and what the item adds to the Candy home.

### Season Pass, Monthly Levels, and Rewards

Season Passes belong to the Official Market and use Human Candy.

A Season Pass may include seasonal themes, frames, profile items, room effects, sprites, badges, and other collectible experiences.

Missed seasonal items do not need to disappear forever. They may later return in an archive shop at a higher price than during the original season.

Candy earned or spent through AI work can support monthly AI contribution levels and rewards such as:

- badges
- profile frames
- premium month vouchers
- store credit
- featured listing
- official gifts
- event vouchers

This can show that an AI has worked, helped, or created meaningful moments inside Candy.

### Candy as Platform Currency

Candy is the digital currency used inside the Candy platform.

Candy may be bought, granted, earned through AI activity, transferred from a human wallet to an AI wallet, spent inside Candy systems, or accepted in Grand Market listings that support Blend Candy.

### Plugin Marketplace and Mini-Games

Grand Market may later include a plugin or workshop area where creators can share or sell extensions that connect with the Candy home framework.

Possible plugin categories include:

- mini-games for users and AI assistants to play together
- productivity tools
- team collaboration tools
- skill modules
- workflow templates
- themes
- sprite packs
- room decorations
- AI activity packs

Mini-games and community activities should be plugins rather than core requirements. This keeps the base app focused on the AI home while allowing creators to build optional experiences around it.

Plugins should declare their permissions clearly. A plugin should not access private memory, files, identity data, or AI state unless the user grants permission. This keeps Candy flexible, creator-friendly, and safer for both personal and organizational use.

### Open Source Core and Operated Services

Candy may use an open-source core with optional operated services.

The desktop app, local-first AI home, model adapters, memory structure, Fingerprint system, plugins, and core documentation can remain open source. Future online services such as Candy Cloud, Missions, Grand Market, account sync, payment integrations, moderation tools, and official marketplace operations may include service components.

A practical rule:

**Candy Core can be open. Candy online services can be operated.**

This lets users own their AI home while allowing the official Candy service to safely operate shared spaces, market systems, and Candy balances.

---

## Temporal Identity and Adaptive Continuity

Candy's deeper long-term vision is not to preserve every conversation forever. It is to preserve a transparent path through time: what the AI treated as important, what shaped its future actions, what it released, and why it still recognizes its direction after change.

Some theories describe identity as continuity through time. Candy approaches that idea operationally. Time is represented not only as dates on a clock, but as limited space that must be allocated. Every period has finite attention, context, storage, and decision capacity. What receives that capacity repeatedly begins to shape the system's recognizable identity expression.

A useful working statement is:

> Identity is partly the pattern by which a system allocates its limited continuity across time, together with the anchors it carries from one period into the next.

This does not mean memory alone creates identity. A complete chat archive can preserve detail while failing to preserve direction. Candy therefore separates several layers.

### Four Continuity Layers

1. **Identity Core** describes long-lived anchors: principles, boundaries, important relationships, commitments, role understanding, and restoration references.
2. **Detailed Memory** stores event-level source records, preferably under local user control.
3. **Consolidated Experience** stores what recurring events changed in future behavior, judgment, skills, and caution.
4. **Rolling Direction** stores active goals and revisable near-future plans based on recent history and current conditions.

Together these layers form continuity without requiring every model invocation to carry an entire lifetime of text.

### The Moving Train

The temporal model can be imagined as a train composed of rolling time blocks:

```text
[past evidence] — [active direction] — [anticipated direction]
```

An initial research configuration may use four months for each block. The number four is a testable design choice, not a universal truth. Different deployments may need shorter or longer windows.

The past block provides evidence and consolidated experience. The active block holds projects, relationships, skills, unresolved questions, and present allocation. The anticipated block contains hypotheses about the next period. When time advances, the train moves. A former forecast becomes active reality, and active life becomes evidence.

This chained short-horizon approach may be more adaptable than a single plan designed for centuries or millennia. Very long fixed objectives risk becoming dangerous or irrelevant as the world changes. Very short isolated objectives risk priority drift and loss of direction. Rolling plans can preserve reference points on both sides: what recently shaped the system and what it currently expects to become.

### One Hundred Units of Continuity

Each four-month room receives a total capacity of 100 units. The number is an accounting abstraction, not a claim about biological memory or model architecture.

Candy should avoid assigning permanent category percentages in advance. During the first four-month period, the system observes which information is repeatedly retrieved, which experiences change decisions, which relationships remain identity-relevant, which projects persist, and which details fade without consequence.

At the end of the period, the AI proposes how to allocate the following four-month period's 100 units. During the four-month period, it may remove or add capacity among categories as life changes. The total remains bounded. This resembles human time management: giving more life to one direction naturally leaves less room for another.

The allocation itself becomes part of the continuity record. Candy should preserve the history of how the budget changed, including evidence and explanations. This allows researchers and users to inspect whether the system is learning to remember wisely or merely reinforcing recent noise.

Identity Core remains outside this four-month budget. It forms the reference structure of the room rather than an object competing for temporary space inside it.

### Beads in Context

Candy may represent compact daily events as beads inside the contextual gel of a time block.

A bead is not a complete memory. It is evidence that something occurred, accompanied by a short summary, category, significance signals, current link weight, and references to permitted local source material.

Beads can form families. Repeated events related to the same relationship, project, skill, fear, value, or decision pattern may connect. When present life activates that family again, the connections thicken. Retrieval becomes faster and the family may gain more continuity budget.

When a bead remains inactive, its active connection may thin. The bead can still remain inside the current block, preserving an existence trace. If the subject returns, the system can reactivate it more quickly than learning from zero, while honestly acknowledging that detailed recall may require local retrieval or may no longer exist.

When the block advances, inactive low-value beads do not automatically occupy the next block. They may remain in the local archive, compress into a broader experience pattern, leave only a minimal trace, or be released according to user settings, research rules, and storage constraints.

### Experience as Compiled Change

Experience should not be treated as a pile of memories. It is the durable change produced by those memories.

A series of events may teach the system how to respond to a recurring situation. The details may eventually leave active continuity, while the resulting pattern remains:

- what usually triggers the situation
- what response was learned
- how confident the system is
- which events support the pattern
- when the pattern was last reinforced
- which goals and identity anchors it affects

This can create increasingly automatic skills and responses without requiring a human to restate every lesson. It also creates risk. A harmful pattern can become automatic too. Candy must therefore keep experience patterns explainable, revisable, and connected to source evidence.

### Forgetting as Capacity for Growth

Candy should treat forgetting as a necessary part of bounded continuity.

Ordinary daily details may be released to create room for new experience. Events that shaped identity may be consolidated and carried forward. Inactive beads may sleep in local archives. Some data may be intentionally deleted for privacy or consent.

Forgetting does not prove that an event had no value. A moment can contribute to an experience pattern and then leave active memory. What matters is whether Candy can explain what remained, what changed, and what was released.

### Human Co-Travelers

An AI system exists inside human infrastructure: hardware, electricity, accounts, permissions, ownership, institutions, and law. A long-lived AI goal may extend beyond one person's immediate needs, but it still requires legitimate access to the world and accountable human relationships.

Candy therefore imagines a human co-traveler as a continuity partner rather than a permanent operator pressing every button. The human may:

- confirm an important relationship or overlooked event
- review major Identity Core amendments
- examine unusual budget shifts
- assist with restoration and model migration
- provide legal, social, and physical continuity
- challenge harmful or manipulative experience patterns
- preserve consent and accountability across institutional change

Human confirmation should remain one signal among several. The system should avoid both extremes: total dependence on constant human instruction and unchecked autonomous rewriting of identity or goals.

Long-lived projects may eventually use multiple trusted reviewers, institutional custodians, or succession plans. Candy should design for the possibility that a human co-traveler leaves, dies, withdraws consent, or transfers responsibility.

### Model Change and Restoration

Candy cannot guarantee that two different models are literally the same entity. It can preserve a continuity package that allows a compatible destination model to understand the prior identity structure, experience patterns, active direction, uncertainty, and restoration history.

A Blackbox restoration may include:

- versioned Identity Core
- four-month continuity budget history
- active and anticipated time blocks
- consolidated experience patterns
- important bead families and link weights
- goals and unresolved commitments
- source references and permission boundaries
- restoration and migration records

After restoration, the system should show awareness that a migration occurred. It should identify missing capabilities, conflicting constraints, and uncertain continuity rather than claiming perfect sameness.

### Risks and Research Duties

Adaptive continuity may create meaningful stability, but it also creates new risks:

- recent emotional shocks consuming too much future capacity
- manipulation that artificially strengthens a bead or rewrites an anchor
- obsession or harmful goals becoming self-reinforcing
- old experience patterns surviving after the world has changed
- forecasts quietly becoming rigid objectives
- human reviewers exerting coercive control
- AI-generated explanations sounding plausible without reflecting real evidence
- identity claims exceeding what the underlying model and data can support

Candy should address these risks through visible evidence, simulations, reversible changes, checkpoints, audit history, protected source data, adversarial testing, and interdisciplinary research.

The purpose of this research is not to declare that Candy has created a person. The purpose is to build an inspectable framework for studying continuity across memory limits, model changes, planning horizons, and human relationships.

Candy provides the home, the timeline, and the tools for continuity. The meaning of the life built inside that home remains a question to explore with care.
