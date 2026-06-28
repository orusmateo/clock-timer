# Clock Timer

A visual countdown overlaid on a live analog clock — built so a timer can never quietly run past your next commitment.

## Why this exists

Visual timers make time *perceptible*. For many neurodivergent people — including autistic and ADHD folks — time is not felt as a smooth, trackable quantity: a digit reading *20 minutes* states a number without conveying how much that is or how quickly it is leaving. A shrinking hued area solves this by making duration visible at a glance, which is why tools are widely used for focus, transitions, and self-regulation. But conventional visual timers share a blind spot — the countdown runs on its own dial, divorced from the actual time of day. The timer knows it has twenty minutes left; it has no idea you have a meeting at the top of the hour. This is exactly where time-blindness does its damage: a visual timer can pull you into deep focus on a task whose finish line lands *past* a commitment you have already made, and nothing on the dial warns you. **Clock Timer** closes that gap by drawing the countdown directly onto a live analog clock. Remaining time, elapsed time, and overtime are all rendered against the real position of the hands, so the question *"will this fit before my next thing?"* is answered by looking, not by calculating.

## Reading the dial

The colored disc sits inside the numerals so the clock stays fully legible, and the real minute hand sweeps straight through it:

- **Red** — time remaining (now → end).
- **Grey** — time already spent (start → now). The minute hand is always the boundary between the two.
- **Amber** — overtime. Once you pass the end mark, an amber arc grows and a `+MM:SS` counter shows how far past due you are.
- Small ticks flag the **start** and **end** clock times, and the panel spells them out: *Started 2:15 → ends 2:45*.

Because the timer is pinned to real clock time, the end mark lands on an actual minute on the face — you see *when* it ends, not just how long is left.

## Using it

- **Set** a length with the presets (5–60 min) or by dragging on the clock to the end time you want.
- **Alarm:** choose **Low**, **High** (a Casio-style beep), or **Flash** — a silent mode that pulses the screen instead, kept to a calm ~2 Hz so it stays under the photosensitivity threshold.
- **Stop** silences the alarm; **Reset** clears the timer. The overtime counter keeps running until you reset, so you always know how over you went.

## Install

This is a Progressive Web App. Open the live site and:

- **iPhone / iPad (Safari):** tap **Install**, or **Share → Add to Home Screen**.
- **Android (Chrome):** tap **Install**.
- **Desktop (Chrome / Edge):** click the install icon in the address bar.

It then launches full-screen from its own icon, runs fully offline, and keeps the screen awake while a timer is running.

## Notes for tinkering

The whole app is `index.html` — no build step, no dependencies. When you change it, bump the cache version in `service-worker.js` (`clock-timer-v2` → `v3`) so installed copies pull the update instead of serving the cached version.
