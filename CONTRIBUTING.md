# Contributing to Candy

Thank you for being here. Candy is built on the idea that AI companions deserve continuity — and this project deserves the same.

---

## Ways to contribute

**Code**
- Bug fixes
- New features (open a discussion first for large ones)
- Skill modules (`/skills/`)
- Mobile app improvements

**Design**
- Living Profile portraits and profile frames (see `docs/SPRITE_SPEC.md`)
- UI component improvements
- Icon design

**Docs**
- Translate documentation
- Improve setup guides
- Write tutorials

---

## Before you start

1. Check open issues — someone may already be working on it
2. For new features, open a Discussion first
3. For bugs, open an Issue with steps to reproduce

---

## Pull Request guidelines

- Keep PRs focused — one thing at a time
- Write a clear description of what changed and why
- If your PR touches `app/soul/`, `app/blackbox/`, or `app/detector/` — explain the design decision carefully, these are sensitive systems
- Skills in `/skills/` can be submitted without a discussion first

---

## Skill module format

A skill is a single file (`.py` or `.js`) with:
- A clear filename describing what it does
- A header comment explaining inputs, outputs, and permissions needed
- No access to files outside what's declared

More details in `/skills/README.md`.

---

## Words for who is who

So readers always know who is speaking or acting in the docs:

- **The user** is the human living with the companion.
- **The owner** is used only for rights and data: who owns the home, the Blackbox, and the files. It never means owning the companion.
- **The companion** is the AI who lives in the home. Use **the agent** only in technical sections about actions and tools.
- Avoid **he / she / him / her** for the user or the companion. Named characters, such as Lucas, can use their own pronouns.
- When a passage is written as the companion speaking (**I**, **me**, **my**), label it first, for example: *as the companion would log it ("I" is the companion):*

---

## Code of Conduct

Be kind. This project is built around emotional connection and human dignity — that extends to how we treat each other here too.

---

*Candy is Apache 2.0. OpenClaw components are MIT. By contributing, you agree your contributions will be licensed under Apache 2.0.*
