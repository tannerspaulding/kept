# Kept

A slower channel for the words worth keeping.

Texts are built to be disposable. Some words are meant to be held. In Kept, the sender writes once. Kept composes how it plays: the pacing, the type, the imagery and a score. The receiver unseals it and watches it play slowly, with sound. It's digital, but it should land like a handwritten note: felt, experienced, something to keep. Letters can also be ordered as printed keepsakes.

Owner: Tanner. Designer and collaborator: Ben Fogarty (high-end UI/UX). The prototype is for Ben and others to try on a phone.

## Where things stand

- `index.html` is a working single-file prototype (vanilla JS, no build). It is live on GitHub Pages at https://tannerspaulding.github.io/kept/.
- A claude.ai artifact copy of the same page also exists. That copy uses the claude.ai `sample` capability for AI composing. Here on Pages there is no AI, and the rule-based composer runs instead.
- Tanner's feedback on v1: "not terrible, but not amazing, a little clunky". The invented home screen, a landing-page-style list of cards, was cut. The app now opens straight into the sealed letter.

## Taste: non-negotiables

- Printed, tactile, never sterile. Paper texture should be very light and real, not a noisy filter.
- Type is the image. Large Fraunces set like a film title, not UI text. Use impactful imagery, not plain single-word type.
- Sound is organic and cinematic: rain, breath, felt piano, low strings. No chimes, no UI blips, nothing kitsch.
- Slow by design. Nothing pops. Things arrive, settle and fade.
- One accent color (ember). Restraint over decoration.
- Phone-first and native-feeling: full-bleed, safe areas respected, hold gestures, and no web-page chrome or scrollbars.

## Design tokens (from the concept deck)

- Ink `#100F0E`, ink2 `#1A1816`, char `#1B1917`
- Paper `#F3EEE6`, bone `#EEE7DB`
- Ember `#CE8B58`, ember-deep `#A8622F`
- Muted on dark `#A69D90`, muted on light `#6A635A`
- Line on dark `#3A3631`, line on light `#D6CCBE`
- Fonts: Fraunces (300 for display and italic ledes) and Inter (UI, tracked uppercase eyebrows)
- Mark: an arc with a dot under it, like a light over a horizon. SVG: `M5 21.5A15 15 0 0 1 35 21.5` plus a circle at (20, 17.5) with r 3.4, in a 40×24 viewBox.

## The flows

**Sender**
1. Write: To, From, the message. Dictation is optional.
2. Kept composes: beats, styles, look, score. The sender's words are never changed.
3. Preview the composed piece. Nudge it with Warmer, Quieter, Simpler or Try another.
4. Deliver: choose when it opens (Now, Tonight, Tomorrow morning) and set toggles for headphones and reply-in-kind.
5. Hold to seal. This produces a link.

**Receiver**
1. A lock-screen-style notice: "Iris sent you something to hear slowly."
2. Cover: "A Kept message from Iris", concentric rings of the letter's phrases, "For Jonah". Hold the light to open.
3. Full-screen paced playback with the score. Tap to pause.
4. End screen: Replay, Keep it (to the shelf), Answer in kind (compose back), Print it (an 18×24 poster).

## Beat styles

- `name`: the opening address
- `plain`
- `weight`: the last word lands huge
- `drop`: the last word falls small, lower right
- `list`: comma items appear one by one
- `echo`: the whole letter shimmers as a mosaic and the arc mark lights up in it
- `whisper`
- `close`: the final line, with its key phrase glowing

## Looks and scores

- Vesper ("Slow, low light"): the score is Low Tide, with rain and felt piano.
- Dawn ("Morning paper, open air"): the score is First Light, with breath and a string pad.
- Hearth ("Close and warm"): the score is Low Ember, with a low drone and piano.

All sound is synthesized in Web Audio: a convolver reverb and filtered noise beds.

## Demo letter (keep it preloaded)

From Iris to Jonah:

> Jonah, I've started this text a dozen times. Every version was too small. So I'm saying it slower. This year was heavy. You carried more of it than you ever let me see. The early trains, the late dinners, the porch light still on. I noticed. I noticed all of it. Thank you. I'd choose you again, every single time.

## Delivery today

The whole letter is compressed into the URL hash (`#kz…`, deflate-raw then base32), so there is no server. The shelf, sent and received lists live in localStorage on each device.

Real delivery would need a backend: short links, an inbox, push notifications, and AI composing with the API key kept server-side. Vercel plus a small database is the likely next step.

## Working rules

- Keep it deployable as a static site unless a change truly needs a server. If you add one, say so and explain why.
- Never ship an API key in client code.
- Test at phone width (390×844) and in the iOS Safari standalone mode.
- Commit messages describe what a person would notice.
