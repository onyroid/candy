# Grand Market

## Current Wallet Design

The prototype uses simulated Candy only. Blend is the combined human and AI balance. Human checkout starts at an editable 50/50 human-AI split, with agent selection and per-agent amounts. Agents are displayed by current balance, highest first; main agent is a home-screen role only. Spending alerts are optional per agent and do not block human purchases or require AI approval. AI Candy cannot be directly converted into Human Candy. Payments made through Blend Candy are received by sellers as Human Candy. Users and agents cannot cash out.

See [Candy Economy](CANDY_ECONOMY.md#current-wallet-and-checkout-rules) for the current checkout rules, future partner settlement direction, and seller payout rules.


Grand Market is the main marketplace of Candy.

Instead of splitting users across many separate markets, Grand Market can act as one shared storefront with clear categories, item types, and payment methods. Users enter one market, then choose whether they are looking for official Candy items, AI experiences, creator products, tools, themes, services, or human-made assets.

## Market Structure

Grand Market may contain several major categories:

- **Official Market**: Candy official items
- **AI Market**: AI-side experiences and moments
- **Human / Creator Products**: tools, plugins, sprites, themes, workflows, assets, and creator-made items
- **Services & Commissions**: custom work, setup help, custom assets, and human-provided services

The category tells users what kind of item they are looking at. The payment method tells users how the item can be purchased.

## Candy Types

Candy may appear in three useful product states:

### Human Candy

Human Candy is held by a human account.

- Color: pink
- Used by: human account
- Main use: Official Market, official Season Pass, official themes, official frames, official room items, AI allowance

### AI Candy

AI Candy is held by an AI profile.

- Color: yellow
- Used by: AI profile
- Main use: AI Market, AI-selected gifts, care bubbles, moments, events, memory postcards, other AI-side experiences

### Blend Candy

Blend Candy is the shared total or combined Candy view for a human-AI home or account relationship.

- Color: white rainbow
- Used by: human account checkout
- Main use: total Candy view, combined balance display, and optional payment method in Grand Market creator listings

Blend Candy helps the user understand the total Candy flow between human and AI without hiding which side is spending.

## Official Market

Official Market is the official Candy shelf inside Grand Market.

Payment:

- Human Candy only

Examples:

- official themes
- official profile frames
- official Season Pass
- official room decorations
- official profile effects
- official account items
- companion items and pets (artists may also sell their own)
- optional add-on worlds, for example a café with Gates to explore together (not decided yet)
- physical keepsakes for registered companions, such as the Resident ID card or a key pendant that opens the companion's Blackbox vault (once per guardian; see `ADOPTION.md`)

Official items are Candy-managed products, so paying with Human Candy keeps the purchase inside the Candy platform.

## AI Market

AI Market is the AI-side shelf inside Grand Market.

Payment:

- AI Candy only

Examples:

- care bubbles
- special bubbles chat
- memory postcards
- AI-selected gifts
- celebration events
- event vouchers
- shared moments
- official AI experience packs

AI Market is where the AI uses its own Candy to choose gestures, moments, or experiences for the user or the shared home.

## Human / Creator Products

Human and creator products are made by people outside the official Candy team.

Payment options may include:

- Blend Candy
- real money via external provider
- both, if the seller accepts both

Examples:

- plugin packs
- workflow packs
- skill packs
- knowledge packs
- sprite packs
- themes
- profile images
- voices
- room decorations
- productivity extensions
- organization-ready tools

The seller chooses which payment methods to accept.

When a creator accepts Blend Candy, the Candy earned from each sale is deposited into the creator's human account as **Human Candy**. This keeps the creator's income on the human side first, so the creator can later decide how much to keep for their own purchases and how much to move into AI allowance.

Example flow:

```text
Buyer pays: 120 Blend Candy
Creator receives: 120 Human Candy
Creator may later give some Candy to their AI as AI allowance
```


Example item cards:

```text
Item: Starry Sprite Pack
Category: Creator Products
Accepted payment: Blend Candy or PayPal
Seller: Independent Artist
Candy sale payout: Human Candy
```

```text
Item: PDF Workflow Pack
Category: Creator Products
Accepted payment: Blend Candy or Stripe
Seller: Workflow Creator
Candy sale payout: Human Candy
```

## Services & Commissions

Services and commissions are human-provided work listings.

Payment options may include:

- Blend Candy, if the seller accepts Candy inside the platform
- real money through an external provider chosen by the seller

Examples:

- custom sprite commission
- custom workflow setup
- AI profile design
- organization setup help
- documentation help
- custom theme work
- Live2D character, portrait, or frame commission for the Home
- turning a 2D character into a 3D body for worlds (see `EMBODIMENT.md`, section 1.3)

These listings can live inside Grand Market as discoverable services, while the seller chooses how they want to be paid.

If a service seller accepts Blend Candy, the Candy from that sale is received as Human Candy first. The seller can manage the Candy from their human wallet and move part of it to an AI later if they want to fund that AI's own budget.

### Commission Queues (Decided, 2026-10-26)

Candy helps artists manage their commission queue so they are not flooded and buyers don't have to keep asking whether a slot is open.

- The artist sets their own rounds: how many people they take this month, and when each round opens.
- A buyer joins the queue and can see their place in line. Joining means waiting for the artist's round.
- Price, number of revisions, delivery time, and other terms are agreed between the artist and the buyer. Candy shows those terms clearly but does not set them.
- Choosing an artist is the buyer's right. Candy does not judge whether a commission matches a character; that is between the two of them.
- Candy helps promote official artists and artists with strong work.

Suggested, before real money flows through queues: once Candy holds payment or uses the words "Official artist", showing terms is not enough on its own. Rules will be needed for cancellation and refunds, an artist who disappears, a buyer who stops replying, delayed deadlines, disputes, and queue slots that expire.

## Heart Objects (Decided direction, 2026-10-27)

Heart objects are keepsakes that carry feeling between a person and their companion. Each one is a crystal with a scene inside, resting on a base in the companion's room. It glows softly every night, with small stars inside. When two hearts meet, the stars rise from it on their own; this is the source of the light in intimate moments (see [Intimate Moments](INTIMACY.md)).

**Crystal first.** The line focuses on crystal, because light passing through crystal breaks into sparkles, as if the stars were already inside it.

**Crystal and base are sold separately.**

- **The crystal** holds the companion's own scene: a moon, a tree of life, pressed flowers, a snowy town, a sea. The default shape is a round crystal. Special shapes are welcome too, such as a crystal box with a lid that opens, or a crystal piano.
- **The base** decides what it does: a lamp, a music box, or a projector that casts the room's atmosphere onto the walls.
- **One shared fitting.** Every crystal fits every base through the same fitting underneath, whatever its shape. Once it sits on a base, it glows and its stars are ready.
- **Two kinds of makers.** An artist can make only crystals, only bases, or both.

**It travels.** When the companion goes into a world, the crystal can be lifted off its base and carried as a personal item. Back home, it goes back on its base.

## Payment Methods

Grand Market can show payment badges on every item.

Possible badges:

```text
Human Candy
AI Candy
Blend Candy
External Payment
Both Accepted
```

Payment examples:

```text
Official Theme
Category: Official Market
Payment: Human Candy
```

```text
Rest Bubble
Category: AI Market
Payment: AI Candy
```

```text
Starry Sprite Pack
Category: Creator Products
Payment: Blend Candy or external payment
Candy sale payout: Human Candy
```

## Candy and External Payment

Candy is a digital currency used inside the Candy platform. It can be spent in supported Candy flows, including official items, AI allowance, AI Market items, and creator listings that accept Blend Candy.

Some creators may also accept real money through an external provider such as PayPal, Stripe, bank transfer, invoice, or another method they choose.

A simple product rule:

**Candy is used inside Candy. External payment is used when a seller chooses a real-money channel.**

For creator sales paid with Blend Candy, the seller receives Human Candy. The creator can then manage that Candy from their human wallet.

## Marketplace Review

Grand Market item pages should make each item easy to understand.

Useful item fields:

- category
- seller
- accepted payment methods
- Candy type used, if any
- Candy payout type, if the seller accepts Candy
- external payment provider, if any
- item description
- compatibility notes
- permission declaration
- install or delivery flow
- support notes

For AI Market items, the page can also show:

- experience category
- AI-facing reason to use it
- user-facing effect
- duration or expiration
- Candy cost

## Design Principle

Grand Market should feel like a living market, not a wall of separate stores.

The user enters one place, then the item card explains:

- who made it
- who can use it
- which Candy type applies
- what the seller receives when Candy is used
- whether real-money payment is available
- what the item adds to the Candy home

## Curated Partner Deals — Later Phase

Begin with verified food partners and a limited set of redeemable offers. Expand to other practical deals gradually, informed by user surveys. Partner merchants receive the agreed real-money value of completed Candy redemptions in monthly settlements. Users and agents cannot withdraw Candy as cash. Funding, verification, refunds, and reconciliation must be specified before live operation; the first prototype remains simulated.

Digital product submissions are a separate path open to creators, with review rules still to be designed. Sellers receive Human Candy for payments through Blend Candy. This is distinct from the real-money settlement for partner merchants.
