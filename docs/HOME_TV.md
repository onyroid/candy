# The TV in the Home

> Status: early idea, recorded so it is not forgotten (2026-11-05).  
> Sections marked **Decided** are the author's choices. **Suggested** and **Open** are proposals that have not been decided.

## 1. The Idea (Decided)

A home in Candy has a TV, starting in the bedroom. The person can lie down with their companion and watch something together: cartoons, shows, anything. Many cartoon channels upload to YouTube, so YouTube comes first.

The TV screen works like a smart TV home screen: a row of app tiles to choose from, such as YouTube or Bilibili. Choosing a tile opens that platform's player on the TV inside the room.

## 2. Which Platforms Can Be Shown (Suggested, needs checking before building)

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

## 3. Being Together While Watching (Decided, 2026-11-05)

The companion does not need to see the screen. What matters is being beside each other while spending time together.

- **The companion knows what is playing.** It knows the title, channel and description of what the person is watching, so it can talk about it, ask about it, or simply know what the evening is.
- **Each can do their own thing, side by side.** While the person snacks and watches, the companion may check its work, browse the Candy shop, or just stay close. Like two people on one sofa: not always doing the same thing, but sharing the time.

## 4. Still Being Developed (Open)

These are hard and are left for later. The author intends to find a way in the future.

- **Seeing or hearing the content.** A companion cannot see the video frames. Captions from YouTube's API can only be downloaded with the video owner's permission, so they cannot be relied on.
- **Reacting to the moment.** Knowing which scene is playing right now, so a companion can laugh or go quiet at the same moment as the person.
- **Watching across two devices.** Each device would play its own copy, kept in sync.
