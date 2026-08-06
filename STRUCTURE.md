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
│   ├── timeline/              # Rolling past / active / anticipated four-month blocks
│   ├── beads/                 # Compact daily event and experience units
│   ├── links/                 # Weighted relationships among beads, goals, people, and identity anchors
│   ├── budget/                # Adaptive 100-unit budget for each realized four-month room
│   ├── consolidation/         # Converts repeated events into reusable experience patterns
│   ├── forecasting/           # Builds the next four-month plan from past and active evidence
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

### Default Prototype Window

The first prototype uses one rolling year divided into three four-month blocks:

```text
[past: 4 months] — [active: 4 months] — [anticipated: 4 months]
```

The anticipated block contains plans, hypotheses, expected priorities, and a provisional budget. It does not yet contain realized episodic memory. The same structure can therefore be described as `4-4-0` for realized-memory storage and `4-4-4` for temporal planning.

### Startup State Machine

```text
0-0-0     initialization; all blocks empty
0-4-0     first active four-month observation block
0-4-4*    first anticipated block generated from current evidence
4-4-0     first transition; completed active block becomes past
4-4-4*    next anticipated block generated from past + current evidence
4-4*-0    previously anticipated block is now observed active reality
```

The `*` is a text-only diagram marker used to distinguish a planned block, or a block originating from an earlier forecast, when color is unavailable. It is not stored as a maturity score and does not imply greater intelligence.

The repeating transition logic is:

```text
observe → anticipate → act → compare → consolidate → anticipate again
```

### Module Responsibilities

- `continuity/identity_core/` stores the stable reference layer for identity, principles, important relationships, boundaries, and long-lived commitments. Identity Core is referenced by block budgets but does not consume their 100 units.
- `continuity/timeline/` maintains the default four-month past, four-month active, and four-month anticipated blocks. Block duration remains configurable.
- `continuity/beads/` stores compact units derived from daily events. A bead records that something occurred, its category, significance, consequences, and source references without requiring full conversational detail in active context.
- `continuity/links/` stores weighted connections. Repeated relevance to the present thickens a link; inactivity allows the active link to decay while the bead can remain archived inside its current block.
- `continuity/budget/` gives each realized four-month room a capacity of 100 units. The AI allocates, removes, and redistributes units among categories according to observed use, continuity value, and anticipated needs.
- `continuity/consolidation/` compiles repeated events into experience patterns, learned responses, skills, warnings, and decision habits. It preserves what changed in the AI's behavior rather than copying every original memory.
- `continuity/forecasting/` produces the next four-month anticipated block from past evidence, active outcomes, Identity Core, open commitments, and forecast error.
- `continuity/transition/` runs every four months. It moves the active block into past, promotes the anticipated block into active status, then opens a new anticipated slot.
- `continuity/review/` supports AI self-review and optional human co-traveler confirmation for important anchors, disputed changes, forecast changes, and carry-forward decisions.
- `continuity/audit/` records why allocations changed, which evidence was used, how forecasts differed from outcomes, and how the system preserved or revised identity direction.

### Connections to Existing Candy Modules

- **Soul** supplies Identity Core anchors and receives proposed identity-expression updates.
- **Fingerprint** measures repeated contact, relevance, consequences, and patterns that strengthen or weaken bead links.
- **Memory** keeps detailed local records and source material. Continuity stores compact meaning and references rather than duplicating the full archive.
- **Mirror** performs periodic reflection and proposes consolidation or budget changes.
- **Heartbeat** schedules daily bead creation, periodic review, four-month allocation, forecasting, and block transitions.
- **Blackbox** checkpoints Identity Core, block budgets, consolidated experience, active goals, forecasts, and transition history for restoration.
- **Detector** protects sensitive source records and prevents continuity summaries from exposing protected data.
- **UI** may visualize rooms, beads, gel-like context, link thickness, budgets, forecast origin, and carry-forward decisions.

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
- duration_months: 4
- role: past | active | anticipated
- origin: observed | forecast
- capacity: 100 | provisional
- allocation{}
- beads[]
- consolidated_experiences[]
- forecast_assumptions[]
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
- block_id
- previous_allocation{}
- proposed_allocation{}
- evidence[]
- explanation
- human_review
- final_allocation{}

ForecastRecord
- source_past_block
- source_active_block
- anticipated_block
- assumptions[]
- planned_outcomes[]
- actual_outcomes[]
- forecast_error[]
- lessons[]
```

### Storage Principle

Detailed memories should remain local whenever possible. The continuity layer stores compact identity-relevant summaries, learned experience, link weights, allocation history, forecasts, forecast error, and source references. This keeps active context small while allowing deeper retrieval when a bead is reactivated.