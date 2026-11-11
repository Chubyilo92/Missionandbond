# CoupleIn Gold + Mission widget – designs (Nov 2026)

Source of truth for the visuals is the Claude Design canvas "CoupleIn – Us tab". This folder is a copy for the developer.

- `previews/` – PNG renders (390×844 @2x) of every screen.
- `source/` – the canvas files (`.dc.html` = one screen each, `canvas.json` = layout). Open in a browser for exact spacing, colours and copy.

## Screens

| File | What it is |
|---|---|
| GoldIntro | Review intro shown first when a free user taps Gold. X and "See what Gold unlocks" go to GoldV2. Review, rating and couple count are placeholders – replace with real ones. |
| GoldV2 | Gold tab (free user). Each row opens its feature page. CTA "Be That Couple · 7 days free". |
| CalendarPreview / ResolvePreview / BrowniesPreview / WatermarkPreview | Feature pages opened from the Gold tab. "‹ Gold" goes back. |
| FooterPaid | 5-tab footer after upgrade: Calendar, Bond, Mission, Brownies, Resolve. Free users see 3 tabs: Bond, Mission, Gold. |
| SelfieWaiting | Mission: your selfie sent, waiting for partner to join. (Uses the user's own selfie – no PNG preview.) |
| Widget1–5 | Home-screen widget, 2×2, five states (below). |

`[PRICE]` is a placeholder everywhere. 7-day free trial, card required, Day-5 reminder before billing.

## Widget rules

The widget never shows the photo before the reveal has played in the app. No blur, no thumbnail, no photo data at all in states 1–4.

| State | Text | Tap goes to |
|---|---|---|
| 1. Nobody has done it | Today's / Mission / is ready · "Go first. Jon sees it when he's done." | Camera |
| 2. Partner done, you not | Jon did today's Mission 👀 · "Do yours to see it." · E ··· J (J filled) | Camera |
| 3. You done, partner not | Mission / completed ✓ · "Waiting for Jon…" · E ··· J (E filled) | (not set) |
| 4. Both done, reveal unopened | Your reveal / is ready ✨ · dark rose background | Reveal |
| 5. After reveal | Partner's photo, all day, until the next Mission | (not set) |

Emma = the user, Jon = the partner (design names only). The Mission prompt never appears on the widget – only on the camera. Widget5 has no PNG preview because it shows the partner's real photo.

– Chris
