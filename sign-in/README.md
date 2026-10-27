# Sign-in screen (redesign, Oct 2026)

Replaces the old "Why we ask for your email" screen. The new screen shows the Mission feature before asking people to sign in, because asking for sign-in before users see any benefit is a big ask.

## Platform rule

| Platform | Sign-in options |
| --- | --- |
| Android | Google only |
| iOS | Sign in with Apple **and** Google (Apple requires Sign in with Apple when Google sign-in is offered) |

On iOS the Apple button sits above Google. It is the same size as Google: black on the light screen, white on the dark screen.

## Two layouts (pick one)

| Layout | Android | iOS |
| --- | --- | --- |
| **A · Two phones (light)**: the mission screen and the revealed screen side by side, with "1 You send yours" / "2 Theirs unlocks" labels | `CoupleIn-SignIn-A_Android.png` | `CoupleIn-SignIn-A_iOS.png` |
| **B · Reveal hero (dark)**: one phone showing the revealed screen, a frosted iOS notification "Emma sent hers. Send yours to reveal it.", sign-in in the tabbed bottom sheet | `CoupleIn-SignIn-B_Android.png` | `CoupleIn-SignIn-B_iOS.png` |

Images are 1170 × 2532 (iPhone @3x). Match the layout and spacing.

## Copy

- Headline (both layouts): **One shared mission a day, for you two.** (A also has "Take a selfie. Unlock theirs." above it)
- B sheet tab: "Your first mission"
- Under the buttons: "Email only used to pair you with your partner"
- Legal line: "By continuing, you agree to our Terms & Privacy Policy" (links)

## Build notes

- Use the official Sign in with Apple and Google Sign-In buttons and SDKs. The Google button in the mockups uses the CoupleIn gradient; Google's branding rules may require their standard button style, so check before shipping.
- The phone images are the real Mission app screens (`../images/mission-screens.png`). In the app, export them as static images inside a device frame.
- Motion (optional): phones float slowly; in B the notification slides in and out on a loop.
- Live, editable designs (including an unused option C): https://claude.ai/artifact/3FQZEs7fiVHEXNFcj5AY4A
