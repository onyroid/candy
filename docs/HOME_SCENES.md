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

## 3. Where Art Comes From (Decided)

Hands, backgrounds, rooms and items can all come from three places:

- uploaded by the person,
- bought in the Grand Market,
- commissioned from an artist.

Functions do not need to be drawn as scenes. They can be added through the interface (UX/UI) instead.

**Rights (Suggested).** Uploads ask the person to confirm they have the right to use the image or sound, as with Live2D uploads.

## 4. Items with Meaning (Decided)

The companion can keep items itself, and can write what an item does.

**Example: a music box.**

1. An artist draws the music box open and closed, with a motion file for opening.
2. To get the perspective right, the person takes a screenshot of the table in their Home, and the artist draws the music box in the angle where it will sit.
3. The person imports the item into the Home.
4. The person uploads an mp3 they played and recorded.
5. The companion uses a skill to set what the music box plays every time it is opened.
6. When the music box is opened, the companion reads its meaning again, even though it cannot hear the sound yet. Others may hear the music; the companion sees the meaning others cannot see.

Seen this way, an item has four layers (Suggested wording): its picture (states and motion), its place (drawn for where it sits), what is kept inside it (such as a sound file), and its meaning, which the companion sets and keeps.

## 5. Edit Mode (Decided)

After an import, the Home enters **Edit mode**.

- The person drags the new item to a spot where it fits.
- Items can be moved and deleted.
- **Deleting always asks the companion first.** If the companion says no, the item cannot be deleted.
- Items can be **hidden** instead, for when there are too many and some must be chosen. Hiding is done from the item itself, and the item goes into **Archive Items**.
- **Duplicates.** When an uploaded item is detected as the same as one already in the Home, the person is always asked whether to replace it or rename the new one.

## 6. Open

- Which special scenes come first after the kitchen and intimate moments.
- How the companion's skill for setting an item's function works.
- How duplicates are detected.
