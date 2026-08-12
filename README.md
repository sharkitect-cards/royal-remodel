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
| `logo.png` | 640px crown-and-shield mark, transparent, palette-quantized. Also the PWA icon. |
| `manifest.json` | Add-to-home-screen support. |
| `.gitattributes` | `*.vcf -text` — **required.** vCard 3.0 mandates CRLF; without this git normalizes to LF and some phones reject the file. |

## Design standard held

- **One button** — "Save My Contact" — opens the QR modal. No `saveContact()`, no direct
  `.vcf` anchor, no separate QR button.
- **Clean palette.** Text is white/neutral. Brand gold appears only on the button, the top
  hairline, the divider crown, and the QR.
- Button text is **navy on gold**, not white — white on gold fails contrast and reads washed.
- **Divider crown** carries the brand's own motif, matching the logo.
- QR is decode-verified with `cv2.QRCodeDetector` at 100%, 40%, and 25% scale.

## Fields deliberately omitted, not fabricated

- **Website** — `royalremodelkc.com` returned 404 on 2026-08-11 and again on 2026-08-12.
  A bare `URL:` renders as "homepage" in the saved contact, so it stays out until the site
  is live. Backfill is a two-line edit (`index.html` + `contact.vcf`), not a rebuild.
- **Job title** — never stated by Daniel, so not invented.
- **X / Twitter** — handle unconfirmed (`royalremodel` vs `royalremodelkc`, neither
  resolvable at build time). Omitted rather than guessed.
- **Service specifics** — only "Residential Remodeling" is confirmed. No kitchens/baths/
  whole-home claim until Daniel confirms.

## Not to be confused with

`sharkitect-cards/daniel-molina-c6t` — Daniel's **previous** card from his time at Fantastic
Floors. Retired 2026-08-12. That URL is an FF-branded asset and was **not** reused here.
