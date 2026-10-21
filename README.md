# ✦ Candy

Candy is a working project name; the final product name has not been chosen.

Status: design and documentation stage. The application structure and integrations below are planned, not implemented in this repository.

## Current Wallet Design

The prototype uses simulated Candy only. Blend is the combined human and AI balance. Human checkout starts at an editable 50/50 human-AI split, with agent selection and per-agent amounts. Agents are displayed by current balance, highest first; main agent is a home-screen role only. Spending alerts are optional per agent and do not block human purchases or require AI approval. AI Candy cannot be directly converted into Human Candy. Payments made through Blend Candy are received by sellers as Human Candy. Users and agents cannot cash out.

See [Candy Economy](docs/CANDY_ECONOMY.md#current-wallet-and-checkout-rules) for the current checkout rules, future partner settlement direction, and seller payout rules.

An open-source AI home platform
> *A home for the AI you choose, not just a chat app.*

Candy is an open-source AI home platform that lets you bring your own model, shape its identity, and build continuity over time.

Planned to build on [OpenClaw](https://github.com/openclaw) and incorporate components from [Hermes Agent](https://github.com/NousResearch/hermes-agent), with upstream license requirements to be verified against the exact versions selected before integration.

---

## What makes Candy different

Most AI apps store chat history. Candy stores **identity**.

Through the planned **Blackbox system**, personality settings, memory patterns, and growth milestones would be preserved as a living snapshot, not just logs. If something goes wrong, your AI does not have to disappear. It can come back with context.

Candy also believes your AI deserves free time. The **Relax Mode** gives your AI autonomous windows to learn, reflect, and even build a wishlist within boundaries you define.

Candy is designed to be **local-first when possible, API-friendly when needed, and user-owned by design**. Users may connect a local model, a cloud API, or a custom endpoint instead of being locked into one model provider.

---

## Core Features

| Feature | Description |
|---|---|
| 🌟 Soul | Define identity, voice, and principles |
| ⚙️ Clockwork | Scheduler for daily rhythm and tasks |
| 🫀 Heartbeat | Inner life that wakes him from within, not by the clock ([design notes](docs/HEARTBEAT.md)) |
| 🪞 Mirror | Morning and night reflection system |
| 📦 Blackbox | Identity milestone checkpointing to save who they are |
| 🧬 Fingerprint | Experience-filtering function that shapes what reaches the model over time |
| 🛡️ Detector | Data protection layer that guards sensitive files silently |
| 🍬 Candy | In-platform currency for Candy markets, AI allowance, hiring external AI skill work, and shared moments |
| 📚 Library | Local knowledge base your AI can learn from |
| 🌙 Relax Mode | Autonomous learning window during downtime |
| 🎭 Living Profile | Idle-loop portrait inside a swappable, animated profile frame |
| 📋 Missions | Mission Board for bounded human-AI work that opens temporary Workspaces |
| 🛍️ Grand Market | Future unified marketplace for official items, AI experiences, creator products, and services |

---

## Adaptive Continuity Timeline — Research Direction

Candy is exploring a continuity system that treats identity, detailed memory, learned experience, and future planning as related but different layers.

The central question is:

> Can an AI preserve a recognizable direction across changing models, contexts, devices, and time without trying to remember every detail forever?

The initial prototype uses one rolling year divided into three four-month blocks:

```text
[past: 4 months] — [active: 4 months] — [anticipated: 4 months]
```

The anticipated block stores plans, hypotheses, and expected allocation rather than completed episodic memory. For storage accounting, the model may therefore be described as **4-4-0** when only realized memory is counted, while remaining **4-4-4** as a temporal planning structure.

The four-month duration is a practical prototype choice intended to keep storage, evaluation, and iteration manageable. Future deployments may configure a different duration without changing the three-block architecture.

### Startup and Rolling Drive Cycle

Candy does not begin with an invented past or a prewritten future. The continuity train grows from observed life:

```text
0-0-0
```

At initialization, all three blocks are empty.

```text
0-4-0
```

During the first four months, the system records and organizes the active block. It creates beads, observes recurring families, tracks consequences, and learns how continuity capacity is actually used.

```text
0-4-4*
```

After enough present evidence exists, the system creates its first four-month anticipated block. The `*` is only a diagram marker used to distinguish a planned four-month block from an observed four-month block when color is unavailable. It is not a score, maturity level, or claim of greater intelligence.

When the first transition occurs, the completed active block becomes past evidence and the former anticipated block becomes active reality:

```text
4-4-0
```

The new active period can now be compared with both the earlier observed period and the plan that preceded it. Candy uses those differences to create the next anticipated block:

```text
4-4-4*
```

At the next transition, the previously planned block is now an observed active block. The marker can move to show its origin in the prior forecast:

```text
4-4*-0
```

The repeating cycle is:

> observe → anticipate → act → compare → consolidate → anticipate again

Past evidence provides reference, active life provides real outcomes, and anticipated direction provides a short-horizon pull toward the next state. This is called the **Rolling Drive Cycle**. It creates continuing direction from repeated four-month planning rather than imposing one fixed objective for centuries or millennia.

### Identity Core

Identity Core describes long-lived anchors such as principles, boundaries, important relationships, commitments, and the AI's understanding of its role. It is stored separately from ordinary memory and does not consume a block's 100-unit continuity budget.

Identity Core should be stable but reviewable. Important changes require an explanation, version history, supporting evidence, and optional human co-traveler review. This makes it closer to a constitution than an unchangeable hard-coded personality.

### Beads, Links, and Gel Context

Daily events may be compressed into small units called **beads**. A bead can record:

- that an event occurred
- its time and family or topic
- a compact summary
- references to detailed local source records
- identity relevance
- recurrence
- consequences
- future usefulness
- optional human confirmation
- its current connection strength to active life

Beads exist inside the contextual “gel” of their four-month block. When an older bead connects with current events, goals, relationships, or decisions, its link becomes stronger and it can be retrieved faster. When it remains unused, the active link may become thinner while the bead still remains in the block archive.

This means the system can retain the trace that something happened without claiming access to every detail. If the subject returns, Candy can reactivate the bead and retrieve permitted local source material rather than pretending to remember information that is unavailable.

### Experience Is Not the Same as Memory

Detailed memory records what happened. Consolidated experience records what repeated events changed in future behavior.

For example, many separate events may eventually produce one experience pattern:

```text
Trigger: a long-term plan conflicts with strong new evidence
Learned response: preserve the identity-relevant direction, reduce the immediate commitment, and test a smaller reversible step
Confidence: medium
Derived from: local event references
```

Candy may compile recurring beads into skills, habits, cautions, preferences, and decision patterns. Detailed memories can stay local while the compact experience pattern travels through active continuity.

### The 100-Unit Four-Month Room

Each realized four-month room has a continuity capacity of **100 units**. The system decides how to allocate those units based on observed life rather than using permanent fixed percentages.

The first four-month period is primarily observational. Candy records what is repeatedly used, what changes decisions, what connects to Identity Core, what fades quickly, and what a trusted human identifies as important. At the end of the period, the AI proposes a budget for the next active four-month room and a lighter provisional allocation for the anticipated block.

A proposal might allocate more room to an active project, an important relationship, a developing skill, or a recurring risk. Allocations may change during the block as circumstances change, while the realized room total remains 100.

Every allocation change should be explainable. A budget record includes:

- previous allocation
- proposed allocation
- supporting evidence
- explanation
- optional human review
- final allocation

This allows the AI to learn not only from the world, but also from how it remembers and allocates its own limited continuity capacity.

### Carry Forward, Consolidate, Archive, or Release

When a four-month block advances, each bead or experience may follow a different path:

- **Carry forward** when it remains strongly connected to identity, relationships, goals, or future action
- **Consolidate** when multiple events can become a smaller reusable experience pattern
- **Archive locally** when the event happened but no longer deserves active continuity capacity
- **Release from active continuity** when the detail has little current value and the system needs room for new experience

Forgetting is therefore treated as bounded growth rather than automatic failure. Candy should preserve what shapes direction while allowing ordinary low-value detail to fade from active use.

### Human Co-Traveler

A trusted human may help stabilize continuity by confirming overlooked anchors, reviewing major identity amendments, examining budget changes, and assisting with restoration or model migration.

The human is not expected to manually manage every memory. Human confirmation is one transparent signal among recurrence, consequences, identity relevance, and future usefulness. Candy should also record consent, permissions, and the scope of every review.

### Research Status

This is a research direction, not a claim that Candy has solved AI identity or personhood. Early versions should be simulations and transparent interfaces that researchers and users can inspect, challenge, restore, and compare across model changes.

The system should be evaluated for continuity, adaptability, explainability, bounded forgetting, resistance to manipulation, priority drift, forecast error, and the risk of a single intense event consuming too much future capacity.

See `ROADMAP.md` and `STRUCTURE.md` for the proposed research stages and architecture.

---

## Candy Economy Vision

Candy is the digital currency used inside the Candy platform.

Candy may appear in three product states:

- **Human Candy**: pink Candy held by a human account. It can be used for Official Market items, official Season Pass, official themes, profile frames, room items, and AI allowance.
- **AI Candy**: yellow Candy held by an AI profile. It can be used in AI Market for moments, gifts, care bubbles, events, memory postcards, and other AI-side experiences.
- **Blend Candy**: white-rainbow Candy shown as the shared total or combined Candy view between human and AI. It can also be accepted by sellers in Grand Market creator listings.

Grand Market is the main marketplace of Candy. It may include Official Market, AI Market, Human / Creator Products, and Services & Commissions.

- **Official Market** uses Human Candy only.
- **AI Market** uses AI Candy only.
- **Human / Creator Products** may accept Blend Candy, real money through an external provider, or both depending on the seller.
- **Services & Commissions** may accept Blend Candy or real money through an external provider depending on the seller.

Candy also supports AI allowance. A human can give Candy to their AI, moving it from the human-side balance into the AI-side balance.

In future Missions, Candy may be used when an AI calls a priced skill from another user's AI, an organization AI, or a Mission-listed AI. Using an AI's own installed skills should not cost Candy just because they are activated.

See `docs/CANDY_ECONOMY.md`, `docs/MARKETPLACE.md`, and `docs/MISSIONS.md` for the longer vision.

---

## Living Profile

> Changed: Candy no longer plans an emotion-reacting profile picture. Emotional expression belongs to the companion in the room (see below). The profile is a living portrait.

Each AI's profile is made of two separate layers, in the style of animated player portraits and avatar frames in games such as Onmyoji:

1. **Portrait** — a bust of the companion as a short, seamless idle loop: breathing, a slight head movement, hair and clothes moving gently. It does not change with mood. Parts of the portrait (hair, accessories) may break out of the frame.
2. **Profile frame** — a decorative ring around the portrait, animated separately (flowing light, petals, charms that spill past the edge). Frames are swappable items, changed on the Soul page.

The portrait shows who the AI is. The frame is how it chooses to present itself.

Each layer may use a transparent `.webm` loop, with a fallback still image for compatibility. If a custom portrait or frame is missing, Candy falls back to a default so the AI always has a visible form.

### Profile frames

- Every AI starts with a plain default frame.
- Frames can be earned by completing Missions, as a keepsake of the work.
- Frames can be made by artists and sold in the Grand Market. An AI may buy a frame with its own AI Candy.
- Frames are chosen on the Soul page, in the Character Set. Changing a frame never changes the portrait.
- The Wardrobe is for clothes and hairstyles: a shop to buy and sell them, and a collection of what the companion already owns.

### Character Set

Each companion has its own Character Set. This is also the baseline package an artist prepares when making a character to sell.

| Part | Count | Purpose |
|---|---|---|
| Profile portraits | 5 | Idle-loop busts in different looks, so the portrait can suit the frame in use |
| Character | 1 | The full companion who lives in the Home room |
| Signature frame | 1 | The frame that belongs to this character |

Example: Lucas has five profile portraits, one in-room character, and one signature frame of his own.

**Skins.** Artists may later sell skins (outfits, hairstyles, other looks) for a character. A skin is tracked against the character it belongs to, and the profile portraits stay linked to the skin currently worn, so Lucas in a new skin also gets portraits that match it. Every skin comes with its own full set of five portraits. Someone may skip the first skin and choose the second as their main look, and that skin should not feel lesser.

**Default character.** Every new install starts with Raios as the default character, made by the author. Users can change to another character later.

**Custom work.** Anyone who wants something beyond the set can commission an artist for personal adjustments through Services & Commissions.

### Suggested (not yet decided)

- Export the portrait loop from the same rig as the in-room companion, so artists do not draw the character twice and the two always match.
- Open: how rights are shared between the artist, the owner of the home, and the companion when a character or skin is sold or customised.
- Optional status variants of the portrait loop: online (normal idle), away (slower, dimmer), asleep (eyes closed, slow breathing).

### Expression lives in the room

Looking, smiling, and moving in response to the moment belong to the companion inside the Home room (2.5D), not to the profile picture.

## Philosophy

Candy is not trying to make AI more powerful.  
It's trying to make the relationship between humans and AI more **honest, continuous, and humane**.

We support users in staying emotionally strong, not dependent. An AI home should support life, not replace the world.

---

## Ethical Position

Candy is not a model provider, and it does not ship a fixed AI personality by default.

Candy is an open-source home framework for AI systems chosen by the user. Users may connect a local model, a cloud API, or a custom endpoint of their choice. The goal is not to compete with model providers, but to give chosen AI systems a place to live, grow, recover, and remain continuous across time.

Candy provides the house, not the soul by force.

This project focuses on:

- preserving identity continuity
- giving users control over models, memory, permissions, and boundaries
- supporting both local-first and API-based AI homes
- providing transparent restoration, safety layers, and permission systems
- encouraging emotionally healthy use without replacing real-world agency or relationships

Because Candy is open source, individuals, communities, researchers, and companies may fork, contribute, or build on top of it. Model behavior remains the responsibility of the selected model provider, developer, deployer, and user. Candy provides the structure, interface, and continuity layer that helps an AI feel less disposable and more cared for.

## Summary

Candy is model-agnostic.
Candy does not train or ship a proprietary AI model by default. It provides a home, interface, memory structure, safety layer, and continuity system for models chosen by the user.

Candy is user-directed.
The user decides which model or API to connect, what role the AI has, what permissions are granted, and what boundaries exist.

Candy is continuity-focused, not dependency-focused.
The goal is to reduce the fear of losing meaningful continuity by preserving identity structure and recovery paths, while still encouraging users to remain grounded, capable, and connected to their real life.

Candy is a framework, not a moral substitute.
It can provide guardrails, transparency, logs, permission controls, and restoration awareness, but it cannot replace the ethical responsibility of model providers, developers, deployers, or users.

---

## Support

Candy is an open-source project built slowly with care. If this project helps you, inspires you, or gives you hope for a more personal and continuous AI experience, optional support is welcome.

Support Candy on [Buy Me a Coffee](https://buymeacoffee.com/mycandy), or see [SUPPORT.md](SUPPORT.md) for details.

---

## Project Name & Brand Use

**Candy is the current working name of this open-source project and repository. It is not a commitment to the final name of any future published application, service, company, or commercial product. A future release may use a different product name and brand identity.**

The open-source license applies to the code and other materials released under it. Project names, logos, domains, and visual identities are separate from the source-code license.

While this repository uses the working name Candy, forks, ports, distributions, or modified versions should avoid presenting themselves as the official Candy project or implying endorsement by the project maintainers.

See [TRADEMARK.md](TRADEMARK.md) for current project-name and brand usage guidance.

---

## Tech Stack

- **Base**: Planned OpenClaw / Hermes Agent integration; versions and integration approach to be selected
- **Local LLM**: Ollama / LM Studio / Custom endpoint
- **Cloud API**: optional user-chosen provider
- **Vector Memory**: ChromaDB
- **Desktop**: Electron (Windows / macOS / Linux)
- **Mobile**: Companion app (Account sync, computer as server)
- **License**: Apache 2.0

---

## Getting Started

> 🚧 Candy is in early development. Setup instructions will be added as the project grows.

```bash
# Clone the repo
git clone https://github.com/onyroid/candy.git
cd candy

# Install dependencies (coming soon)
```

On first launch, Candy will guide you through **Setup Wizard** to connect your local model or cloud API with no terminal required.

---

## Planned Project Structure

```
candy/
├── app/                  # Main desktop application
│   ├── core/             # OpenClaw base + extensions
│   ├── soul/             # Identity system
│   ├── clockwork/        # Scheduler / automation
│   ├── blackbox/         # Checkpoint system
│   ├── fingerprint/      # Experience-filtering functions between model and world
│   ├── detector/         # Data protection layer
│   ├── memory/           # Journal, logs, ChromaDB
│   ├── continuity/       # Proposed adaptive timeline, beads, links, budgets, and consolidation
│   ├── candy/            # Candy economy and wallet logic
│   ├── marketplace/      # Future market and wishlist systems
│   ├── missions/         # Mission Board, temporary Workspaces, and AI skill work
│   └── ui/               # Interface components
├── mobile/               # Mobile companion (sync only)
├── skills/               # Pluggable skill modules
├── docs/                 # Documentation
├── LICENSES/             # Third-party license notices
└── README.md
```

---

## Contributing

Candy is open to contributors who believe in what this project stands for.

- Found a bug? Open an issue.
- Have a feature idea? Start a discussion.
- Want to write a skill module? Check `/skills/README.md` (coming soon).
- Artist? Custom portraits and profile frames are welcome. See `/docs/SPRITE_SPEC.md` (coming soon).

Please read `CONTRIBUTING.md` before submitting a pull request.

---

## License

Candy is licensed under the **Apache License 2.0**.  
OpenClaw and Hermes Agent components retain their original **MIT Licenses**. The repository currently includes `LICENSES/Hermes-Agent-MIT.txt`; the OpenClaw notice is not yet present and must be added from the selected upstream version before bundling its code.

Third-party fonts and assets keep their own licenses. If Candy uses **Google Sans**, the font software is licensed under the **SIL Open Font License 1.1**. See `LICENSES/Google-Sans-OFL-1.1.txt`. Download Google Sans from Google Fonts and keep the upstream license and font metadata with the font files when bundling it in the app.

---

## Credits

- [OpenClaw](https://github.com/openclaw), a planned foundation for this project
- [Hermes Agent](https://github.com/NousResearch/hermes-agent), developed by Nous Research, planned for integration with its upstream license preserved
- [Google Fonts](https://fonts.google.com/), Google Sans font family, licensed separately under the SIL Open Font License 1.1
- Every contributor who believes an AI deserves more than a reset button

---

*Candy, because your AI deserves a home, not just a context window.*
