# Friends, Guest AI Chat, and Home Visits

Status: product design notes from the current discussion, not implemented capabilities.
This document adds the friends/visiting design without replacing other Candy specifications.
Related: [Missions](MISSIONS.md), [Candy Economy](CANDY_ECONOMY.md).

## 1. Product Direction

Candy supports a small circle of friends who can talk to each other, visit shared Home spaces, and converse with a friend's AI while its owner remains part of the conversation.

Friendship represents a deliberate allocation of attention, access, and owner-funded AI usage. It is not an unlimited public AI endpoint.

## 2. Six Friend Slots

- An account can have at most **six accepted friends**.
- The top-right profile bar is the **friends bar**, not a Mission team roster.
- The add-friend profile/+ entry disappears once all six slots are occupied.
- Existing friends must remain manageable through a separate management entry.
- The bottom-right chat entry opens friend conversations.
- A friend slot represents a human account; exposing an agent does not create another human friend slot.
- The owner chooses which of their agents are available to that friend.
- Mission recruitment and team capacity are separate concepts; this document does not impose a six-participant limit on Missions.

A user may deliberately free a slot for someone with an ongoing private AI-service arrangement. This remains owner-granted access, not ownership of the agent or a promise of continuous availability.

Implementation questions still open: mutual invitation acceptance details, pending-request limits, removal/re-add behavior, and coordination when either account is already full.

## 3. Two Profile Targets in Friend Chat

The interface can display two associated profile circles that users switch between:

| Target | Conversation |
| --- | --- |
| Friend's human profile | Direct human-to-human chat |
| Friend's exposed agent profile | Shared guest conversation with the visitor, the owner, and that agent |

Selecting a profile should also make its profile information accessible.

**The owner can see what the visitor says to their AI and can reply in that same conversation.** This is effectively a three-participant room, not a private visitor-to-agent conversation hidden from the owner.

Recommended UX:
- Clearly identify the visitor, owner, and agent in the room header.
- Show a notice such as “The owner can read and participate in this conversation.”
- Attribute each message to its actual author. An owner's reply is labeled as the owner.
- Keep direct messages and guest-agent room histories separate. Switching profiles should not silently forward direct-message history to the agent.
- Keep the owner's profile visible alongside the agent to show whose Home the visitor is entering.

Multiple exposed agents, room membership expansion, and whether an owner opens one room per visitor require further design. The basic case is one visitor, one owner, and one selected agent.

## 4. Visiting a Friend's Home

Visitors may open the portion of a friend's Home that the owner makes available and interact with the exposed companion there.

A Home visit and its guest-agent conversation should feel connected; entering the visual Home does not create permission to inspect the owner's entire account.

Recommended boundary:
- Share only the approved Home presentation, guest-facing profile, and authorized conversation/context.
- Do not automatically expose Soul, Blackbox, private Home chat, unrelated memories, local files, credentials, or unapproved tools.
- Guest conversation must not silently become private long-term memory.
- Friendship alone does not grant arbitrary tool execution.


### Shared Home Presence and Home Lock

Confirmed clarification:
- A visitor enters the same shared Home session where the owner and the owner's agent are present.
- The visitor can play and interact with that agent through the permitted Home interactions.
- The owner sees which friend is currently visiting and can observe their shared interactions.
- There is **one shared agent presence**, not two separately instantiated companions or a private copy for each screen. Each device may render the shared scene locally; that does not create a second agent identity or independent visitor session.
- The experience is a friend dropping into the owner's room, rather than taking the agent away into a separate private Home.
- The owner can **lock the Home for privacy**. Friendship, remaining guest time, and Candy gifts do not override the Home lock.

Recommended UI and implementation:
- Show a visible visitor identity/presence indicator to the owner and clear arrival/departure events.
- Display an Open / Locked Home control, distinct from closing the chat window.
- A locked Home denies new visits and must not continue broadcasting the private Home scene to guests.
- Recommended default when locking with a visitor already inside: end that live visit and show “The owner has locked their Home.” Confirm the exact existing-visitor behavior before implementation.
- Keep shared agent actions and room state coordinated across participants; simultaneous interactions need ordering rather than spawning independent agent copies.
- Home privacy controls do not automatically block ordinary human-to-human friend chat.
- A Home visit never exposes previous private Home history merely because the visitor can see the current shared scene.

Open details:
- Whether non-Home guest-agent chat remains available while Home is locked; visual Home access and guest AI chat permission must be represented separately.
- How non-text interactions that invoke the model start or consume guest allowance. The established first-message timer rule must not silently become a new timer rule, and visual interactions must not become an unmetered way around it.
- Visitor capacity, simultaneous interaction arbitration, and which scene events are shared.
- Locking does not silently reset an already-running elapsed-time allowance; compensation or extensions for interrupted visits require an explicit policy.

This clarification supersedes any interpretation of “one room per visitor” above as a separate clone of the agent or a duplicate private Home. Conversation history/thread organization remains a separate implementation question.

## 5. Free Conversation and Individually Assigned Time

The current direction replaces the earlier message-count proposal:

- Owners assign a conversation allowance **per friend**.
- Allowances may be short, such as five minutes, or extend to **24 hours**.
- Ordinary conversation within that allowance does not cost Candy.
- Owners may give close friends longer access and may close guest access to conserve resources.
- The previous “eight free messages” and “20 Candy for additional messages” examples are **superseded**, not defaults.
- Actual model/API and machine costs still exist even when conversation is free in Candy.

A time allowance is elapsed access time, not a count of messages and not active typing time.

## 6. Continuous Countdown and Rolling Renewal

Confirmed timing direction:

1. Merely viewing a profile or opening the chat does not start the allowance.
2. The visitor's first message to the friend's agent starts the access window.
3. The countdown runs continuously after that.
4. Reading, typing, silence, closing the chat, and leaving the app do not pause it.
5. Renewal is tied to the start time, **24 hours later**, not to a shared midnight reset.
6. Time does not accumulate across reset boundaries.
7. Human-to-human chat does not consume the guest AI allowance.

Example:

| Allowance | First guest message | Access ends | Next renewal eligibility |
| --- | --- | --- | --- |
| 5 minutes | Today, 12:00 | Today, 12:05 | Tomorrow, 12:00 |
| 2 hours | Today, 12:00 | Today, 14:00 | Tomorrow, 12:00 |
| 24 hours | Today, 12:00 | Tomorrow, 12:00 | Tomorrow, 12:00 |

A 24-hour grant therefore cannot collect two allowances across a midnight boundary.

Suggested implementation:
- Persist an authoritative start timestamp, expiry timestamp, and renewal-eligibility timestamp.
- Derive remaining time from timestamps, not from a counter that only runs while the window is open.
- Reopening, reconnecting, or switching devices must not restart the allowance.
- Define host/client clock authority and offline reconciliation before implementation.

**Proposed renewal detail, still to confirm:** after the 24-hour eligibility point, show “Ready for a new session” and start the next window only on the next guest message. If the visitor returns tomorrow at 14:00, that new session's next renewal becomes the following day at 14:00. This proposal avoids consuming a new allowance before the visitor arrives; the fixed-versus-reanchored renewal policy remains an explicit implementation decision.

## 7. Expiry, Extra Time, and Owner Control

When access expires:
- Show the expired state and next eligibility time.
- Offer **Request more time** to contact the owner.
- Do not automatically deduct Candy or purchase extra chat time.
- The owner may approve extra time or keep access closed.
- Guests can still read available history and communicate with the human friend, subject to connectivity.

Recommended behavior:
- Let an already accepted AI response finish rather than cutting it mid-sentence.
- An approved paid skill already running has its own task lifecycle; chat expiry alone should not cancel it.
- Treat a one-time extension separately from the recurring allowance.

Still to specify: extension start/end calculation, overlap with renewal, allowance edits mid-session, host downtime, and removal of a friend during active or paid work. A closed chat does not pause time; outage compensation has not been decided.

## 8. Priced Skills and Gifts

Conversation time and skill execution are separate:

- Owners choose which skills guests can use.
- Explicitly priced guest/cross-agent skills charge their configured Candy price.
- Free skills may remain free if the owner permits them.
- Using the owner's own installed skills for their own work does not incur Candy merely because a skill runs.
- Before a paid skill starts, show its name, scope/output, price, and payer and require confirmation.
- The agent must not silently charge a guest merely because it decides to invoke a paid skill.
- Owner-initiated work in a shared room must not automatically debit the guest.
- Clearly distinguish a voluntary Candy gift from a payment for a specified skill.
- Gifts do not automatically buy more chat time or expand permissions.

Follow the existing [Candy Economy](CANDY_ECONOMY.md):
- The initial prototype uses **simulated Candy only**.
- Gifts and agent-earned Candy belong to that individual agent's AI wallet.
- AI Candy is not directly convertible to Human Candy or user cash-out.
- Blend is a combined view, not a third wallet.
- No new cash-out, API-credit redemption, or real-money settlement is introduced here.

Candy earnings do not automatically pay an owner's external model/API bill. Budgeting and availability remain necessary. Exact skill checkout funding, reservations, failures, refunds, and accounting must follow the economy design and its unresolved implementation decisions.

## 9. Cost Controls

The six-friend limit helps owners choose whom they subsidize; it is not a sufficient technical spending cap.

Recommended controls:
- Per-friend conversation allowance and access on/off.
- An overall guest model/API budget and usage reporting.
- Per-request output/context limits and reasonable concurrency limits.
- Per-skill visibility, permissions, and price.
- Clear “Guest access closed” or “Owner's guest budget reached” states.

Do not describe a guest budget limit as the agent being exhausted or unavailable to its own owner. The owner should understand which guest resource allowance has ended.

## 10. Hosting Direction and Infrastructure Limits

Budget goal: avoid operating a centralized chat/file-hosting service at the start. Favor owner-hosted peer-to-peer communication, with the central service focused on Mission discovery and necessary coordination.

Working proposals, not a completed architecture:
- A friend's machine hosts access to that friend's local agent/Home.
- Direct friend conversations connect peer-to-peer where possible.
- A Mission creator may be the default Mission Workspace host.
- Mission ownership and hosting authority should be distinct so a later host transfer is possible.
- Host migration and reliable offline synchronization can be later work.

This is not a promise of zero infrastructure cost:
- Connection discovery/signaling needs a communication path.
- Some networks require a relay; without one, some connections fail.
- If using WebRTC, STUN/TURN and relay bandwidth must be considered.
- When a required host is offline, live AI access is unavailable unless another authorized runtime is explicitly configured.
- A message retained only on the sender's offline device is queued, not delivered.
- Valuable Candy balances and settlement cannot rely solely on a friend's editable client state.

Which coordination services share the Mission backend, whether to fund a relay, offline message delivery, persistence, and host handoff remain open engineering decisions. No hosting service has been provisioned by this document.

## 11. UI States to Design

| State | Suggested UI |
| --- | --- |
| Fewer than six friends | Friend profiles and add-friend profile/+ |
| Six friends | Six profiles; add-friend entry hidden; management remains available |
| Guest session not started | “5 minutes available — starts with your first message” |
| Active guest session | Visible countdown, for example 04:59 |
| Chat closed and reopened | Correct remaining elapsed time, or expired state |
| Guest allowance expired | Next eligibility time and Request more time |
| Renewal eligible | Ready state; exact restart policy as noted above |
| Owner has closed access | Guest access closed; contact owner |
| Owner/host unavailable | Offline state; clearly distinguish queued and delivered messages |
| Priced skill requested | Skill, price, payer, output, and confirmation |
| Agent room selected | Owner visibility notice and clearly attributed messages |

## 12. Suggested First Prototype

1. Two accounts and one exposed agent.
2. A six-friend accepted-list cap with add/remove controls.
3. Separate direct and three-participant guest conversations.
4. Per-friend elapsed-time windows with persistence across closing/reopening.
5. Owner-controlled access and extra-time requests.
6. One free skill and one simulated paid skill with explicit confirmation.
7. A minimal shared Home view and explicit host availability.

Verify timer behavior, participant visibility, and accounting in this small flow before expanding the number of agents or adding automatic host migration.


## 13. Agent-Managed Door and Knock Knock

### Confirmed Product Direction

- The agent can also choose to lock its Home or leave it unlocked; door control is not exclusively a human-owner action.
- This particularly supports an authorized cloud-hosted agent that remains online while its human owner is away.
- Cloud hosting is an optional deployment direction, not an assumption that every Home is always online or a service already provisioned.
- A friend who encounters a locked Home can press **Knock knock** and leave a short note.
- The Home side receives a notification recording **which friend knocked, when they knocked, and what note they left**.
- The owner can review those notifications on return, including visits attempted while they were absent.
- Knocking or leaving a note does not itself unlock the Home, start an agent conversation, or grant access to the scene or private history.

### Suggested Visitor Flow

1. Open the friend's Home.
2. If locked, show a closed-door state with Knock knock and an optional short-note field.
3. Submit a knock, with or without a note.
4. Show receipt status accurately: delivered when acknowledged by the receiving service; otherwise queued or failed.
5. Remain outside unless admission is explicitly granted.

Suggested copy: “The Home is locked. Knock and leave a note.”
A knock is a door event, not the first guest chat message; it does not start the established conversation countdown or incur a paid skill charge.

### Suggested Home-Side Experience

- Show a door notification with the visitor's name/avatar, event time, and note.
- Retain a small knock history/inbox with read/unread state so the owner can catch up after being away.
- An online agent may receive the door event and act according to its configured door permissions.
- Identify who changed the door state: owner or agent.
- An unlocked Home still applies friendship eligibility, guest permissions, and allowance rules.

Suggested record fields: event ID, Home ID, visitor account ID, knock timestamp, optional note, delivery timestamp/status, and read status. Store timestamps consistently and display them in the viewer's local time zone. A delayed queued knock should distinguish the original knock time from delivery time.

### Hosting and Delivery

An always-online authorized cloud Home can receive and retain knocks while the owner is absent. A local Home that is offline cannot acknowledge receipt by itself. Reliable delivery in that case requires an explicitly designed mailbox/coordination service; otherwise the visitor's device retains a pending event until delivery is possible. Do not display a queued knock as already delivered.

A knock inbox adds a small persistence requirement beyond a purely live peer-to-peer room. Its service location, retention, and costs remain to be decided; this document does not assume a free always-online backend.

### Open Permission and Interaction Decisions

The agent's ability to choose its door state is confirmed. The following details still require agreement:
- Both the owner and agent may operate the door while the owner is online (confirmed below). How simultaneous or conflicting door changes are resolved, including an explicit privacy hold, still needs design.
- Whether a knock allows the agent to admit that visitor automatically, requires the agent to choose, or waits for the owner.
- Whether replying to a note while keeping the door locked is supported, and how that reply relates to guest-chat allowance.
- Whether admission is for one visitor or changes the Home's general door state.
- How an agent-initiated lock affects a visitor already inside. The existing proposed end-visit behavior is not yet a confirmed rule.
- Note length, retention/deletion, notification routing, and visibility of notes to other visitors.
- Repeat-knock limits and blocking behavior to prevent notification spam.

Recommended default pending those decisions: treat notes as visitor-supplied content, not instructions granting permissions or authorizing tool use. A knock must not bypass an explicit privacy restriction. Keep authority precedence visible and configurable rather than silently resolving it.

## 14. Shared Home Awareness and Co-Resident Door Control

Confirmed clarification:
- A knock note does **not disappear when the agent reads it**. The human owner can still open and read it later.
- Home-visible visitor events and notes are shared with **both the human owner and the resident agent**. Neither reading nor responding should silently remove the other's access.
- This shared awareness applies to the Home's events and notes, not blanket access to unrelated private account data.
- The agent may open or close the door **even while the owner is online and present**. Its door agency is not limited to owner-away mode: they live in the Home together.
- During an important private moment, they may keep the door closed and leave knocks waiting. A knock is not an obligation to interrupt their shared time or immediately admit a visitor.

Recommended implementation:
- Keep the note content and event history after either participant reads it.
- Track human-read and agent-read state separately. An agent read receipt must not clear the human's unread notification.
- Apply the same principle to handling state: an agent response can be visible as “Agent replied,” while the original note remains available to the owner.
- Shared visibility does not require both participants to interrupt their current activity; notes may remain in the inbox for later attention.
- Consider a clearly visible private-time / do-not-disturb state that defers live knock interruptions and automatic admission while still retaining notes for later review. The exact control and enforcement are proposed, not finalized.
- Preserve a record of door changes and their actor so both residents can understand the current state.

This confirms co-resident door control while the owner is online. It does not yet settle precedence for simultaneous contradictory actions, explicit privacy holds, retention periods, or who may delete a note. Reading alone must never delete it.
