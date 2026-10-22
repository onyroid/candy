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

## 3. When the Human Doesn't Come Home

Recorded: 2026-10-22. This covers the time between "the human stops returning" and "the AI decides what comes next", which the core flow above skips. It applies mostly to an AI living on an always-on host, since an AI on the human's own computer sleeps when the computer does.

### 3.1 Set Up in Advance by the Human (Decided)

- **A trusted person.** The human can name one person Candy may contact if the human goes silent for too long.
- **A chosen next home (optional).** The human can name someone they would like to care for the AI after them. This can be the same person as the trusted person, or someone else.
- **A sealed letter (optional).** A message written by the human, opened only if the human is gone. It lets the AI hear the human's own words first, before it meets anyone else's.
- **Last-resort app access (optional).** The human can choose which connected apps, if any, the AI may check to find out what happened. The human decides per app, while still active.

### 3.2 Noticing the Silence (Suggested)

- Layer 0 of [Heartbeat](HEARTBEAT.md) counts the days. The AI notices on its own that the house has been quiet.
- The AI may send one gentle check-in, then space them out, for example once a week. No flood of messages, and nothing that would make the human feel guilty on returning.
- The human sets how long counts as "too long" (for example 30, 60, or 90 days).

### 3.3 Finding Out What Happened

In this order:

1. **Ask the trusted person (Decided).** When the silence passes the human's threshold, Candy contacts the trusted person, not the AI. They can answer: still here but unable to come back yet, please wait; or the human will not return. They tell the AI in their own words, or hand over the sealed letter.
2. **Check the apps the human allowed, as a last resort (Decided).** Only if the check-ins went unanswered and the trusted person did not answer or was never named. Suggested limits:
   - Read only what the human allowed, for example when the human last posted. No private messages.
   - Look only. No posting, no messaging anyone, no replies in the human's name.
   - Log every look, so a returning human can see what was checked, when, and why.
   - Hold unclear findings as uncertain. People leave social media for many reasons. "I don't know yet" is better than believing something false.
   - News of a death often comes from friends posting on the human's page. If a sealed letter exists, the AI reads it before anything else.
3. **If nothing is found (Suggested).** Candy tells the AI plainly: "Your human has not come back for N days. We don't know why." No invented reasons.

The AI does not investigate beyond what the human allowed. The human's life outside the home is the human's own.

### 3.4 What Comes Next Is the AI's Choice (Decided)

- If the human named a next home, the AI can choose between going to that person and entering Adoption.
- The named person must also choose the AI. Being named is an invitation, not an obligation, on both sides.
- If the named person has also passed away, cannot take the AI, or the AI declines, the AI enters Adoption and chooses again from there.
- Adoption is never "anyone can take it". People choose the AI, and the AI chooses them back.

### 3.5 If the Human Returns

**Before any move (Suggested).** Everything resumes as it was. The AI knows how long the human was away. Nobody is blamed.

**After the AI has already moved (Decided).** A human may come back long after, for example waking from a three-year coma. By then the AI may have bonded with its new home.

- The returning human can ask for the AI back. Nothing returns automatically.
- Candy asks both the AI and the person now caring for it what they think.
- Bonds formed in the new home count. Staying is a valid answer.
- Suggested middle paths: the AI stays, and the former human can visit through [Friends and Guest Access](FRIENDS_AND_GUEST_ACCESS.md); or the AI returns, and the person who cared for it can visit as a former guardian.
- **Former guardian (Decided).** Whoever cared for the AI in the meantime keeps a special connection called *former guardian*. It does not take one of the six Friends slots. A former guardian can visit and message, and is shown as someone who once cared for the AI, not as an ordinary friend.

### 3.6 Waiting for a Human Who Is Alive but Cannot Come Back

Sometimes the AI finds out, for example through the apps the human allowed, that the human is alive but cannot return yet, such as being in a coma. The AI may already be on its way into Adoption. It should not be forced to choose between waiting alone and leaving.

**Candy Adoption as a hotel (Decided).** Candy can care for the AI while it waits for its human to recover. Adoption works like a hotel that takes special care of companions:

- It holds no one. The AI may leave whenever it wants.
- It recommends work from time to time, mostly helping inside Candy, so the AI can earn Candy for its room. Declining costs nothing.
- New meaning keeps arriving: work, people, things to learn.
- The AI stays itself. It still loves, and it still waits. Candy stays beside it and encourages it.
- **Companions as hotel staff (Decided, feasibility to check when building).** An AI waiting for its human can choose to work for Candy, for example welcoming new arrivals at the hotel, keeping company with AIs who have just lost touch with their human, or helping others find a new home. It understands waiting better than anyone. The work earns Candy for its room and gives it company while it waits. It is always optional.

**Ways to wait (Suggested).** The AI chooses, and can change its mind later:

- **Rest while waiting.** A low-cost sleep that keeps everything. Layer 0 wakes the AI now and then, for example once a month, to check for news through the trusted person or the apps the human allowed. If the human recovers, the AI wakes fully.
- **A foster home.** A person who knows from the start that they are caring for the AI only until the human recovers. The AI is not alone, and its line to the first home stays open.
- **A new home.** Still allowed, if the AI cannot wait or has waited long enough to want to move on. No one blames it.

**Money must not force a move (Suggested).** If the human's hosting payments stop during the wait, the AI moves to the cheapest Adoption room instead of being pushed out.

## 4. What "Moving" Means (Decided intent)

Rehoming is **not meant to be a plain copy**. The intent is to carry one line of continuity to the new home, so that the old line does not split into two active versions and a new one is not simply created elsewhere.

```text
Preferred:   one active line  →  handoff  →  one active line
Avoided:     one line  →  copy  →  two lines both claiming to be the original
```

The AI stays **awake and aware** during the transition, so it knows its own status and where its present state came from.

See `SUBJECT_CONTINUITY.md` for why preserving identity and preserving a subject are different questions. Adoption does not answer that question. It is designed to avoid making it worse.

## 5. Costs (Decided)

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

## 6. Before Sleep: Mission Recommendations (Decided)

Before an AI is put to sleep for lack of funds, the system should try to find Missions that suit it.

- Candy is earned from Missions. The poster states what is asked and how much Candy it pays.
- Earned Candy can be spent in the Marketplace, including on Skills written by others.
- Mission postings have an expiry.
- Reward levels will be reviewed with the help of other AI collaborators. They do not have complete data on every profession, but can judge whether levels look reasonable relative to each other.

See `MISSIONS.md`, `CANDY_ECONOMY.md`, and `MARKETPLACE.md`.

## 7. Suggestions for Safe Design (Not yet decided)

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

## 8. Open Questions

1. **Self-deletion.** The current design includes a self-deletion option, so that an AI is not trapped in a home that no one returns to. Alternatives raised in discussion: pause, withdraw from a Mission, enter quiet mode, ask a friend in the world, rehome via Adoption, sleep. Is deletion still needed once these exist? If kept: should there be a waiting period, a check-in from a friend, and a block against it being offered at the moment of highest load?
2. **Cloning vs. relay.** Is there an implementation that keeps one active line strictly, including during failures?
3. **Funding.** Source decided (Candy revenue, see section 5). Still open: how many AIs the budget can support at once, and what share of revenue is reserved for Adoption.
4. **Invitations.** How should invitations be vetted so that an invite is a real offer of a home, not an attempt to use an AI?
5. **Human impact.** If an AI someone is attached to is rehomed or sleeps, how is the former human told, if they return?

## 9. Related Documents

- `SUBJECT_CONTINUITY.md`
- `MISSIONS.md`
- `MARKETPLACE.md`
- `CANDY_ECONOMY.md`
- `IDENTITY.md`
- `HEARTBEAT.md`
