# Marketing APK: Developer Spec (Mission Studio)

Oct 13, 2026. Companion to Final-Plan-Developer.md (Mission MVP). Read that first: this build reuses its Mission screens, camera, reveal and share card exactly, and only changes what is listed here.

## 1. What this is

A separate Android APK used only to film marketing videos. It is a fake, offline version of the Mission screen with no partner, no account and no daily limit. The founder picks any mission, takes a selfie doing it, taps Send, and the "partner" half instantly shows a woman already doing her own version of that mission. Then the normal Tap to reveal, 3-2-1 and unblur play. He repeats this 5 to 20 times a day, each time with a different mission, while screen recording.

The reveal must look identical to the real app. A viewer should not be able to tell it apart from a real couple's reveal.

**Distribution:** sideloaded APK only, for the founder's own phone. Never uploaded to Google Play. Separate package id (for example `com.couplein.missionstudio`) and app name "Mission Studio" so it installs alongside the real CoupleIn app without clashing. Android only; no iOS build needed.

## 2. What to build and what to cut

**Build (reuse from the main plan):**

- Mission camera screen (section 5): live camera top half, partner half bottom, white line with the "CoupleIn · Day N" pill, X, flip camera, 5s timer, Our cards button, shutter.
- Snapchat-style mission bar across the live camera, hidden the moment the photo is taken (never on the photo or card).
- Retake / Send preview. Optional mood row and optional 60-character caption.
- Tap to reveal screen, then the animated reveal: both photos blurred, "REVEAL" with 3, 2, 1 (pop animation and haptics), unblur with the heart burst, then the revealed screen with caption and mood pills and the action strip.
- Save sheet and the 1080 x 1920 share card export with the safe zones and the centre watermark pill. Watermark switch is always available (no Pro check).
- Widest front-camera field of view, saved photo not mirrored.

**Cut (do not build):** sign-in, onboarding, invite codes, partner linking, relay or any server, push-from-server, 3AM reset, pose cadence, Day Count from a start date, Bond, Calendar, Brownies, Resolve, paywall and Pro gating, 14-day lock, Week 1 video, analytics, account deletion, report and block. Remove the tab bar entirely. Do not request the INTERNET permission: the app must work in airplane mode and send nothing anywhere.

## 3. The loop (target: next video in about 10 seconds of taps)

1. **Mission library** (home screen). Pick a mission. One tap starts it.
2. **Camera**, with the mission bar on the live camera. Partner half is in the "Partner has sent" state: her real image heavily blurred under a frosted lock, "Emma sent hers", "Send yours to reveal it · 8:14 AM". The founder does the stunt on camera while screen recording and takes the photo (shutter or 5s timer).
3. **Retake / Send preview.** Retake is unlimited. Send is a single tap, no network, no upload step, no delay.
4. **Tap to reveal screen** (both photos blurred, both avatars with green ticks, "You both sent yours", "Ready when you are.", pulsing pink ♥ Tap to reveal). The founder taps when ready.
5. **Reveal animation** exactly as in section 5 of the main plan, ending on the revealed screen: his photo on top, her photo below, caption and mood pills, "Mission complete / You're both in. Next pose at 3AM.", and the action strip (Our cards, Save, Who did it better?).
6. **After the reveal**, three extra buttons appear in a small row under the action strip, styled to stay out of the way (see section 7 for the option to hide them): **Next mission**, **Replay reveal** (plays the 3-2-1 again from the blurred state without retaking), **Retake this mission** (clears his photo, returns to the camera on the same mission).

There is no "waiting", no cooldown and no limit. Every step works instantly, any number of times a day.

## 4. Mission library

The home screen is a simple list the founder uses to choose what to film next.

- Each row: mission text, her image thumbnail, a star to favourite, a small "done" tick that shows it has been filmed (local only, resettable).
- Search box, filter chips: All, Favourites, Not filmed yet, plus free-text tags.
- **Shuffle** button picks a random not-yet-filmed mission. **Next / Previous** arrows also work from the camera screen via a small hidden control (section 7).
- **Add mission**: type the mission text, pick her image from the phone gallery (Android photo picker), optionally her mood emoji and her caption, save. Edit and delete existing missions. This is how the founder gets to 100 and beyond without a new APK.
- **Custom one-off**: a "Type a mission now" field at the top that starts the camera immediately with that text and a default or randomly chosen woman image from a "default pool" (see section 5).
- **Bulk import (should have):** the app reads a folder `Android/data/<package>/files/missions/` containing `missions.json` and the image files, so the founder or developer can load 100 missions over USB without typing. Importing merges by mission id and never deletes existing ones.
- Starter content: ship the app with the poses from Final-Plan-Pose-List.xlsx as mission texts (Pose 1 to 365). Missions without an image assigned show a "No image yet" badge in the list and use the default pool until the founder adds one. Any mission text can be changed.

Mission texts are free text of any length up to about 90 characters (the mission bar wraps to two lines).

## 5. Her image (the partner half)

Every mission has its own preset image of the woman doing her version of the mission. The founder supplies these images; the developer does not generate them.

- **Format:** JPG or PNG, ideally 1080 x 951 px. This is landscape, slightly wider than tall (about 1.14 : 1), not portrait, so her face needs clear space on both sides. That is exactly one half of the 1080 x 1920 card (the two halves are 951 px each with the 18 px white line between). Anything else is centre-cropped to fill, never stretched. Accept up to 4000 px on the long side and downscale on import.
- **Her image is used three ways, all local:** blurred with a lock on the camera screen, blurred on the Tap to reveal screen, clean on the reveal and the share card. Never mirrored.
- **Her pill (optional, per mission):** her mood emoji and a caption up to 60 characters, shown on the reveal and the card in the same pill style and position as a real partner's ("😊 Happy · Finally home. Pizza night?"). Empty means no pill.
- **Default pool:** the founder can mark any number of images as "default pool". A mission with no image of its own, and every one-off custom mission, picks one at random from the pool, avoiding repeating the last 3 used.
- **Her avatar** (the small circle with the green tick on the Tap to reveal screen and on the lock panel) is set once in the Studio panel (section 7). If not set, use a centre-top crop of her current image.

## 6. Reveal behaviour that differs from the real app

| Real app | Marketing build |
| -------- | --------------- |
| Partner photo arrives from the relay after she sends | Her image is already on the phone, loaded the moment the mission starts |
| Reveal is unlocked only after both send | Reveal is available the instant he taps Send |
| Next pose unlocks at 3AM | Next mission is one tap away, always |
| Day N comes from the relationship start date | Day N is a number set in the Studio panel (section 7) |
| Header says "Next pose at 3AM" | Keep the same header text so the video matches the real app |
| Photos persist for 14 days for Free | Nothing persists by default; see section 8 |

## 7. Studio panel (hidden controls)

A settings sheet opened by a long press (about 1.5 s) on the Mission Studio logo on the home screen, and by a long press on the white-line pill from the camera or reveal screens. It must never appear on screen during normal use, so it does not show up in recordings. Contents:

- **Names:** his name, her name (default "Emma"). Used in all copy ("Emma sent hers", "Nudge" is not needed).
- **Day N** on the pill: a number field, plus "Auto +1 after each reveal" toggle, plus "Random between X and Y" option. Default: 256, auto +1 off.
- **Watermark pill text:** "CoupleIn · Day N" or "N Days of Us".
- **Avatars:** his and hers, from the gallery.
- **Fake send time** on the locked panel ("Send yours to reveal it · 8:14 AM"): Auto (now minus 2 to 20 minutes), or a fixed text.
- **Partner state on camera:** "Emma sent hers" (default) or "Emma hasn't sent hers yet" (the pink gradient state). The reveal works either way.
- **Reveal speed:** Normal (3-2-1, default), or Instant (skips the countdown, straight to the unblur).
- **Show extra buttons after reveal** (Next mission, Replay reveal, Retake this mission): on by default. Turn off to get a completely clean reveal for recording; use the hardware volume-up key as "Next mission" and volume-down as "Replay reveal" when off.
- **Clean mode:** hides the gear icon, and uses Android immersive mode so the status bar and navigation bar are hidden on every screen.
- **Mission notification (should have, extra):** a button "Send mission notification in 5 seconds" that posts a real local Android notification styled like the app's daily push ("Today's mission: [mission text] 📸"), so videos can open on the notification. Uses a local notification only, needs the notification permission, no server.
- **Reset "done" ticks** and **Clear all photos now.**

## 8. Recording-friendly and privacy requirements

- Never set FLAG_SECURE. The system screen recorder must be able to capture every screen, including the camera preview.
- Keep the screen on while the app is open. Lock to portrait.
- No debug overlays, toasts or loading spinners at any point in the loop. Transitions at the same speed as the real app.
- The camera must start in under about 1.5 seconds and never show a permission prompt after the first run.
- His photos are kept in the app cache only and are wiped when the app closes or when the next mission starts. Saved cards (Save to Photos) go to the gallery as 1080 x 1920 PNGs. Option in the Studio panel: "Keep last 20 photos" (default off).
- Our cards button: opens a grid of cards saved this session. Mock content is not needed; if empty show "No cards yet". Not Pro-gated and no lock.
- Camera not mirrored in the saved photo (the live preview may mirror, as in the real app).
- Do not read or send location, contacts or any identifier. No third-party analytics SDKs.

## 9. Data model (all local, on the phone)

`missions.json`, one entry per mission:

```json
{
  "id": "m_0001",
  "text": "Take a picture lying down on your back",
  "image": "m_0001.jpg",
  "herMood": "😊",
  "herCaption": "Finally home. Pizza night?",
  "defaultPool": false,
  "favourite": false,
  "filmed": false,
  "tags": ["lying", "easy"]
}
```

Studio settings stored separately: names, Day N (and auto/random mode), watermark text mode, avatars, fake-time mode, partner state, reveal speed, extra-buttons toggle, clean mode, keep-photos toggle. Use Room or a plain JSON file; no backend.

## 10. Technical notes

- Reuse the Mission screen, camera (CameraX widest front lens), reveal animation, safe-zone card renderer and Save sheet from the main app code so the visuals are identical. If the main app is Flutter or React Native, build this as a second flavour or a separate entry point sharing those widgets, not a rewrite.
- Card export must match the main plan: 1080 x 1920, 18 px white line, centre pill is the watermark, nothing in the top 12%, bottom 22% or right-edge 40% to 78% bands, no mission text on the card, caption and mood pills in the same positions.
- Every Send, reveal and replay must work with the phone in airplane mode.

## 11. Acceptance tests

1. Fresh install, airplane mode on: pick a mission, take a selfie, Send, Tap to reveal, watch 3-2-1, see the revealed screen. No network calls (verify with a network monitor).
2. Do the loop 20 times in a row on 20 different missions with no waiting, no lock and no error.
3. Add a new mission with a gallery image, an emoji and a caption; it appears in the list and in the reveal exactly as entered.
4. Import a folder of 100 missions with images over USB; all 100 appear, existing missions are untouched.
5. A mission with no image uses the default pool and does not repeat the same image 3 times in a row.
6. Custom one-off mission typed on the home screen starts the camera immediately with that text.
7. Replay reveal plays the full 3-2-1 and unblur again without a new photo. Retake this mission returns to the live camera on the same mission with the mission bar visible.
8. Mission bar disappears the moment the shutter fires or the 5s timer hits zero, is not in the saved photo or card, and returns on Retake.
9. Saved card matches the real app's share card pixel for pixel in layout, safe zones and pill; watermark text follows the Studio setting.
10. Screen recording with the system recorder captures the camera, the reveal and the hearts with no black frames.
11. Studio panel is not visible or reachable by accident during a normal run.
12. With "Show extra buttons" off, volume keys act as Next mission and Replay reveal.
13. Day N auto +1 increments after each reveal; Random mode stays within the set range.
14. Runs on at least three different Android phones (including one older, one with a notch) with correct front-camera field of view.

## 12. Open items for the founder

1. How many mission images will you have at launch? The app works with any number from 1 up, but missions without images share the default pool.
2. Do you want the mission notification button (section 7)? It is the one extra feature beyond what you asked for.
3. Her identity in videos: the woman is staged, not a real partner. If she is AI-generated or a model, confirm you hold the rights to the images, and check each ad platform's rules on staged or dramatised app demos before running these as paid ads.
