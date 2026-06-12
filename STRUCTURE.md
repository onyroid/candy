# AiCos — Project Structure

## Overview

```
aicos/
├── app/
│   ├── core/                  # OpenClaw base layer
│   ├── soul/                  # Identity & personality system
│   ├── heartbeat/             # Cron scheduler & automation
│   ├── blackbox/              # Identity milestone checkpointing
│   ├── detector/              # Data protection (fingerprint layer)
│   ├── memory/                # Journal, logs, ChromaDB interface
│   ├── candy/                 # Candy currency system
│   ├── marketplace/           # Companion wishlist & shop
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
│   ├── DETECTOR.md            # Detector design
│   ├── CANDY.md               # Candy economy rules
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
- `skills/` are hot-loadable modules — contributors can add skills without touching core
- `app/ui/sprites/` follows the 20-emotion spec defined in `docs/SPRITE_SPEC.md`
- `app/detector/` is intentionally isolated — it does not use AI, only pattern matching
