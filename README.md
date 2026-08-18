# The Endless Loading Page

A trap for people using their phones at Burning Man. NFC tags and QR codes
scattered around the event lure them into scanning; this site is what's waiting
on the other end.

## The experience (three acts)

**Act I — The Hook.** An official-looking prize page: "You found it! This tag is
one of ten hidden across the playa. Your prize: 0.1 BTC." Big glowing CLAIM
button. The fine print already gives the joke away, but nobody reads fine print
— which is sort of the whole point.

**Act II — The Slow Burn.** A progress bar that creeps toward 99%, panics, and
falls back — forever. Status messages start plausible ("Verifying blockchain
transaction…") and slowly turn on the reader ("You are AT Burning Man." …
"The progress bar is embarrassed for you."). A timer labeled *time spent
staring at this screen* counts up the whole time. After ~45 seconds of messages
(or an early tap on the "just tell me what's going on" escape hatch) it
transitions to—

**Act III — The Reveal.** "There is no bitcoin." A stats card (Prizes won: 0.
People nearby not looking at a phone: ~69,999.) and their *actual* prize:
permission to put the phone in airplane mode and go be a person. A TRY AGAIN
button that only ever produces escalating refusals, and eventually gives up on
them entirely.

**Repeat offenders.** Visits are counted in localStorage. Scan a second tag and
the hook page drops the pretense: "You scanned another one. The prize is still:
fake."

## Design constraints

- **One file, zero external requests.** Cell service at Black Rock City is
  somewhere between bad and theoretical. The whole site is a single 12KB
  `index.html` — no fonts, images, or CDN anything.
- **Dark, warm palette.** Easy on eyes (and batteries) at night, readable in
  daylight, and it looks like the desert.
- **Mobile-first.** It will only ever be viewed on a phone, by definition.

## Deploying

Any static host works — GitHub Pages, Cloudflare Pages, Netlify. Then:

1. Get a **short** URL (short = smaller/denser QR code = scannable from further
   away, and fits on cheap NTAG213 NFC stickers).
2. Write the URL to NFC stickers (any NFC-writer phone app) and generate QR
   codes pointing at it.
3. For extra pull, label the physical tags with something irresistible:
   "SCAN FOR PRIZE", "DO NOT SCAN", or just a mysterious "7/10".

## Local preview

```sh
open index.html
```
