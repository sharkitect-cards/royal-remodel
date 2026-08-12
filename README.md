# Royal Remodel — Daniel Molina

Digital business card. Live at **https://cards.sharkitectdigital.com/royal-remodel/**

Built from `sharkitect-cards/_template` on 2026-08-12 — fourth clean run of the standing
card design standard after Victoria, Maldonado, and NevkaR.

## Files

| File | What it is |
|---|---|
| `index.html` | The card. Self-contained except Google Fonts (Orbitron + Montserrat). |
| `contact.vcf` | vCard 3.0 with embedded photo. **The QR and NFC chip both point here.** |
| `qr-code.png` | 800px on-page QR shown in the modal. Encodes `contact.vcf`, not this page. |
| `logo.png` | 640px crown-and-shield mark, transparent, palette-quantized. Card tile + favicon. |
| `icon-180/192/512.png` | Home-screen icons: the **full logo including the ROYAL REMODEL wordmark**, flattened on `#1A1A1A`. |
| `manifest.json` | Add-to-home-screen support. Installs as "Royal Remodel". |
| `.gitattributes` | `*.vcf -text` — **required.** vCard 3.0 mandates CRLF; without this git normalizes to LF and some phones reject the file. |

### Why two different logo treatments

The card tile and favicon use the **crown-and-shield mark only** — the wordmark is
illegible at 150px and disappears entirely at 16px. The home-screen icon uses the **full
logo with the wordmark**, because that is what identifies the app on a phone screen.
Both are flattened on the brand dark for the icon: iOS ignores alpha on home-screen icons
and would otherwise composite the transparent PNG onto black with no padding.

## Design standard held

- **One button** — "Save My Contact" — opens the QR modal. No `saveContact()`, no direct
  `.vcf` anchor, no separate QR button.
- **Clean palette.** Text is white/neutral. Brand gold appears only on the button, the top
  hairline, the divider crown, and the QR.
- Button text is **navy on gold**, not white — white on gold fails contrast and reads washed.
- Title line is **sentence case and muted** on purpose: name and company are both uppercase,
  so an uppercase title would blur the three lines together.
- **Divider crown** carries the brand's own motif, matching the logo.
- QR is decode-verified with `cv2.QRCodeDetector` at 100%, 40%, and 25% scale.

## Content sourcing

Services and the "Royal Design. Regal Quality." line are **Daniel's own words**, taken
verbatim from the Royal Remodel Instagram bio — not written for him. He does **flooring
and remodeling**, not remodeling alone.

## Fields deliberately omitted, not fabricated

- **Website** — `royalremodelkc.com` returned 404 on 2026-08-11 and again on 2026-08-12.
  A bare `URL:` renders as "homepage" in the saved contact, so it stays out until the site
  is live. Backfill is a two-line edit (`index.html` + `contact.vcf`), not a rebuild.

Everything else on the card is confirmed: phone and email from Daniel directly, title
confirmed by Chris, socials verified (both Facebook share links resolve to the same page;
the X handle is `royalremodelkc`, confirmed by Chris after lookup).

## Not to be confused with

`sharkitect-cards/daniel-molina-c6t` — Daniel's **previous** card from his time at Fantastic
Floors. Retired 2026-08-12: repo archived and its GitHub Pages site deleted. That URL is an
FF-branded asset and was **not** reused here. The other Fantastic Floors cards
(`juan-bernal-74s`, `emmanuel-arizpe-1w1`, `alberto-bernal-p2k`, `angeles-chavez-cano-zwz`)
are untouched and remain live.
