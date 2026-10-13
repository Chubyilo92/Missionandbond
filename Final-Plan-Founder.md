# Final Plan: Founder Plan (Mission)

Updated Oct 13, 2026

## 1. Decisions and what was cut

Mission is the hero feature and the growth engine: one pose a day, both partners send, they tap to reveal, a 3-2-1 countdown, and a card worth sharing. Bond (the daily question) is the second free feature. The developer has a separate spec (Final-Plan-Developer.md). This page is yours: marketing, money, risks and what only you can decide.

**Locked**

- One thing a day, every day. A new pose unlocks at 3AM once both have sent the current one.
- Pricing: weekly £5.99, monthly £9.99, yearly £49.99.
- Two free features: Mission and Bond. Calendar, Brownies and Resolve are Pro, shown as locked placeholders with promise lines ("We are a priority.", "Speak their language!", "8 of 10 couples resolve in 5 minutes.").
- Photos stay on the phone. Free users can open the last 14 days. A short-lived relay delivers photos between phones and deletes them.
- First selfie is a hard gate: nobody sees any other screen until it is sent.
- Week 1 video after the 7th completed pair, promised on the first reveal.
- "Who did it better?" is the post button. Each partner taps "Tap to reveal" themselves; the countdown only says "Reveal" then 3-2-1.
- The mission shows only on the camera (Snapchat-style bar) and is never on the card. The watermark is the centre pill: "CoupleIn · Day N" for free, "N Days of Us" for Pro.
- Optional mood emoji and caption on every photo.
- Two Mission nudges a day (9 AM and 6 PM) until the user sends.
- Pro paywall leads with "2 for the price of 1" (depends on Pro being per couple).

**Cut from the MVP**

- Saturday global challenge (too many bugs for a non-core feature). It returns as a social challenge only, see section 2.
- Streaks, mood-only posts, missed-day tiles.
- "Who did it better" voting and scoreboard. Good idea for later.
- "Couple of the week" and any public in-app feed.

## 2. Marketing and viral launch plan

Two growth loops: your absurd videos bring in the first couples, then every shared card and every partner invite brings in the next.

**Your content (from the filming sheet).** Each location (road, roof, bathtub, fridge) is filmed as two rival POVs: "My wife is too competitive" and "My husband made me do this". Add a screen recording of the 3-2-1 reveal and a "5 poses that made us laugh" carousel. Cadence: POV videos 1 a day, screen recordings 2 to 3 a week, carousels 2 a week. Show the countdown in real time, never sped up.

**The Trojan horse.** The absurd poses are the marketing. Stunts such as the road and the roof are fine as your own filmed content with a spotter, as the sheet requires. Keep them out of the in-app pose list: Apple and Google review the app, and a pose that sends people onto a road is the one thing that could get it pulled. Safe-but-absurd poses (floor, fridge, dry bathtub, chair) give the same effect.

**Moves to make**

1. **End every video with the pose name and "Do it with your partner, link in bottom."** Reply to the best stitches and duets with your own.
2. **Saturday as a social hashtag challenge** (no app build). One fixed day, one pose, one hashtag. Anyone does it with their normal daily selfie.
3. **Seed 5 to 10 couple creators from one niche** with overlapping audiences, all posting the same pose within a few hours with the same hashtag and format, so one audience sees it several times. Twenty creators with separate audiences would not look busy.
4. **A landing page per shared card.** Anyone tapping a shared card lands on "Do this pose with someone" with a one-tap store link, not the generic home page.
5. **Write each pose notification as a dare**, for example "Pose 4: kiss while pretending to be asleep."
6. **Make the first 7 poses the funniest and most filmable.** They feed the Week 1 video and set the tone for the habit.
7. **Put the paywall where people are attached:** the watermark switch on Save, the locked tabs, and the day 10 to 13 photo-lock warning. The Week 1 video is not part of the offer for now.
8. **Invite as a curiosity gap.** The invite carries the blurred locked card and the compliment, and says they took a selfie just for the partner.

**Later:** a real "Who did it better?" vote with a scoreboard, and a stake on it (the loser does the dishes).

**Numbers to watch:** share of couples where both partners send each day, partner joined within 48 hours of the invite (this is your second install per user), installs per share, 7-day return, Week 1 video shared. If both-send is under about 30%, fix the format before spending more on reach.

## 3. Economics: pricing, relay cost, what to measure

| Plan | Price |
| --- | --- |
| Weekly | £5.99 |
| Monthly | £9.99 |
| Yearly | £49.99 |

**Relay storage cost** (photos wait in an encrypted temporary store until both partners have sent, then are deleted once both have downloaded, or after 30 days). At 100,000 photos a day, roughly: Cloudflare R2 about $17 a month, Amazon S3 about $95 a month. These are approximations; R2 is the cheaper option.

**Numbers to watch:**

- Share of new users who send the first selfie (the hard gate).
- Share of couples where both partners complete a day.
- Couples reaching the Week 1 video (7th completed pair).
- Paywall views from the Save sheet watermark switch and from locked old cards, and conversion from each.
- Weekly vs monthly vs yearly split.

## 4. Risks

- **Locked old photos:** doing the pose is unlimited and free, and only viewing photos older than 14 days is Pro. Some users may still feel punished when a loved photo locks. Watch conversion from the locked cards in Our cards.
- **Camera effort drop-off:** one pose a day only works if sending feels easy. Watch day 2 to day 7 retention.
- **Privacy promise:** the relay means photos briefly leave the phone. The copy must say this honestly (encrypted, deleted after both download).
- **Unverified claim:** "8 of 10 couples resolve in 5 minutes" is not backed by data yet. Verify before it goes live.
- **Gendered placeholders:** the women/men versions may draw criticism as generalisations. "Prefer not to say" gets a neutral version.

## 5. Open questions and your to-do list

**Open questions (decide with the developer):**

- Is Pro per person or per couple?
- Hard gate: first selfie only, or every day?
- What do points buy, and is there a daily cap? (25 points per photo for now)
- Week 1 video trigger: after the 7th completed pair; partial video on day 10 if slow.

**Your to-do list:**

- Verify the 8 of 10 claim and the invented Resolve timings (1:30 / 1:00 / 1:00 / 1:30).
- Approve the first 7 poses.
- Still to design: invite fork, Week 1 video promise and ready screens, Bond reveal when the partner has not joined.
- Hand the Developer Spec to your developer.
