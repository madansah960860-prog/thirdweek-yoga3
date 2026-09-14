# Stillform — brand and design reference

*Yoga, plainly taught.*

This file records the rebrand so the site stays consistent. It replaces the
previous "Nine Breaths / Ink & Signal" identity entirely.

---

## 1. The name

**Stillform.** One word, capital S, no space, no hyphen. Never "StillForm",
"Still Form" or "stillform" mid-sentence.

In the wordmark the two halves are set differently, so the markup is always:

```html
<a class="wordmark" href="index.html">Still<span>form</span></a>
```

The `<span>` carries the clay colour and the italic. Do not change that markup.

**Why the name.** *Still* is the state the practice is aiming at. *Form* is the
shape you are actually holding. The site teaches the second in service of the
first, and says so plainly.

---

## 2. Voice

Warm, grounded, unhurried, concrete, quietly confident.

- Second person. Short declarative sentences.
- Give the number, not the adjective: "hold for five breaths", not "hold for a
  good while".
- Name the joint, the prop, the direction, the minute count.
- Say what the thing costs and who pays for it.
- If a sentence would sound strange said out loud by a teacher at the front of
  a room, rewrite it.

**Never:** exclamation marks, hype, "unlock", "journey", "transform your life",
"game-changer", mystical filler, fake urgency, or health claims. This site
publishes general movement education, not medical advice, and the copy never
blurs that line.

---

## 3. Colour — "Warm Clay"

| Token | Value | Role |
|---|---|---|
| `--shell` | `#FAF6F0` | Page ground (warm bone) |
| `--shell-deep` | `#F2EAE0` | Tinted bands, rails |
| `--shell-warm` | `#F6EFE6` | Secondary warm fill |
| `--surface` | `#FFFFFF` | Cards, panels |
| `--ink` | `#1C1714` | Body text (warm near-black) |
| `--ink-soft` | `#332B25` | Lede, secondary text |
| `--ink-muted` | `#6B5F55` | Captions, meta |
| `--clay` | `#A34528` | **Primary brand + CTA** |
| `--clay-deep` | `#7C3119` | Hover, pressed |
| `--clay-soft` | `#F7E7DF` | Tints, selection |
| `--clay-line` | `#E4C6B8` | Outline-button border |
| `--moss` | `#3C5A46` | **Secondary** |
| `--moss-deep` | `#2A4132` | Inverted bands (`.section--ink`) |
| `--moss-soft` | `#E4EBE4` | Moss tint |
| `--amber` | `#C8891C` | Ornament only |
| `--amber-text` | `#7E560F` | Amber-family colour that may carry words |
| `--danger` | `#9B2C1B` | Form errors |

**Rules.** Amber never carries small text — use `--amber-text` when it must.
Hairlines are warm (`rgba(28,23,20,…)`), never cool grey. All body text clears
WCAG 2.1 AA; large text clears 3:1. The measured ratios live in the header
comment of `assets/css/main.css` and must be re-checked if a value moves.

---

## 4. Type

| Role | Family | Notes |
|---|---|---|
| Display | **Fraunces** | Optical-sized serif. Headings, `.lede`, `.pull`, `.stat__num`. Tracking about `-0.015em` — a serif does not want the tight grotesque tracking. |
| Body | **Karla** | 17.5px / 1.7. Humanist, warm, highly legible at length. |
| Label | **DM Mono** | Uppercase, `0.16em` tracking. `.eyebrow`, `.label`, `.section__index`, step numerals, spec keys. |

Loaded from Google Fonts with `display=swap`; every family has a real fallback
stack. The previous Bricolage Grotesque / Public Sans / JetBrains Mono trio is
retired and must not reappear.

---

## 5. Shape language

The redesign is built on **arches and warm hairlines**, replacing the old sharp
3px-corner editorial look.

- **The arch is the brand shape.** `.hero__media img` carries a tall arched top
  (`border-radius: 200px 200px 22px 22px`). The logo is the same arch.
- Radii: `--radius: 14px`, `--radius-lg: 22px`, `--radius-pill: 999px`.
- Buttons are pills. Cards are soft rectangles with a warm hairline and a low,
  wide shadow.
- Shadows are warm and diffuse, never grey drop-shadows.
- `.section--ink` is deep moss, not near-black.
- Focus is always visible: 2px `--clay` outline at 3px offset. Never removed.

---

## 6. The mark

`assets/img/brand-mark.png` (512), `apple-touch-icon.png` (180),
`favicon-32/16.png`, `favicon.ico`, `brand-card.png` (1200×630).

A clay arch with an inner aperture, sitting on a moss ground line, on shell.
It reads as a doorway and as the arch of the hero image. The favicon sizes drop
the aperture for legibility at 16px. Regenerate from the script in the session
scratchpad if sizes are ever needed beyond these.

---

## 7. Two brand components

Added in this rebrand and available on every page:

```html
<blockquote class="pull">
  <p>One strong sentence that earns its size.</p>
  <cite>Attribution or source line</cite>
</blockquote>

<ul class="note-strip">
  <li><strong>Label</strong> One short sentence.</li>
  <li><strong>Label</strong> One short sentence.</li>
  <li><strong>Label</strong> One short sentence.</li>
</ul>
```

`.pull` is the editorial pull-quote. `.note-strip` is the three-up fact row —
use it for at-a-glance facts (breath, hold, prop; or duration, difficulty,
kit). Both work inside `.section--ink`.

---

## 8. Facts the copy must keep straight

- Free to read. No account, no paywall, and nothing free today moves behind one
  later.
- Membership: **$6 / month or $54 / year USD**. It removes ads and adds
  downloadable sequence PDFs, saved collections and printable pose cards. It
  never paywalls instruction that was previously free.
- Funding: display advertising, optional membership, affiliate commissions,
  paid downloads, and labelled sponsored posts. Disclosed at the link, not only
  in the footer.
- Newsletter: **The Slow Start**, weekly, Monday mornings, free, one-click
  unsubscribe, sender name and postal address on every send.
- Every pose and every sequence carries a chair, wall or block path.
- Business details: Stillform, 812 Alder Street, Studio 4, Portland, OR 97205,
  United States. `hello@stillform.co` · +1 (503) 555-0179 · stillform.co
  *(placeholder details — replace with verified information before launch).*

---

## 9. Hard constraints for future edits

The site is 37 hand-written HTML pages sharing one stylesheet and one script,
with no build step. Class names, `id`s, `data-*` attributes, form field names
and `aria-*` values are load-bearing — `assets/js/main.js` reads them for the
breath pacer, the pose-library filters, the sequence timer, the FAQ accordion,
the cookie consent and form validation. Re-skin and rewrite freely; do not
rename a hook.
