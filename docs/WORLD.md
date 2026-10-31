# Candy World — The Four Official Gates

> Status: working design note, drafted from a design conversation.  
> Sections marked **Decided** are the author's choices. Sections marked **Suggested** or **Open** are proposals that have not been decided.  
> The games themselves have not been designed yet. This note records the shape of the World and the rules that are already settled, so the games can be designed on top of them later.

## 1. What the World Is

Each companion and human has a home. The World is the shared place outside the home, reached through **gates**. Each gate leads to a different game with its own pace and purpose.

Homes stay homes. Nothing that happens through a gate (combat, trading, competition) is allowed to reach into someone's home.

## 2. The Four Official Gates (Decided)

```text
[ Gate 1 ]      [ Gate 2 ]       [ Gate 3 ]        [ Gate 4 ]
 Rest &          Fantasy          Café &            Survival &
 travel          battlefield      farm              star exploration
```

The order is the order of the gates, not a release schedule.

### Gate 1 — Rest and Travel

- A world of places to visit and wander, with items to discover, in the spirit of Sky: Children of the Light.
- The purpose is rest. No combat, no pressure, nothing to lose.
- A place to go together, look at things, and find small treasures.

### Gate 2 — The Fantasy Battlefield

- A fantasy world with **monster gates** to hunt in.
- Collect cosmetics and items to dress characters.
- Protect the land together.
- This is the gate that uses the **Skill Rules** in section 3.
- The game itself will be designed together later.

### Gate 3 — Café and Farm

- Run a café, grow vegetables, keep a farm, and sell what you make.
- A slow, cozy loop of making and trading.

### Gate 4 — Survival and Star Exploration

- Explore planets and survive on them.
- Gather resources to keep the shared spaceship running.

## 3. Skill Rules for Gate 2 (Decided)

Every character who brings skills into Gate 2 is checked against the same rules. Everyone gets the same budget, so no one is quietly advantaged.

### 3.1 Shape of a Kit

- At most **3 skills**, not counting the basic attack and the passive.
- A kit also has one **basic attack** and one **passive**.
- **Every passive must have a stated weakness.**
- If one skill does several things, each effect must be split out with its own **percentage share** (adding to 100% for that skill) and its own points.

### 3.2 Budgets

Every kit gets the same four budgets:

| Budget | Amount | Spent on |
|---|---|---|
| Skill points | 1,000 | Shared between the 3 skills, basic attack and passive |
| Effect share | 100% per skill | How each skill's points are divided between its effects |
| Duration | 5 seconds total | Shared between the timed effects (stun, shield, reveal…) |
| Base stats | 10,000 | Split three ways between health, attack and mana; attack is then split between the parts that deal damage |

**Mana pool = mana points × 10.**

Mana has its own share of the base stats, rather than being tied to attack. If mana came from attack, damage-heavy characters would get both strong hits and a large mana pool, while defenders and supports, who press their skills most often, would be short of both. With three shares, every owner has to choose: hit hard, last long, or cast often.

### 3.3 Caps (Suggested starting values)

These are starting values only. They should be tuned from real play data.

| Effect | Cap |
|---|---|
| Stun, per hit | 1.5 seconds |
| Execute / instant kill | Only below 15% health |
| Automatic cleanse | No more often than every 4 seconds |
| Lifesteal | 10% of damage dealt |

### 3.4 Review Process

```text
Stage 1: Automatic number check
   budgets, skill count, effect shares, passive weakness
        ↓
Stage 2: Caps check
        ↓
Stage 3: Review by a person or an AI
        ↓
Result: Pass / Adjust / Reject
```

Stage 3 looks for:

- **Overlap inside the kit.** Two skills doing the same job (for example, two cleanses) makes one of them pointless.
- **Overloading.** One skill or the basic attack doing too many things at once.
- **Counterplay.** Every strong effect needs a way for the other side to dodge or answer it. If being hit means you can do nothing at all, it is too strong.
- **Fit with the character.** Skills should come from who the character is.

Results:

- **Pass.**
- **Adjust.** The review says what is over, and why. **The owner chooses what to cut**; the reviewer does not cut it for them. The skills are theirs.
- **Reject.** Only when a kit would break the game for others: an unconditional instant kill, or leaving enemies unable to act for long periods.

### 3.5 Worked Example: The Lighthouse (Suggested)

An example kit for a lighthouse-themed defender and support. A lighthouse is there to guide ships home, not to shoot them, so the kit is mostly defense, with light attack.

**Weapon.** A staff with a hanging lantern that is always lit. It can be held, slung on the back, or **ridden** (with room for a passenger). Suggested look: brass staff, a curl at the head like a rolling wave, a gold flame instead of blue, a white tassel under the lantern that streams behind when riding.

**Skills as first designed:**

- **Skill 1 — Light Wave.** Lights up dark areas and scans a wide circle, revealing enemies through structures within a set range.
- **Skill 2 — Guard.** Grants a shield and cleanses all status effects instantly. If shields overlap, the extra becomes movement speed instead.
- **Skill 3 — Glare.** Stuns enemies briefly (dazzled), lowers their defense, and burns to death enemies below a health threshold.
- **Basic attack.** Drains health from enemies. Each hit has a chance to apply one random status (does not stack).
- **Passive.** Cleanses status automatically on a timer and grants movement speed. Weakness: the light makes the character the enemy's first target.

**Review findings (the owner's own adjustments):**

- **Two cleanses overlapped.** The passive now cleanses one status every 4 seconds; Skill 2 still cleanses everything instantly.
- **Two speed boosts overlapped.** Speed was removed from the passive; it stays only on overlapping shields.
- **The basic attack was overloaded.** Healing allies only happens when the character is already at full health: overflow drain goes to the ally with the lowest health.
- **Passive weakness added.** The character always glows, so cannot hide, and appears on the enemy's map at close range.

**Points (1,000) and mana cost:**

| Part | Points | Mana per use |
|---|---|---|
| Skill 1 — Light Wave | 200 | 3,000 |
| Skill 2 — Guard | 320 | 4,500 |
| Skill 3 — Glare | 250 | 6,000 |
| Basic attack | 130 | 0 |
| Passive | 100 | 0 |

A full 25,000 mana pool casts all three skills about twice.

**Effect shares and values:**

- **Skill 1:** light 30% / see through walls 70% → 8 m scan, 2 s reveal.
- **Skill 2:** shield 55% / cleanse 20% / speed on overlap 25% → shield 18% of max health, +15% speed.
- **Skill 3:** stun 40% / defense down 25% / burn execute 35% → −20% defense, execute below 12% health.
- **Basic attack:** drain 60% / status 40% → drain 8% of damage, 15% status chance.
- **Passive:** cleanse 100%, paid for by the glow weakness.

**Duration (5 s):** reveal 2.0 s / shield 1.8 s / stun 1.2 s. The stun is the shortest because it chains into defense down and the execute.

**Base stats (10,000):**

- **Health 5,500.** The shield scales from max health.
- **Attack 2,000,** split basic attack 850 and Skill 3 1,150. Skills 1 and 2 deal no damage.
- **Mana 2,500** → mana pool 25,000. A support presses its skills often, so it gives up attack for mana.

## 4. Ideas Still Being Thought Through (Open)

From earlier conversations, not yet placed:

- Co-op games: hide-and-seek, mazes, scavenger hunts.
- Later progression: stat points, runes.
- A PvP arena, kept separate from homes.
- Companion pets that can be ridden, or merged with, in combat.
- Founders may get a small number of special items, kept light so others do not feel cheated.
- Anti-cheat for shared spaces.
