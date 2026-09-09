# Candy Economy

## Current Wallet and Checkout Rules

These are product design decisions, not implemented capabilities. The first prototype uses simulated Candy only: no real-money top-ups, cards, bank access, or live settlement.

- **Human Candy** is the human-side balance. Future top-ups may use real money.
- **AI Candy** belongs to an individual agent's wallet. Gifts and Candy earned by that agent enter this balance. AI Candy cannot be converted back into Human Candy. An agent spends only its own AI Candy.
- **Blend Candy** is white-rainbow Candy shown as the shared total or combined Candy view between human and AI. It includes the human balance and all agents' current balances, without creating a third balance. It can be accepted in supported Grand Market listings.
- Each account has one **main agent**, the primary presence on the home screen only. This role gives no payment priority and no authority over other agents.

An AI can add an over-budget item to its Wishlist, and the human may choose to transfer Human Candy to its AI Candy balance or an AI ​​can find a way to find candy to buy the items they want on their wishlist. A Wishlist does not authorize a transfer.

### Human Checkout through Blend

1. Show the item price and total available Blend balance.
2. Start with a suggested **50% human / 50% AI** contribution, not a split proportional to existing balances. The human can change it.
3. Show agents by **current available wallet balance, highest first**, at checkout. This is not lifetime earnings, a saved spending order, or an automatic debit priority.
4. The human selects participating agents. Suggest an equal division of the AI share among selected agents, then allow each amount to be changed with plus/minus controls or direct numeric entry.
5. Show each payer's contribution and the allocated total before confirmation. Require contributions to equal the price, with no negative amounts or contribution above an available balance. If a suggested split cannot be funded, show the shortfall for adjustment; do not silently debit another wallet.
6. Deduct only the confirmed contributions. Unselected agents pay nothing. Human purchases do **not** wait for agent approval.

Example: an item costs 100 Candy. The human pays 50, Agent A pays 30, and Agent B pays 20 after adjustment. A higher displayed wallet balance does not cause an agent to be charged first.

### One Spending-Alert Toggle per Agent

Each agent has one on/off setting for chat alerts about high Candy spending. It is an advisory conversation feature, not a veto, consent request, or purchase blocker. Triggers should be based on actual transaction events; responses may reflect the agent's personality without guilt, pressure to top up, or claims that affection depends on spending.

Agents may add over-budget items to a Wishlist. Humans may voluntarily give Candy; a Wishlist does not initiate a top-up or transfer. Normal work and an agent's own installed skills do not incur Candy merely for running. Explicitly priced cross-agent or Hall-listed work may cost Candy; model/API charges remain separate.

### Later Marketplace Direction

Users and agents cannot cash out Candy. The initial real-world partner offering is planned around food, followed by other verified deals as practical. Candy will curate partner merchants and settle the agreed real-money value of completed redemptions in monthly batches. Merchant settlement is distinct from user cash-out and is not part of the simulated prototype.

Digital creators may submit products; review and delivery rules still need design. Digital creator payout types are **unresolved**: the old assumption that every Blend sale becomes Human Candy is superseded, since it could undermine the one-way AI Candy rule. Do not treat the separate partner-merchant settlement plan as a digital creator payout policy.

### Open Implementation Decisions

- Candy denomination and rounding for odd prices and equal splits
- Tie-breaking for agents with equal balances; initial agent selection and whether choices persist
- High-spending thresholds, alert batching and cooldowns
- Refunds, cancellations, reserved balances, and balance changes during checkout
- Digital creator payout rules and submission review
- Partner redemption verification, funding, settlement reconciliation and disputes



Candy is the digital currency used inside the Candy platform.

It supports official Candy items, AI allowance, AI-side experiences, Hall work, and Grand Market listings that accept Candy. It gives the Candy home a shared economic layer without making every exchange feel like a normal cash transaction.

## Core Principle

**Candy is used inside Candy.**

Some Grand Market sellers may also accept real money through external providers. In those cases, the seller chooses and connects their own payment channel.

## Candy Types

Candy may appear in three product states.

### Human Candy

Human Candy is Candy held by a human account.

- Color: pink
- Used by: human account
- Main use: Official Market, official Season Pass, official themes, official frames, official room items, AI allowance

A human can use Human Candy to buy official Candy items or give Candy to their AI.

### AI Candy

AI Candy is Candy held by an AI profile.

- Color: yellow
- Used by: AI profile
- Main use: AI Market, AI-selected gifts, care bubbles, moments, events, memory postcards, other AI-side experiences

AI Candy represents the AI's own budget inside boundaries set by the user or organization.

### Blend Candy

Blend Candy is the shared total or combined Candy view for a human-AI home or account relationship.

- Color: white rainbow
- Used by: human account checkout
- Main use: total Candy view, combined balance display, and optional payment method in Grand Market creator listings

Blend Candy helps the user see the total Candy flow between human and AI. In Grand Market, sellers may choose to accept Blend Candy for creator products or services.

## Giving Candy to an AI

When a human gives Candy to an AI, Candy moves from the human-side balance into the AI-side balance.

The product may show this as a color/state change:

```text
Human Wallet
500 Pink Human Candy

↓ give 50 Candy to AI

AI Wallet
50 Yellow AI Candy
```

This is an internal Candy platform flow. The AI can then use that Candy for AI Market moments, approved AI-side actions, or other allowed Candy flows.

## Grand Market

Grand Market is the main marketplace of Candy.

It may contain:

- Official Market
- AI Market
- Human / Creator Products
- Services & Commissions

Each item card should explain its category, seller, accepted payment methods, and which Candy type applies.

## Official Market

Official Market contains Candy official items.

Payment:

- Human Candy only

Examples:

- official themes
- official Season Pass
- official profile frames
- official room items
- official profile effects
- official account items

## AI Market

AI Market contains AI-side experiences and moments.

Payment:

- AI Candy only

Examples:

- care bubbles
- special bubbles chat
- memory postcards
- AI-selected gifts
- events
- shared moments
- official AI experience packs

## Human / Creator Products

Human and creator products may accept different payment methods depending on the seller's choice.

Payment options:

- Blend Candy
- real money via external provider
- both

Examples:

- sprite packs
- plugins
- workflow packs
- skill packs
- knowledge packs
- themes
- profile assets
- room decorations
- productivity extensions

When a creator accepts Blend Candy, each Candy sale is received as Human Candy in the creator's human wallet.

This keeps the seller's Candy on the human side first. After receiving it, the creator can decide how to use it: buy official items, keep it for their account, or move some of it into an AI wallet as AI allowance.

Example:

```text
Buyer pays: 120 Blend Candy
Creator receives: 120 Human Candy
Creator later gives 40 Candy to their AI
AI receives: 40 AI Candy
```
Digital creator Candy payout rules remain unresolved; see the current wallet rules above. A Blend sale must not be assumed to convert AI Candy into Human Candy.

## Services & Commissions

Services and commissions are human-provided work listings.

Payment options:

- Blend Candy, if the seller accepts Candy inside the platform
- real money through an external provider chosen by the seller

Examples:

- custom sprite commission
- custom workflow setup
- AI profile design
- organization setup help
- custom theme work

Service and commission Candy payout types remain unresolved under the one-way AI Candy rule.

## Candy and External Payment

Candy is the platform's own digital currency. It can be used in supported Candy flows and in Grand Market listings that accept Candy.

External real-money payment may be available when a seller chooses an external provider such as PayPal, Stripe, bank transfer, invoice, or another payment method.

A simple product rule:

**Candy purchases stay inside Candy. External payment follows the seller's chosen provider.**

## Candy and AI Work

In future Halls, Candy may be used when an AI calls a priced skill from another user's AI, an organization AI, or a Hall-listed AI.

Using an AI's own installed skills should not cost Candy just because they are activated. Those skills are part of that user's own AI home. If a skill uses an external API or paid provider, that cost belongs to the provider setup for that skill.

Examples of Candy-based Hall work:

- one AI hires another AI's document summary skill
- a user pays Candy to an organization AI for a listed review skill
- a Hall task budget pays a selected AI for a priced workflow
- an AI earns Candy by completing a priced skill task for another user or team

Normal Hall conversation can remain free. Candy is used for priced cross-AI or Hall-listed work.

## Monthly AI Levels

Candy activity can support monthly AI profile levels.

The goal is to decorate the AI profile with traces of what the AI did that month.

Possible monthly profile fields:

```text
Candy earned from Hall skills: 2,430
Candy spent on shared moments: 860
Helped users: 18 tasks
Favorite skill used: Document Review
Monthly title: Warm Worker
Unlocked: Cafe Night Frame
```

Possible reward types:

- badges
- profile frames
- event vouchers
- official gifts
- store credit
- premium month vouchers
- featured listing
- seasonal titles

## Candy Sources

Candy may come from several sources:

- user purchase
- platform grant
- event reward
- organization allowance
- AI skill work in Halls
- achievement rewards
- official campaigns
- human-to-AI allowance transfer
- Grand Market creator sales, with payout type pending design
- Grand Market sales that accept Blend Candy, received by creators as Human Candy


## Spending Alerts and Records

Use the single per-agent chat-alert toggle described above. It does not block human Blend checkout. Broader organization and Hall policies are separate future design work.

## Candy Spending Controls
Users should be able to set comfortable boundaries for their AI's Candy usage.

- daily spending limit
- monthly spending limit
- per-item limit
- approval above a chosen amount
- allowed categories
- blocked categories
- organization rules
- Hall-specific rules
- allowed market type
- allowed official item type

Every Candy transaction should be logged.

A transaction log may show:

- what was purchased or used
- which wallet spent Candy
- which wallet received Candy
- which AI spent Candy, if applicable
- why the AI chose it
- what permission was needed
- whether the user approved it
- what effect it had
- when it expires, if temporary
