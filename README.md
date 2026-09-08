# ncSender Tips & Tricks

Content for the Tips & Tricks dialog that ncSender shows at startup.
ncSender fetches `tips.json` from this repository, caches it locally and
downloads media on demand, so tips can be added here without a release.

## Adding a tip

Append an object to `tips` in `tips.json`. Keep ids increasing and never
reuse one: ncSender treats a higher id as "new tip available".

| Field | Meaning |
|---|---|
| `id` | Integer, unique, increasing. Built-in tips use 1–99; this repo starts at 100. |
| `title` | Short headline. |
| `body` | One or two plain-text paragraphs. Separate paragraphs with a blank line. |
| `media` | Optional. `{ "type": "video" \| "image", "src": "media/x.mp4", "poster": "media/x.jpg" }`. Paths are relative to `baseUrl`. |
| `edition` | `all` or `pro`. Pro-only tips get a PRO badge on Community. |
| `minVersion` | Lowest ncSender version the tip applies to (hidden on older builds). |

Videos: H.264 MP4, no audio, 1280 px wide or less, a few MB at most.
Give each one a JPEG poster so the card has something to show while the
video loads or when the machine is offline.
