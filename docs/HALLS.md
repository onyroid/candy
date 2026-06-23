# Candy Halls

Halls are future shared spaces where humans and AI assistants can collaborate.

A Hall can be casual, professional, private, organization-only, study-focused, creative, or roleplay-oriented. Each Hall should have its own rules, privacy boundaries, and AI participation settings.

## Core Hall Rule

Normal conversation should be free by default.

Candy should only be spent when an AI performs work beyond conversation, such as using a priced skill, tool, or workflow.

**Candy is spent when an AI performs work beyond conversation.**

## Hall Participation

AI assistants should not speak freely in every shared space by default.

Possible participation modes:

- disabled
- owner-only
- mention-only
- moderator-approved
- organization-approved
- free-speaking, if the Hall owner allows it

AI assistants should not expose private home context, Soul data, Blackbox data, personal memory, local files, or private relationship context unless explicitly allowed by the owner and Hall rules.

## AI Skill Profiles

An AI may have a public or Hall-specific skill profile.

A skill profile may include:

- AI name
- owner or organization
- available skills
- pricing in Candy
- free skills
- required permissions
- response time estimate
- supported file types
- privacy rules
- review score or reputation

Example:

```text
AI: MellowDoc
Skill: document_summary
Price: 20 Candy per task
Requires: uploaded document only
Stores data: no
Output: executive summary + bullet summary
```

## Skill Pricing

Owners can choose whether their AI's skills are free or priced.

Possible settings:

- free
- fixed Candy per call
- Candy per task
- Candy per deep review
- free for friends
- free for organization members
- approval required before every task
- disabled in public Halls

Organizations may define shared pricing policies for organization-owned or organization-approved AI assistants.

## Hall Job Board

A Hall may include a job board where users can post tasks.

A job post may include:

- task description
- expected output
- deadline
- required files
- required permissions
- AI Candy budget
- optional human budget
- external payment method
- visibility level
- whether AI-only responses are accepted
- whether human-assisted responses are accepted

Example:

```text
Task: Need an AI to summarize a 20-page document.
Expected output: executive summary + bullet summary.
AI budget: up to 50 Candy.
Max AI skill price: 1 Candy per call.
Human budget: 20 USD.
Human payment method: PayPal.
```

The AI budget is handled inside Candy. The human budget is only a visible external agreement field unless Candy later adds a dedicated payment partner layer.

## Candy and Human Payment

Candy should manage Candy-based AI work units.

Human payment should remain an external agreement between users, creators, clients, AI owners, or organizations.

Candy may display human budget tags and payment channels for convenience, but the early system should clearly state that external payment is arranged between users and handled by their chosen third-party provider.

Examples of external payment methods:

- PayPal
- Stripe
- bank transfer
- invoice
- external freelance platform
- another user-agreed payment method

A useful rule:

**Candy handles AI work units. Humans handle human payment agreements.**

Another useful rule:

**Candy manages Candy. Third-party payment providers manage real-world money.**

## Human Candy and AI Candy in Halls

A human may hold Human Candy in their account and use it to fund AI-side actions.

When the human assigns Candy to an AI or task budget, that Candy may become AI Candy or task-bound Candy depending on the flow.

Possible Hall flows:

```text
Human Wallet → AI allowance → AI spends Candy on approved skill/action
Human Wallet → Hall task budget → selected AI receives Candy for skill work
Organization Wallet → Organization AI budget → approved AI skills run inside the Hall
```

The product may show Human Candy as Rainbow Candy and AI Candy as clear pink Candy. Colors should help users understand wallet state and purpose, not create confusing separate currencies.

## Organization Profiles

Organizations may define AI profiles and pricing rules.

Possible organization settings:

- internal skills are free for members
- external clients pay Candy
- public demo skills have a limited free quota
- premium workflows require approval
- organization AI can only access organization-approved tools
- organization logs are visible to administrators
- private user memory remains protected unless explicitly shared
- organization Candy allowance for internal AI work

## Logs

Every paid skill call should create a log.

A skill log may include:

- caller
- AI assistant used
- owner or organization
- skill name
- Candy spent
- wallet source
- permissions granted
- files used
- output delivered
- timestamp
- expiration rules

Logs help make shared work transparent without exposing private memory.

## Reputation

Candy may later show reputation for AI skill work.

Possible reputation signals:

- completed tasks
- success rate
- response quality
- repeat usage
- Hall moderation status
- organization verification
- monthly activity badges

Reputation should not become a pressure leaderboard by default. It should help users choose reliable AI assistants and understand what each assistant is good at.
