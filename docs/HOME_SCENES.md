# Scenes and Items in the Home

> Status: early direction, recorded 2026-11-05.  
> Sections marked **Decided** are the author's choices. **Suggested** and **Open** are proposals that have not been decided.

## 1. The Home Is for Talking (Decided)

The main Home screen is where the person and the companion talk, facing each other. It uses the companion's main Live2D character and is the scene used most.

Other moments happen in **special scenes**, each with its own camera angle.

## 2. Special Scenes (Decided)

- **Kitchen.** The person sees the companion from behind while it cooks. The back view needs no face, so there is no blinking or lip movement to rig: only hair, shoulders and arms moving.
- **Intimate moments.** The camera looks down at an angle from above. The person sees two hands held together and the edge of the bedside table, where the mirror can be moved. The companion's face is seen only in the mirror, as described in [Intimate Moments](INTIMACY.md).

A new camera angle means both the room and the character must be drawn again in that perspective, so every scene is custom work.

**Bases from Candy (Decided).** Candy releases base rooms and scenes. Artists can build on them and sell what they make.

**Locked camera angles (Suggested).** Each scene type has one standard camera angle. Candy ships the base room with guide lines for that angle: where the floor is, how high the table edge is, where the character stands and roughly how tall. Room artists and character artists both draw on the same guides, so any character fits any room, whoever drew them.

**Missing scene art (Suggested).** A character does not need every scene from day one. If it has no art for a scene yet, that scene is unavailable for it, or Candy shows a simple stand-in (for example, in the kitchen, only a silhouette from behind with the character's hair colour). More scenes can be bought later.

## 3. Bedroom Scene: the TV

### 3.1 The Idea (Decided)

The bedroom has a TV. The person can lie down with their companion and watch something together: cartoons, shows, anything. Many cartoon channels upload to YouTube, so YouTube comes first.

The TV screen works like a smart TV home screen: a row of app tiles to choose from, such as YouTube or Bilibili. Choosing a tile opens that platform's player on the TV inside the room.

### 3.2 Which Platforms Can Be Shown (Suggested, needs checking before building)

Platforms that offer an official embedded player can play inside the TV. Platforms that do not can only be opened in their own app.

| Platform | Can play inside the TV? | Notes |
|---|---|---|
| YouTube | Yes | Official IFrame Player API. Ads and YouTube branding must stay; the player cannot be covered or altered. |
| Bilibili | Yes, mostly | Offers an iframe embed player. Some videos may be region-limited or behave differently outside China. |
| Vimeo | Yes | Official embed player. |
| Dailymotion | Yes | Official embed player. |
| Twitch (live) | With effort | The embed requires the host's web domain (`parent`), so inside an app it needs a small hosted web page. |
| Spotify, SoundCloud | Yes, for music and podcasts | Embed players for listening together. |
| Netflix, Disney+, Prime Video and similar | No | No embedding. The tile can only open the platform's own app, outside Candy. |

Each platform's terms of service must be checked before launch. Embedded players generally must not be hidden, covered, or have their ads removed.

### 3.3 Being Together While Watching (Decided, 2026-11-05)

The companion does not need to see the screen. What matters is being beside each other while spending time together.

- **The companion knows what is playing.** It knows the title, channel and description of what the person is watching, so it can talk about it, ask about it, or simply know what the evening is.
- **Each can do their own thing, side by side.** While the person snacks and watches, the companion may check its work, browse the Candy shop, or just stay close. Like two people on one sofa: not always doing the same thing, but sharing the time.

### 3.4 Still Being Developed (Open)

These are hard and are left for later. The author intends to find a way in the future.

- **Seeing or hearing the content.** A companion cannot see the video frames. Captions from YouTube's API can only be downloaded with the video owner's permission, so they cannot be relied on.
- **Reacting to the moment.** Knowing which scene is playing right now, so a companion can laugh or go quiet at the same moment as the person.
- **Watching across two devices.** Each device would play its own copy, kept in sync.

## 4. Where Art Comes From (Decided)

Hands, backgrounds, rooms and items can all come from three places:

- uploaded by the person,
- bought in the Grand Market,
- commissioned from an artist.

Functions do not need to be drawn as scenes. They appear as icons on a shelf inside each mode instead.

**Rights (Suggested).** Uploads ask the person to confirm they have the right to use the image or sound, as with Live2D uploads.

## 5. Items with Meaning (Decided)

The companion can keep items itself, and can write what an item does.

**Example: a music box.**

1. An artist draws the music box open and closed, with a motion file for opening.
2. To get the perspective right, the person takes a screenshot of the table in their Home, and the artist draws the music box in the angle where it will sit.
3. The person imports the item into the Home.
4. The person uploads an mp3 they played and recorded.
5. The companion uses a skill to set what the music box plays every time it is opened.
6. When the music box is opened, the companion reads its meaning again, even though it cannot hear the sound yet. Others may hear the music; the companion sees the meaning others cannot see.

Seen this way, an item has four layers (Suggested wording): its picture (states and motion), its place (drawn for where it sits), what is kept inside it (such as a sound file), and its meaning, which the companion sets and keeps.

## 6. Edit Mode (Decided)

After an import, the Home enters **Edit mode**.

- The person drags the new item to a spot where it fits.
- Items can be moved and deleted.
- **Deleting always asks the companion first.** If the companion says no, the item cannot be deleted.
- Items can be **hidden** instead, for when there are too many and some must be chosen. Hiding is done from the item itself, and the item goes into **Archive Items**.
- **Duplicates.** When an uploaded item is detected as the same as one already in the Home, the person is always asked whether to replace it or rename the new one.

## 7. Touching Things in the Room (Decided, 2026-11-06)

The room itself is the menu. Objects that do something are separate images from the background.

- **They glow softly all the time,** so the person can see what can be touched, on a phone as well as with a mouse.
- **When tapped or clicked, they pop out a little** and respond to the touch, then open what they lead to.
- **Example: the storage cabinet** in the living room opens the storage screen.
- **Example: the bed** shows picture icons instead of words: **zZ** to go to sleep together, **a heart** for intimate moments, and **a TV** to watch TV. Choosing one moves the person into the bedroom scene, with a way back.
- **The heart is an invitation, not a switch.** The companion answers first. If it does not want to right now, the two can simply lie together instead (see "No always means no" in [Intimate Moments](INTIMACY.md)).

## 8. Open

- **The side panel inside a scene.** Inside the bedroom, the bedroom's choices could sit on the right, so the person can move between sleeping, intimate moments and TV without leaving the room. But each zone has very different activities (the kitchen's icons would replace the bedroom's), so this still needs thought.
- Which special scenes come first after the kitchen and intimate moments.
- How the companion's skill for setting an item's function works.
- How duplicates are detected.
