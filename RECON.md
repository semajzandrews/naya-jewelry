# RECON — Naya Jewelry

Single-file BWYW pre-built landing page (REVIEW stage). Not deployed.
Output: `builds/naya-jewelry/index.html` (self-contained, ~38 KB, opens in a browser as-is).

---

## Verified facts (only these used)

| Field | Value |
|---|---|
| Legal name | Naya Jewelry Corporation |
| Display name | Naya Jewelry |
| Category | Jewelry store |
| Address | 195 Main St, City of Orange, NJ 07050 |
| Phone | (973) 675-1234  (`tel:+19736751234`) |
| Rating | 3.5 stars, 4 Google reviews |
| Hours | Sun 9:30 AM – 4 PM · Mon–Sat 9:30 AM – 6 PM |
| Map | `https://www.google.com/maps?q=195+Main+St,+City+of+Orange,+NJ+07050&z=16&output=embed` |
| Socials | None verified — omitted (no handle provably this business). |

**Review handling:** review count is tiny (4), so the page deliberately does NOT lean on
review volume. No star widgets, no "rated X by Y customers." Trust is carried by craftsmanship
language (heirloom, hand-checked, custom design, honest repairs) and the neighborhood-jeweler
positioning instead.

**Language:** `lang="en"`. No verified-facts signal of a Spanish-first clientele for this
specific jeweler, so English-primary. No machine-translate toggle added (per language-strategy
rule: only add a vetted toggle, never browser/Google auto-translate).

---

## Art direction (mine)

- **Concept:** "quiet luxe" neighborhood jeweler. Heirloom over flash. The line is
  *"Where gold is kept, not just bought."*
- **Palette:** obsidian / near-black (`#0b0b0d`) ground, warm gold (`#c79a4b` → soft `#e2bd76`),
  ivory (`#f4efe6`) and warm mist for body text. Precious, restrained, lots of negative space.
- **Type pairing (new, not reused in registry):**
  - Display: **Boska** (Fontshare) — an elegant high-contrast serif, italic used for accent words
    ("kept", "story", "everyday", "making by hand").
  - Body/UI: **Satoshi** (Fontshare) — clean geometric sans.
- **Custom brand mark:** a hand-drawn hexagonal faceted-gem monogram (inline SVG, two-tone gold
  strokes + a center brilliant) — not a library/icon-font default. Reused in nav + footer.

## Signature interaction (assigned: parallax shimmer + spotlight-on-hover; NOT horizontal scroll)

1. **Parallax shimmer hero.** On scroll the hero image translates (parallax) while a diagonal
   screen-blend light band sweeps across the metal/stone so "light catches the metal as you
   scroll." `requestAnimationFrame`-throttled, transform-only (no filters), reduced-motion safe.
2. **Spotlight-on-hover product grid.** Each featured piece brightens and lifts on hover, a
   radial spotlight follows the cursor (`--mx/--my`), and a one-shot diagonal **gleam sweep**
   crosses the photo. Keyboard-focusable (`tabindex="0"`).

## Sections

Top nav (brand mark + section links + persistent call CTA, collapses to a 44px gold call icon
under 640px) → parallax-shimmer hero → marquee service strip → featured-pieces grid w/ spotlight
hover → "Custom & Repairs" trust section (4 numbered services) → Visit: live Open/Closed pill +
12-hour hours table (today's row highlighted) + keyless Google Maps embed → CTA band → footer
(name, address, phone, hours, CTA, "Built by bysemaj.com" credit).

## Imagery (Pexels direct URLs — all verified to load, all visually confirmed, none reused)

| Slot | Pexels ID | Subject |
|---|---|---|
| Hero | 2735970 | Diamond stud earrings on raw dark stone |
| Collection · The Solitaire | 691046 | Diamond solitaire + band on ivory |
| Collection · Worn Every Day | 1454171 | Gold beaded necklace + bracelet on model |
| Collection · Blue Topaz | 5370706 | Two blue-topaz rings on dark reflective surface |
| Collection · The Halo | 1232931 | Halo diamond ring in a red rose |
| Collection · The Eternity Band | 998521 | Rose-gold diamond band on dark glass |
| Collection · Made to Be Passed Down | 248077 | Gold wedding bands + olive-leaf crown |
| Custom & Repairs figure | 1721937 | Pearl + gold earrings held in an open palm |
| CTA band background | 1457801 | Two-stone gold diamond ring on dark slate |

Every image was opened and eyeballed before use (Pexels IDs are unreliable; an early pick that
turned out to be a shutter / a medical / a sock-box shot was rejected). All 9 confirmed unique
and category-true. Replace with the shop's own photos before any public launch.

## Compliance check (BUILD_RULES)

- [x] Real per-brand nav bar w/ brand mark + links + persistent call CTA; collapses cleanly < 375px
- [x] Footer: name, real address, real phone, hours, CTA, tasteful `bysemaj.com` credit (linked)
- [x] 12-hour time everywhere; live Open/Closed pill computed in `America/New_York`
- [x] Zero em dashes in any copy (incl. `<title>` and iframe title); en dash only for time ranges
- [x] No image reused; every photo reads as fine jewelry
- [x] Keyless Google Maps embed on the real address (Ramos pattern); URL resolves 200 and
      geocodes to "195 Main / City of Orange" (verified via curl; blank tile in preview MCP is the
      documented sandbox artifact, renders in real Chrome)
- [x] Mobile-first, no horizontal scroll at 375/396px (`scrollWidth === clientWidth`), smooth
      in-page scroll, reduced-motion fallback
- [x] Semantic landmarks, real alt text, focus-visible states, AA-minded gold-on-obsidian contrast

## Verification notes

- Served locally on :4571, audited live in the preview browser at ~396px.
- All 9 images load (`naturalWidth > 0`), IDs unique, no duplicates.
- No console errors. Status pill computed live ("Closed · opens tomorrow 9:30 AM" on a
  Wed evening, matching Mon–Sat 9:30–6).
