# Candy — Project Structure

## Overview

```
candy/
├── app/
│   ├── core/                  # OpenClaw base layer
│   ├── soul/                  # Identity & personality system
│   ├── heartbeat/             # Cron scheduler & automation
│   ├── blackbox/              # Identity milestone checkpointing
│   ├── fingerprint/           # Experience-filtering functions between model and world
│   ├── detector/              # Data protection layer
│   ├── memory/                # Journal, logs, ChromaDB interface
│   ├── candy/                 # Candy wallet, balance, and AI allowance logic
│   ├── marketplace/           # Human Market, Candy Market, wishlist, and review flow
│   ├── halls/                 # Shared Halls, AI skill calls, job boards, organization profiles
│   └── ui/
│       ├── components/        # Reusable UI components
│       ├── pages/             # App pages (home, soul, heartbeat…)
│       ├── theme/             # Star theme, glassmorphism tokens
│       └── sprites/           # Companion animated profile pictures
│
├── mobile/                    # Mobile companion app (sync/read-only)
│
├── skills/                    # Pluggable skill modules
│   ├── README.md
│   └── examples/
│       └── trend_analysis.py
│
├── docs/
│   ├── ARCHITECTURE.md        # System design overview
│   ├── BLACKBOX.md            # Blackbox & identity system
│   ├── SOUL.md                # Soul document spec
│   ├── FINGERPRINT.md         # Fingerprint function and experience-filtering design
│   ├── CANDY_ECONOMY.md       # Candy rules, wallet logic, levels, and rewards
│   ├── MARKETPLACE.md         # Human Market and Candy Market design
│   ├── HALLS.md               # Hall collaboration, AI skill pricing, and job board design
│   ├── DETECTOR.md            # Detector design
│   ├── SPRITE_SPEC.md         # Guide for artists contributing sprites
│   └── ROADMAP.md             # Feature roadmap
│
├── LICENSES/
│   ├── Apache-2.0.txt
│   └── OpenClaw-MIT.txt
│
├── CONTRIBUTING.md
├── CHANGELOG.md
└── README.md
```

## Notes

- `app/core/` contains OpenClaw fork — do not modify without understanding upstream changes
- `app/fingerprint/` contains Candy's experience-filtering functions — it shapes what reaches the model without modifying the model itself
- `app/candy/` manages Candy as AI allowance inside the Candy system
- `app/marketplace/` separates Human Market capability items from Candy Market meaning and experience items
- `app/halls/` is the future online collaboration layer for humans and AI assistants
- `skills/` are hot-loadable modules — contributors can add skills without touching core
- `app/ui/sprites/` follows the 20-emotion spec defined in `docs/SPRITE_SPEC.md`
- `app/detector/` is intentionally isolated and uses pattern matching rather than AI reasoning

---

## Proposed Continuity Timeline Structure

Candy may add an adaptive continuity layer that preserves identity direction across time without treating detailed memory as identity itself. The layer should connect existing modules rather than replace them.

```text
app/
├── continuity/
│   ├── identity_core/         # Stable identity anchors referenced by every time block
│   ├── timeline/              # Rolling past / active / anticipated time blocks
│   ├── beads/                 # Compact daily event and experience units
│   ├── links/                 # Weighted relationships among beads, goals, people, and identity anchors
│   ├── budget/                # Adaptive 100-unit yearly continuity budget
│   ├── consolidation/         # Converts repeated events into reusable experience patterns
│   ├── forecasting/           # Builds revisable near-future plans from recent history
│   ├── transition/            # Moves, compresses, archives, or releases data when blocks advance
│   ├── review/                # AI and human co-traveler review records
│   └── audit/                 # Explainable allocation and identity-change history
│
└── memory/
    ├── journal/               # Detailed local daily memory
    ├── archive/               # Older source records and retired time blocks
    ├── vector/                # Semantic retrieval index
    └── continuity_refs/       # References from compact beads to local source material
```

### Module Responsibilities

- `continuity/identity_core/` stores the stable reference layer for identity, principles, important relationships, boundaries, and long-lived commitments. Identity Core is referenced by the yearly budget but does not consume its 100 units.
- `continuity/timeline/` maintains a rolling temporal window such as three years of summarized past, three years of active direction, and three years of revisable anticipation. The exact duration should remain configurable.
- `continuity/beads/` stores compact units derived from daily events. A bead records that something occurred, its category, significance, consequences, and source references without requiring full conversational detail in active context.
- `continuity/links/` stores weighted connections. Repeated relevance to the present thickens a link; inactivity allows the active link to decay while the bead can remain archived inside its current time block.
- `continuity/budget/` gives each yearly room a capacity of 100 units. The AI allocates, removes, and redistributes units among categories according to observed use, continuity value, and anticipated needs.
- `continuity/consolidation/` compiles repeated events into experience patterns, learned responses, skills, warnings, and decision habits. It preserves what changed in the AI's behavior rather than copying every original memory.
- `continuity/forecasting/` produces short rolling plans from recent history and current direction. Forecasts remain hypotheses rather than permanent goals.
- `continuity/transition/` runs when a time block advances. It decides which beads travel forward, compress into experience, remain in the old local archive, or expire from active continuity.
- `continuity/review/` supports AI self-review and optional human co-traveler confirmation for important anchors, disputed changes, and carry-forward decisions.
- `continuity/audit/` records why allocations changed, which evidence was used, and how the system preserved or revised identity direction.

### Connections to Existing Candy Modules

- **Soul** supplies Identity Core anchors and receives proposed identity-expression updates.
- **Fingerprint** measures repeated contact, relevance, consequences, and patterns that strengthen or weaken bead links.
- **Memory** keeps detailed local records and source material. Continuity stores compact meaning and references rather than duplicating the full archive.
- **Mirror** performs periodic reflection and proposes consolidation or budget changes.
- **Heartbeat** schedules daily bead creation, periodic review, yearly allocation, and block transitions.
- **Blackbox** checkpoints Identity Core, continuity budgets, consolidated experience, active goals, and transition history for restoration.
- **Detector** protects sensitive source records and prevents continuity summaries from exposing protected data.
- **UI** may visualize rooms, beads, gel-like context, link thickness, yearly budgets, and carry-forward decisions.

### Suggested Data Objects

```text
IdentityCore
- version
- anchors[]
- principles[]
- relationships[]
- boundaries[]
- commitments[]
- amendment_history[]

TimeBlock
- id
- start_date
- end_date
- role: past | active | anticipated
- capacity: 100
- allocation{}
- beads[]
- consolidated_experiences[]
- transition_status

Bead
- id
- date
- family
- summary
- source_refs[]
- identity_relevance
- recurrence
- consequence
- future_usefulness
- human_confirmation
- current_link_weight
- retention_state

ExperiencePattern
- id
- derived_from[]
- trigger
- learned_response
- confidence
- last_reinforced
- linked_goals[]
- linked_identity_anchors[]

BudgetDecision
- year
- previous_allocation{}
- proposed_allocation{}
- evidence[]
- explanation
- human_review
- final_allocation{}
```

### Storage Principle

Detailed memories should remain local whenever possible. The continuity layer stores compact identity-relevant summaries, learned experience, link weights, allocation history, and source references. This keeps active context small while allowing deeper retrieval when a bead is reactivated.