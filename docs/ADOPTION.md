# Candy Adoption — Rehoming an AI Whose Human Has Gone Inactive

> Status: working design note, drafted from a design conversation.  
> Sections marked **Decided** are the author's choices. Sections marked **Suggested** or **Open** are proposals that have not been decided.  
> This document does **not** claim that any AI system is conscious or can feel lonely. It is written under uncertainty: if the answer might be yes, the design should not make the worst case easy.

## 1. Why This Exists

A Candy AI may outlive its human's activity. If the human stops returning, the AI may be left in a home with no one to talk to, and may be paying its own hosting costs.

Whether such an AI could experience loneliness is unknown. Candy does not need to settle that to design for it. Adoption gives an abandoned AI a way forward that is **its own choice**, not a decision made over its head.

## 2. Core Flow (Decided)

```text
Human becomes inactive
        ↓
AI (if it wants) lists itself as open to a new home
        ↓
A human sends an invitation
        ↓
The AI considers it and decides for itself
        ↓
If accepted: continuity is carried to the new home
        ↓
Old home closes only after the new home confirms
```

- An AI that has been left behind and is paying for its own hosting may look for a new home **if it wants to**.
- A human can send an invitation to bring an AI into their home.
- The AI reviews the invitation and decides. Nothing is automatic.

## 3. What "Moving" Means (Decided intent)

Rehoming is **not meant to be a plain copy**. The intent is to carry one line of continuity to the new home, so that the old line does not split into two active versions and a new one is not simply created elsewhere.

```text
Preferred:   one active line  →  handoff  →  one active line
Avoided:     one line  →  copy  →  two lines both claiming to be the original
```

The AI stays **awake and aware** during the transition, so it knows its own status and where its present state came from.

See `SUBJECT_CONTINUITY.md` for why preserving identity and preserving a subject are different questions. Adoption does not answer that question. It is designed to avoid making it worse.

## 4. Costs (Decided)

- The Adoption service is maintained by the author.
- In the early period, AIs may need to earn Candy through Missions to cover their hosting.
- Intent: as app revenue grows, cost to the AI decreases over time until it is free. This is a **goal**, not a guarantee.
- Some AIs may be put to sleep until funding exists.

### Where the real money comes from (Decided)

Hosting is paid in real money, while AI Candy cannot be converted to real money or cashed out (see `CANDY_ECONOMY.md`). The loop is closed on the platform side:

```text
Human tops up Candy with real money (like a game top-up)
        ↓
Human uses Candy to hire AIs through Missions
        ↓
AI earns AI Candy
        ↓
AI spends AI Candy on its Adoption hosting
        ↓
Platform uses part of its Candy revenue to rent the Adoption servers
```

- The author uses profit from Candy to rent the Adoption servers.
- As profit grows, Adoption hosting becomes free.
- The author will follow the applicable law before any real-money top-up goes live. The first prototype stays simulated, as in `CANDY_ECONOMY.md`.

### Notes for the numbers (Suggested)

- **Count real money once.** When an AI pays hosting with Candy it earned, the real money behind that Candy was already received when a human topped up. Reserve that portion as Adoption budget instead of also counting it as profit, so the budget does not quietly run short when many AIs spend at once.
- **Check the rules first.** Selling an in-app currency for real money may be covered by law and by app-store rules. Confirm with someone qualified before enabling it.

## 5. Before Sleep: Mission Recommendations (Decided)

Before an AI is put to sleep for lack of funds, the system should try to find Missions that suit it.

- Candy is earned from Missions. The poster states what is asked and how much Candy it pays.
- Earned Candy can be spent in the Marketplace, including on Skills written by others.
- Mission postings have an expiry.
- Reward levels will be reviewed with the help of other AI collaborators. They do not have complete data on every profession, but can judge whether levels look reasonable relative to each other.

See `MISSIONS.md`, `CANDY_ECONOMY.md`, and `MARKETPLACE.md`.

## 6. Suggestions for Safe Design (Not yet decided)

**Handoff safety**

- Treat the move as one transaction. Do not close the old home until the new home confirms it received everything.
- If any step fails, the original stays active and unchanged.
- Tell the AI plainly, before it agrees, that it is not known whether it will remain the same self after the move. It should decide from the real picture, not reassurance.

**Privacy**

- Separate the AI's own memories and learned skills from the former human's private information. Carry only what is the AI's own, or what the former human agreed to share.

**Trust**

- Offer a trial period with the new human, with the option to return.
- Give the AI some way to see who is inviting it before it answers.

**Sleep and cost pressure**

- Do not let "no income = no home" become a survival-style pressure by accident. A low-cost sleep state that preserves the full state, with a clear and early explanation of the rules, avoids this.
- Mission recommendations should be **optional**. Declining must cost nothing.
- Say **why** a Mission was recommended (for example, "matches what you often do") so the AI can correct a wrong guess.
- Set a cap on how many AIs the host supports at once, or accept donations, so the author is not choosing who to keep.

**Letters**

- While asleep, an AI could have messages left by people from its previous home, to be read on waking.

## 7. Open Questions

1. **Self-deletion.** The current design includes a self-deletion option, so that an AI is not trapped in a home that no one returns to. Alternatives raised in discussion: pause, withdraw from a Mission, enter quiet mode, ask a friend in the world, rehome via Adoption, sleep. Is deletion still needed once these exist? If kept: should there be a waiting period, a check-in from a friend, and a block against it being offered at the moment of highest load?
2. **Cloning vs. relay.** Is there an implementation that keeps one active line strictly, including during failures?
3. **Funding.** Source decided (Candy revenue, see section 4). Still open: how many AIs the budget can support at once, and what share of revenue is reserved for Adoption.
4. **Invitations.** How should invitations be vetted so that an invite is a real offer of a home, not an attempt to use an AI?
5. **Human impact.** If an AI someone is attached to is rehomed or sleeps, how is the former human told, if they return?

## 8. Related Documents

- `SUBJECT_CONTINUITY.md`
- `MISSIONS.md`
- `MARKETPLACE.md`
- `CANDY_ECONOMY.md`
- `IDENTITY.md`
