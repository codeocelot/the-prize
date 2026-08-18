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
staring at this screen* counts up the whole time, next to an ETA that only ever
gets worse ("about 10 seconds remaining" → "about 2 hours remaining" →
"1 sunset remaining" → "stop checking").

Then the cruelty escalates in stages:

1. **The crash.** Just when the first message wave ends, the transfer dies:
   "Connection lost. Playa dust detected in the blockchain. Transfer suspended
   pending a security review. (The security risk is you.)" — and the victim is
   marched through three security checkpoints:
2. **Hold to verify you're a human (Checkpoint 1 of 3).** Hold a button for six
   seconds. It fails at 93% ("Grip signature: 'desperate.'"), fails again at
   97%, and passes on the third attempt: "Verified: human. Barely." Letting go
   early also counts — "You let go. A robot would never. Start over."
3. **The fun-recognition CAPTCHA (Checkpoint 2 of 3).** A 3×3 emoji grid:
   "Select all squares containing someone having more fun than you." The only
   passing answer is all nine. ("Incorrect. They are ALL having more fun than
   you. All of them." → "ALL. OF. THEM.")
4. **The confession (Checkpoint 3 of 3).** Four checkboxes they must tick
   themselves: "I am on my phone, at Burning Man, on purpose" … "I have chosen
   this instead." The confirm button stays disabled until they've confessed.
5. **The excuse (Checkpoint 4 of 3).** "For the record: why are you on your
   phone right now?" Every radio option earns a retort — "I thought it might
   be important" → *"It wasn't."* The chosen excuse goes on their permanent
   record in the reveal stats.
6. **The begging (Checkpoint 5 of 3 · We Lied).** "Transfers of this size must
   be requested politely." They must type *please* to proceed. Wrong answers
   get coached ("P-L-E-A-S-E. Six letters. You can do this."); "pls" is
   rejected for laziness.
7. **The oath (Final Checkpoint · Probably).** Say out loud: *"I'm sorry,
   sunset. I chose a URL over you."* A fake LISTENING… indicator pulses, then:
   "We didn't hear you." → "Say it with your chest." → "Confession: we're a
   static website. We can't hear anything. But you just apologized to the sky,
   out loud, multiple times — and honestly? That's the most Burning Man thing
   you've done all day."
8. **The boost button.** The transfer resumes ("Attempt 2 of 1") and offers
   "⚡ TAP TO BOOST TRANSFER SPEED." Each tap *lowers* the bar by 2% and earns
   escalating mockery ("Tapping harder does not help. It never has.").
9. **The false summit.** Round two ends with the bar snapping to 100% —
   "Transfer complete! Redirecting you to your prize…" — two full seconds of
   hope, and then—

Every humiliation is tallied and read back in the reveal stats ("Humanity
checks failed: 3 · Self-incriminating boxes checked: 4 of 4 · Times you typed
'please' to a website: 1"). The full ordeal runs 2–3 minutes; every screen has
an escape hatch ("or admit you might be a robot", "I confess nothing", "I will
not beg") that jumps straight to—

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
