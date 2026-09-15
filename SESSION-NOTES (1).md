# McAlpine Family Reunion 2027 — Session Notes

**Deliverables:** `index.html` + `mcalpine-2027-promo.mp4` (**must be uploaded together, same folder**) · `McAlpine_Sponsorship_Agreement.docx`
**Sessions:** 01 (build from mockup) · 02 (aligned to the written prompt) · 03 (real copy installed) · 04 (seal replaced and retreated) · 05 (Itinerary) · 06 (fees & payment policy) · 07 (sponsorship) · 08 (promo video) · 09 (itinerary from video script) · 10 (proofing pass) · 04 (seal rebuilt)

> Read this file before starting new work on this site.

---

## Session 10 — standing instruction + proofing pass

**Standing instruction: correct grammatical errors silently.** No need to itemize each one or ask first. This applies to all supplied copy going forward. Substantive changes — facts, figures, names, tone — still get flagged.

A full proofing pass was run against the rendered page text, not the source, so nothing was assumed.

**One real defect found and fixed:** a stray `>` was rendering as visible text inside event card three. It was left behind by an alt-text edit in session 02 and had survived every screenshot review since, because it sat in a corner of the image area where nothing drew the eye.

Also corrected:

- "Low Country Boil" in the Saturday title against "Lowcountry boil" in its own description — standardized to **Lowcountry**. Note the supplied documents use three spellings between them: "Low Country", "Low-Country", and "low-country".
- "Something For Everyone" → "Something for Everyone" (title-case preposition)
- Missing serial comma in the Thursday rooftop venue list, which the rest of the site uses
- FAQ read "spades and dominoes" where the itinerary reads "Spades and Domino Tournaments" — capitalized for consistency

---

## Session 09 — itinerary rebuilt from the video script

The promo script carried more detail than the itinerary supplied in session 03. The Itinerary section was rebuilt from it: 14 entries became 19.

### Split into finer blocks

Friday's single "1:00–6:30 PM Lunch, Free Time & Happy Hour" became four entries — Lunch (1:00–2:30), Free Time (3:00–5:30), Happy Hour at Myrtle & Rose (5:30–6:30), and travel to the River Street Dock at 6:30. The cruise itself is now 7:00–9:00, which is what the script says; the old block had it starting at 6:30, which was actually the departure time.

Saturday's "5:00–7:00 PM Committee Meeting & Rest" became Committee Meeting (5:00–5:30) and Rest & Prep (5:30–7:00).

### New on the site

- **Saturday 10:00 PM** — City Market and Savannah nightlife, hotel car service, live local jazz. Wasn't on the site at all.
- **Thursday venues named** — Electric Moon Skytop Lounge, Myrtle & Rose, the Bohemian rooftop, the JW Marriott pool lounge, Wet Willie's.
- **Kelly Tours** as Saturday transportation to Forsyth Park.
- **1st Annual** McAlpine Family Reunion Spades and Domino Tournaments.
- **Social media suite** as the location for children's video-game sessions.
- **A.M.E. Zion Church** promoted into the Sunday entry title rather than buried in the description.

### Event title corrected

Per the script's editorial note, the Friday event is titled **"Uninhibited White: An All-White Dinner & Cruise"** — it's the event's name, not a description. Updated on the itinerary and in the FAQ dress-code answer.

### Deliberately not changed

"–late" was kept rather than the script's "–until," matching what was already verified on the site. Hero and About copy were left alone; the script's title cards ("Four Days of Family, Fun, and Fellowship") overlap but don't obviously improve on what's there.

### Flags

1. **The script runs 2:10–2:25. The delivered video file is 3:41 with audio ending at 1:03.** Together with the earlier "2:33" caption, three different runtimes are now in play. The export almost certainly isn't the intended cut.
2. **The script's art direction contradicts the site's.** It calls for elegant documentary footage, ivory and antique-gold, clean serif type, and a warm mature voice — a different world from the electric chartreuse, heavy condensed type, torn edges and grain the site runs on, and from the "youthful and energetic" direction set in session 04. The delivered video actually matches the *site*, not the script. The script's style section appears to be stale.
3. **Typo in the narration:** "Historic Downtown the Savannah." If the voiceover was recorded from this script, it may be audible.
4. **Internal inconsistency:** the Friday 10:00 PM block is headed "Explore City River Street" with City Market visuals, but the narration describes River Street only.

---

## Session 08 — promo video

### The deployment model changed

The site is no longer a single file. `index.html` now references `mcalpine-2027-promo.mp4` as a sibling, so **both files must be uploaded to the same folder** or the video won't play. The video is 8.7 MB; embedding it as base64 the way the images are handled would have pushed the HTML past 12 MB and made the page unusable.

### Two problems found in the source file, one fixed

**Fixed — the file wouldn't stream.** The moov atom (the index a player needs to begin playback) sat at the end of the file, so a browser would have had to download most of 8.7 MB before showing a frame. It was remuxed with `+faststart` to move the index to the front. No re-encode, so no quality loss, same file size.

**Not fixed — the audio stops early.** The video runs 3:41, but the audio track ends at 1:03. The remaining 2 minutes 38 seconds play silent. The slides keep advancing the whole time — Friday, the picnic, the Savannah closer — so this isn't a still end-card, it's most of the video with no sound. That needs fixing in the editor that produced it; nothing can be done to it here.

### On the page

The placeholder frame is gone, replaced by a real `<video>` element with native controls, `preload="metadata"` so the page stays fast, `playsinline` for iOS, and a poster frame pulled from the 3-second mark and embedded as base64. There's a download fallback link for browsers that can't play it.

The frame moved from 16:10 to **16:9**, matching the video's actual 1920×1080.

**The caption said 2:33; the file is 3:41.** Updated. Worth checking which is right — if 2:33 was the intended cut, this may be the wrong export.

### Size

The block is **25% larger**, done by shifting the About row's columns from `1.15fr / .85fr` to `.88fr / 1fr`. Measured: 536px → 671px wide at a 1440px viewport, a 25.2% increase. Enlarging the column rather than scaling the element keeps the video sharp and the text reflowing properly.

---

## Session 07 — sponsorship

### On the site

A **Sponsorship** section sits between Travel and Contact at `#sponsorship`, with the four levels as cards: Tawny Eagle $2,000, Ghana Gold $1,000, Ghana Green $500, Ghana Roots $250. Each carries a color bar drawn from the seal — tawny brown for the eagle, then the Ghanaian gold, green, and black. The rollover and trust language sits below the cards.

The **badge** is in the footer: "Sponsorship provided by McAlpine PLLC," styled as a ticket stub. "Sponsorship" links to the levels section; "McAlpine PLLC" links to www.mcalpinepllc.com in a new tab. Sponsorship was added to the footer nav but **not** the main nav, which the prompt fixes at six items.

**One correction:** the supplied tier name was "Twany Eagle." It's rendered as **Tawny Eagle** — the word appears in the agreement and on the site, so a typo would be costly. Revert if "Twany" was deliberate.

### The agreement

`McAlpine_Sponsorship_Agreement.docx` — one page, US Letter, editable.

Contracting party is A. McAlpine Alston PLLC d/b/a McAlpine PLLC, 112 S. Tryon St., Ste. 1760, Charlotte, NC 28284, described as administering sponsorships for the reunion. Sponsor identification block, the four levels as a checkbox table, then seven clauses: payment, no refunds, use of funds and rollover to 2029 held in trust, recognition, no endorsement, governing law, signatures.

Two clauses were added that weren't in the brief but follow from the facts. **No attorney-client relationship** — the contracting party is a law firm, so the disclaimer belongs in clause 6. And **the recognition license** — sponsors are giving their name and logo for use in reunion materials, so clause 5 grants a limited license and lets them withdraw it for future materials.

Recognition benefits are stated generically ("commensurate with the level selected") because none were specified. If each tier gets particular benefits — logo placement, banquet tickets, program ad size — those should be spelled out.

Not legal advice, and not reviewed by anyone but me.

---

## Session 06 — fees and payment policy

Fees are now a full/partial grid rather than a flat adult/child pair:

| | Full weekend | Partial weekend |
|---|---|---|
| Adults | $250 | $150 |
| Children | $125 | $100 |

**One assumption to confirm:** the supplied line "$150 (Partial Weekend)" carried no adult/child label. It was read as the adult partial rate, which completes the 2×2. If partial weekend is a single flat rate regardless of age, the table needs rebuilding.

The policy paragraph sits in a green panel below the three cards, with the no-refund policy boxed out beside it in its own callout so nobody can miss it before paying. Two FAQ entries were added — installments and refunds — and the cost answer was rewritten to carry all four figures. The old figures ($250/$100) are gone everywhere.

**Three typos corrected** in the supplied paragraph: "beleive" → "believe", "buy-in buy all of us" → "buy-in by all of us", and "must attend" → "must-attend". "McAlpine Family Member" was lowercased to "McAlpine family member" mid-sentence. Restore any of these if they were deliberate.

---

## Session 05 — Itinerary

**Nav label is ITINERARY, not EVENTS.** This overrides the written prompt, which specified EVENTS. Your instruction wins; don't revert it in a later pass. Changed in the nav, the footer nav, the section heading, the anchor id (`#itinerary`), and the three event-card links. The anchor was clicked and verified to land on the section.

**Capitalization corrected.** When the itinerary was first installed in session 03 the event titles were sentence-cased — "Rooftops & local entertainment." Your copy uses Title Case throughout, so all fourteen entries were rebuilt to match exactly: "Rooftops & Local Entertainment," "Old Town Trolley Tours," "Weeping Time Marker," "Spades and Domino tournaments," and so on. Descriptions are verbatim.

**One typographic liberty:** "Forsyth Park – Barbecue/Low Country Boil" uses an en dash where your copy has a hyphen. Say the word and it goes back to a hyphen.

---

## Session 04 — seal rebuilt

**The root cause was a bad measurement in session 01.** I had cut the seal on an assumed centre and radius, both wrong: the centre was off by 6px and the radius 13px too large. That meant the mask sat outside the real ring, catching chartreuse halo all the way round. My session 02 "fix" then recoloured those fringe pixels to flat black, which is what left the ring looking chewed. I was patching a symptom.

Measured properly this time by scanning the artwork radially:

| Feature | Radius |
|---|---|
| Green band with the lettering | to 382 |
| Thin white line | 384–386 |
| Dark outer ring | 388–395 |
| Chartreuse halo begins | 396 |

True centre is (1456.3, 517.5), not (1450, 516).

**The rebuild.** Rather than mask at the edge, the artwork is taken to radius 386 — inside the ragged zone — and the outer ring is redrawn as clean geometry from 386 to 396 in the ring's own sampled colour, anti-aliased. The seal's outer edge is now a true circle rather than a crop of a painted one. The ring also reads slightly thicker, which helps at the 46px header size.

**Halo bleed lifted.** Chartreuse that had bled into the green band was removed. The mask separates chartreuse from gold on the green-vs-red channel relationship — chartreuse has green above red, gold the reverse — so the laurels are untouched. Verified before applying: 1,778 pixels lifted, zero gold pixels, two lettering pixels.

Exported at 700px instead of 560px for sharper rendering.

A transparent source PNG would still be preferable, since it would sidestep the source's compression artifacts entirely. But the edge quality issue is resolved.

### Correction to session 03 notes

Session 03 recorded that provision for elders and children indicated a non-youthful audience. That reasoning was wrong and has been struck. Accessibility and multigenerational provision are simply a family taking care of its people; they say nothing about how the reunion should be promoted. **The standing direction: the substance stays inclusive, the promotional aesthetic stays youthful and energetic.** These are not in tension and should not be traded against each other in future sessions.

---

## Session 10 — standing instruction + proofing pass

**Standing instruction: correct grammatical errors silently.** No need to itemize each one or ask first. This applies to all supplied copy going forward. Substantive changes — facts, figures, names, tone — still get flagged.

A full proofing pass was run against the rendered page text, not the source, so nothing was assumed.

**One real defect found and fixed:** a stray `>` was rendering as visible text inside event card three. It was left behind by an alt-text edit in session 02 and had survived every screenshot review since, because it sat in a corner of the image area where nothing drew the eye.

Also corrected:

- "Low Country Boil" in the Saturday title against "Lowcountry boil" in its own description — standardized to **Lowcountry**. Note the supplied documents use three spellings between them: "Low Country", "Low-Country", and "low-country".
- "Something For Everyone" → "Something for Everyone" (title-case preposition)
- Missing serial comma in the Thursday rooftop venue list, which the rest of the site uses
- FAQ read "spades and dominoes" where the itinerary reads "Spades and Domino Tournaments" — capitalized for consistency

---

## Session 09 — itinerary rebuilt from the video script

The promo script carried more detail than the itinerary supplied in session 03. The Itinerary section was rebuilt from it: 14 entries became 19.

### Split into finer blocks

Friday's single "1:00–6:30 PM Lunch, Free Time & Happy Hour" became four entries — Lunch (1:00–2:30), Free Time (3:00–5:30), Happy Hour at Myrtle & Rose (5:30–6:30), and travel to the River Street Dock at 6:30. The cruise itself is now 7:00–9:00, which is what the script says; the old block had it starting at 6:30, which was actually the departure time.

Saturday's "5:00–7:00 PM Committee Meeting & Rest" became Committee Meeting (5:00–5:30) and Rest & Prep (5:30–7:00).

### New on the site

- **Saturday 10:00 PM** — City Market and Savannah nightlife, hotel car service, live local jazz. Wasn't on the site at all.
- **Thursday venues named** — Electric Moon Skytop Lounge, Myrtle & Rose, the Bohemian rooftop, the JW Marriott pool lounge, Wet Willie's.
- **Kelly Tours** as Saturday transportation to Forsyth Park.
- **1st Annual** McAlpine Family Reunion Spades and Domino Tournaments.
- **Social media suite** as the location for children's video-game sessions.
- **A.M.E. Zion Church** promoted into the Sunday entry title rather than buried in the description.

### Event title corrected

Per the script's editorial note, the Friday event is titled **"Uninhibited White: An All-White Dinner & Cruise"** — it's the event's name, not a description. Updated on the itinerary and in the FAQ dress-code answer.

### Deliberately not changed

"–late" was kept rather than the script's "–until," matching what was already verified on the site. Hero and About copy were left alone; the script's title cards ("Four Days of Family, Fun, and Fellowship") overlap but don't obviously improve on what's there.

### Flags

1. **The script runs 2:10–2:25. The delivered video file is 3:41 with audio ending at 1:03.** Together with the earlier "2:33" caption, three different runtimes are now in play. The export almost certainly isn't the intended cut.
2. **The script's art direction contradicts the site's.** It calls for elegant documentary footage, ivory and antique-gold, clean serif type, and a warm mature voice — a different world from the electric chartreuse, heavy condensed type, torn edges and grain the site runs on, and from the "youthful and energetic" direction set in session 04. The delivered video actually matches the *site*, not the script. The script's style section appears to be stale.
3. **Typo in the narration:** "Historic Downtown the Savannah." If the voiceover was recorded from this script, it may be audible.
4. **Internal inconsistency:** the Friday 10:00 PM block is headed "Explore City River Street" with City Market visuals, but the narration describes River Street only.

---

## Session 08 — promo video

### The deployment model changed

The site is no longer a single file. `index.html` now references `mcalpine-2027-promo.mp4` as a sibling, so **both files must be uploaded to the same folder** or the video won't play. The video is 8.7 MB; embedding it as base64 the way the images are handled would have pushed the HTML past 12 MB and made the page unusable.

### Two problems found in the source file, one fixed

**Fixed — the file wouldn't stream.** The moov atom (the index a player needs to begin playback) sat at the end of the file, so a browser would have had to download most of 8.7 MB before showing a frame. It was remuxed with `+faststart` to move the index to the front. No re-encode, so no quality loss, same file size.

**Not fixed — the audio stops early.** The video runs 3:41, but the audio track ends at 1:03. The remaining 2 minutes 38 seconds play silent. The slides keep advancing the whole time — Friday, the picnic, the Savannah closer — so this isn't a still end-card, it's most of the video with no sound. That needs fixing in the editor that produced it; nothing can be done to it here.

### On the page

The placeholder frame is gone, replaced by a real `<video>` element with native controls, `preload="metadata"` so the page stays fast, `playsinline` for iOS, and a poster frame pulled from the 3-second mark and embedded as base64. There's a download fallback link for browsers that can't play it.

The frame moved from 16:10 to **16:9**, matching the video's actual 1920×1080.

**The caption said 2:33; the file is 3:41.** Updated. Worth checking which is right — if 2:33 was the intended cut, this may be the wrong export.

### Size

The block is **25% larger**, done by shifting the About row's columns from `1.15fr / .85fr` to `.88fr / 1fr`. Measured: 536px → 671px wide at a 1440px viewport, a 25.2% increase. Enlarging the column rather than scaling the element keeps the video sharp and the text reflowing properly.

---

## Session 07 — sponsorship

### On the site

A **Sponsorship** section sits between Travel and Contact at `#sponsorship`, with the four levels as cards: Tawny Eagle $2,000, Ghana Gold $1,000, Ghana Green $500, Ghana Roots $250. Each carries a color bar drawn from the seal — tawny brown for the eagle, then the Ghanaian gold, green, and black. The rollover and trust language sits below the cards.

The **badge** is in the footer: "Sponsorship provided by McAlpine PLLC," styled as a ticket stub. "Sponsorship" links to the levels section; "McAlpine PLLC" links to www.mcalpinepllc.com in a new tab. Sponsorship was added to the footer nav but **not** the main nav, which the prompt fixes at six items.

**One correction:** the supplied tier name was "Twany Eagle." It's rendered as **Tawny Eagle** — the word appears in the agreement and on the site, so a typo would be costly. Revert if "Twany" was deliberate.

### The agreement

`McAlpine_Sponsorship_Agreement.docx` — one page, US Letter, editable.

Contracting party is A. McAlpine Alston PLLC d/b/a McAlpine PLLC, 112 S. Tryon St., Ste. 1760, Charlotte, NC 28284, described as administering sponsorships for the reunion. Sponsor identification block, the four levels as a checkbox table, then seven clauses: payment, no refunds, use of funds and rollover to 2029 held in trust, recognition, no endorsement, governing law, signatures.

Two clauses were added that weren't in the brief but follow from the facts. **No attorney-client relationship** — the contracting party is a law firm, so the disclaimer belongs in clause 6. And **the recognition license** — sponsors are giving their name and logo for use in reunion materials, so clause 5 grants a limited license and lets them withdraw it for future materials.

Recognition benefits are stated generically ("commensurate with the level selected") because none were specified. If each tier gets particular benefits — logo placement, banquet tickets, program ad size — those should be spelled out.

Not legal advice, and not reviewed by anyone but me.

---

## Session 06 — fees and payment policy

Fees are now a full/partial grid rather than a flat adult/child pair:

| | Full weekend | Partial weekend |
|---|---|---|
| Adults | $250 | $150 |
| Children | $125 | $100 |

**One assumption to confirm:** the supplied line "$150 (Partial Weekend)" carried no adult/child label. It was read as the adult partial rate, which completes the 2×2. If partial weekend is a single flat rate regardless of age, the table needs rebuilding.

The policy paragraph sits in a green panel below the three cards, with the no-refund policy boxed out beside it in its own callout so nobody can miss it before paying. Two FAQ entries were added — installments and refunds — and the cost answer was rewritten to carry all four figures. The old figures ($250/$100) are gone everywhere.

**Three typos corrected** in the supplied paragraph: "beleive" → "believe", "buy-in buy all of us" → "buy-in by all of us", and "must attend" → "must-attend". "McAlpine Family Member" was lowercased to "McAlpine family member" mid-sentence. Restore any of these if they were deliberate.

---

## Session 05 — Itinerary

**Nav label is ITINERARY, not EVENTS.** This overrides the written prompt, which specified EVENTS. Your instruction wins; don't revert it in a later pass. Changed in the nav, the footer nav, the section heading, the anchor id (`#itinerary`), and the three event-card links. The anchor was clicked and verified to land on the section.

**Capitalization corrected.** When the itinerary was first installed in session 03 the event titles were sentence-cased — "Rooftops & local entertainment." Your copy uses Title Case throughout, so all fourteen entries were rebuilt to match exactly: "Rooftops & Local Entertainment," "Old Town Trolley Tours," "Weeping Time Marker," "Spades and Domino tournaments," and so on. Descriptions are verbatim.

**One typographic liberty:** "Forsyth Park – Barbecue/Low Country Boil" uses an en dash where your copy has a hyphen. Say the word and it goes back to a hyphen.

---

## Session 04 — the seal

**Correction carried forward:** provision for elders and children is not an audience signal, it's a family looking after its people. A reunion can be promoted with real energy and still have a ramp at every venue. Those two things were wrongly treated as a tradeoff in session 03's notes. Standing position: **substance stays inclusive, promotional layer skews young.** The electric palette, torn edges, ticket stubs and grain already carry that; no copy was softened.

### New source file

`McAlpine_Crest__Chat_2_.png` replaced the version cut from the flattened mockup. Two things were corrected on the way in:

1. **The original is not circular.** The artwork measures 1104 × 1078 — a slight vertical squash. It was resampled to a true circle, so the ring no longer reads subtly oval at large sizes.
2. **Clean die-cut.** The file has no alpha, so the seal was masked at its outer edge with a 4× supersampled circle. No chartreuse fringe, no pixel surgery on the rim, no compression artifacts. The artwork's own thin white outer margin was kept — it gives the seal a die-cut sticker edge that holds up on any background.

Resolution went from 560px to 640px, and the header and footer marks improved for free since they use the same asset.

### Treatment reworked

| Was | Now |
|---|---|
| Blurred radial gradient halo | Flat chartreuse disc with a 2px black keyline, plus a soft neon spill behind it |
| Heavy green drop shadow | Removed — the keyline does the separating |
| Scale + 6° rotate on load | Fade with a slight scale, no rotation |

The disc reads as a deliberate collar rather than a glow cloud, and the keyline ties it to the black outlines already on the ticket stubs, icon circles and location strip. The prompt's requirement for an electric neon-green halo is still met, and no detail inside the seal is obscured.

The seal's size now belongs to its container rather than the image, so the responsive caps are cleaner: 560px desktop, 430px tablet, 290px phone.

---

## Session 03 — real copy installed

The actual site copy was supplied and every invented word was replaced. Nothing on the page is now fabricated except where explicitly marked "coming soon."

**On the held audience question** — see the correction in Session 04. The content serves every generation; the promotional layer stays energetic. Both, not either.

### Section by section

| Section | Now holds |
|---|---|
| Hero | "A family weekend in Savannah" eyebrow; real lede naming Historic Downtown |
| About | "Meet us in Savannah" preview section, with a video placeholder |
| Events | The full four-day itinerary, verbatim from your copy |
| Travel | JW Marriott, $249/night, both room types, reunion fees, travel notes |
| FAQ | Six questions answered **only** from facts in your copy |
| Contact | "Make your plans official" with the three action links |

### Removed as fabricated

Every invented committee name and email address. The made-up prices ($175/$95 — the real figures are $250 and $100). The 1972 founding date, "6 generations," and the three-sisters origin story. My interpretation of what the crest symbols mean. The old itinerary in its entirety. The `mailto:` RSVP button, which pointed at an address that doesn't exist.

### Needs your input

1. **The preview video.** Your copy says 2:33 with sound on. There's a placeholder frame with a play button and a "video coming soon" tag. Send the file or a hosting link and it drops in.
2. **Committee contact details.** Your copy has none, so the site says contact details will be added here. No names or addresses were invented this time.
3. **Two links are dead.** The AllEvents link went to the site's homepage rather than your event, and the payment link was a temporary Manus sandbox URL that will stop working. Both render as "Coming soon" tags rather than broken links. The JW Marriott link is real and live.

### Kept from the prompt over the real copy

The three event card titles (ROOFTOP HOPS, RIVER STREET CRUISE, FORSYTH PARK PICNIC) and their supporting lines are exact strings the prompt requires, so they stayed as-is. They map cleanly onto the real schedule anyway — Thursday's Electric Moon rooftop, Friday's Georgia Queen cruise, Saturday's Forsyth Park barbecue. The hero button also stays "PLAN THE WEEKEND" rather than your "Explore the weekend," per the prompt.

One detail worth noting: your copy puts the group photo at the Forsyth Park fountain. That raises the stakes on getting a real Forsyth Fountain photograph for card three.

---

## Session 02 — resolving prompt vs. site divergences

The written prompt for the mockup was supplied and the site was reconciled against it. Eight divergences closed, four blocked on source material, one held for a decision.

### Closed

**Nav label.** ITINERARY → **EVENTS** throughout: nav, footer nav, section heading, anchor id, and all three event-card links.

**Header wordmark.** Was `McALPINE 2027`. Now reads **McAlpine** — capital M, lowercase c, capital A, as the prompt requires. The lowercase c carries the specified subtle treatment: slightly reduced size, marginally raised, with a short chartreuse underline. It is not merged with the M, not cut, not decorative, and reads as a c at normal size. The year was dropped; the prompt didn't ask for it. The wordmark now shows at all widths, not just mobile.

**Hero headline.** Line one is now **MCALPINE** in full caps. Note this deliberately differs from the header wordmark, which is mixed case — that split is what the prompt specifies.

**Palette** rebuilt to the prompt's spec. Background is now true white; the warm off-white band (`#F1F1EC`) that read faintly beige is gone, replaced by hairline rules between white sections. Near-blacks lost their green tint. Emerald was electrified. Gold `#F2B417` was replaced with electric orange.

**Missing visual vocabulary** added: the three date tags are now serrated ticket stubs rather than plain rectangles; card photos have torn-paper bottom edges; thin black outlines were applied to the date tags, icon circles, location strip, and travel and fact boxes; a flat print-grain layer sits over the page at ~5% opacity.

**Hero right panel** split into the two separate images the prompt calls for: the riverboat on the left, the JW Marriott Plant Riverside rooftop pool immediately to its right, matched to a shared height. The pool image reads correctly — JW Marriott signage, cabanas, lounge chairs, turquoise pool, riverfront view — and is not a generic resort pool.

**Seal rim.** The lime fringe left over from cutting the seal out of the flattened mockup was removed by detecting chartreuse pixels on the outer rim and folding them into the black ring. Rim is clean now. A transparent source file would still be better.

**Purple removed.** A targeted correction neutralises violet and magenta casts — pixels where blue sits above green — while leaving genuine warm sunset tones alone. Applied to the riverboat in both the hero and card two. This satisfies the prompt's ban on purple.

### Also changed

A green diagonal wedge behind the seal was removed. Once the surrounding elements were tightened it read as a stray triangle in the gap rather than as a design element.

### Blocked — these need real photographs

The mockup is the only image source available, and it cannot supply what the prompt demands:

1. **Forsyth Fountain.** The prompt's strictest requirement — middle third of the card, uncropped, unmistakably Forsyth. The mockup's fountain is not a faithful Forsyth Fountain to begin with, and the card crop slices the basins top and bottom. Needs a real photograph.
2. **Georgia Queen.** The prompt wants a white multi-deck riverboat. The mockup's vessel is red-lit; the purple was removed but the red is the illustration's own lighting, and washing it out looks worse without making the boat identifiable. Needs a real photograph.
3. **Rooftop lounge seating.** The prompt asks for lounge seating and nightlife energy. The mockup shows only a distant skyline.
4. **Card image height.** The mockup contains roughly 85px of actual photography per card above the baked-in text; below that is the dark panel. Cropping taller yields more dark overlay, not more photo. Taller card images require new photography.

**What to supply:** landscape photographs, at least 1600px wide, one each for Forsyth Fountain, the Georgia Queen, and a Savannah rooftop bar. Card image areas can then be made substantially taller.

### Held for a decision — audience and copy

The prompt targets attendees in their twenties with nightlife-guide energy. The existing copy runs the other way: elders' welcome reception, family worship service, six generations, children's rates, a wheelchair-access FAQ. Under the prompt, most written content below the hero would be rewritten and the accessibility and elder content would come out.

This was left as-is, because it may be the one place the prompt misdescribes the actual reunion. Say the word and it gets rewritten.

---

## Design system

**Colors** — sampled from the seal, then electrified per the prompt:

| Token | Hex | Used for |
|---|---|---|
| `--paper` | `#FFFFFF` | Page background |
| `--ink` | `#101010` | Body text, "REUNION 2027", outlines |
| `--panel` | `#0A0A0A` | Event cards, Events and Contact bands |
| `--forest` | `#0BA24F` | Electric emerald — display type and fills |
| `--forest-deep` | `#06703A` | Small emerald text, where contrast is needed |
| `--lime` | `#D3FA4A` | Location strip, date stubs, icon circles, RSVP panel |
| `--red` | `#F81F1A` | Primary buttons, ticket stamp, diagonal accent |
| `--orange` | `#FF6A00` | One small accent only |

Two shape tokens, `--torn` and `--stub`, hold the torn-paper and ticket-stub clip paths so those edges stay consistent wherever they're reused.

**Type** — three faces from Google Fonts: **Anton** (display headlines, card titles), **Montserrat** (nav, body, labels), **Caveat** (the handwritten Hostess City line only).

**Rules of thumb:** display headlines are uppercase; lime is for highlights, never body text; red means "do this"; white and near-black bands alternate so no two adjacent sections match.

---

## Session 01 — the original build

Built from the uploaded key art (`1789079089105_image.png`). The mockup covered the homepage only, so About, Events, Travel, FAQ, Contact and the footer were designed and written from scratch, all as one page with anchored sections so every nav link works.

Artwork was cut directly from the mockup rather than substituted: the seal (masked to a circle, halo rebuilt in CSS), the two hero photographs, and the three card photos. The "Savannah Georgia" ticket was rebuilt in code — serrated edge and hand-drawn palm — so it stays sharp and satisfies the prompt's requirement that both words be clean and dominant. This is the one element where the site beats the mockup, whose stamp has scuffed lettering on mismatched baselines.

All images are compressed to WebP and embedded as base64. **There is no images folder** — the single file is the whole site.

Per your instruction, "McALPINE" is rendered as a solid fill rather than the mockup's half-painted treatment. For consistency, the matching distress texture on "REUNION 2027" was dropped too.

---

## Outstanding items

Content is real as of session 03. What's still open:

- **Preview video** — placeholder frame in the About section
- **Committee contact details** — none supplied; nothing invented
- **Payment link** — the Manus sandbox URL is temporary; needs a permanent one
- **AllEvents link** — needs the direct event URL, not the homepage
- **Three photographs** — Forsyth Fountain, the Georgia Queen, a Savannah rooftop bar (see Session 02, Blocked)
- **Transparent seal PNG** — would remove the last of the source compression artifacts

Dates verified: July 15–18, 2027 does fall Thursday through Sunday.

---

## Verified

Renders correctly at 1440px, 900px and 390px. Mobile menu, FAQ accordion, scroll-spy nav and the live countdown all tested. Keyboard focus outlines, skip link and image alt text in place. Honors reduce-motion. The only animation is the seal easing in once on load.

## Known constraints

1. **Fonts need internet.** Offline the page falls back to system fonts and still works, but headlines lose their condensed look and may wrap an extra line.
2. **Single page, not six.** Splitting into separate files would mean extracting the shared header, footer and CSS first — worth it only if the page grows.
3. **The stamp palm tree** is drawn in code and approximates the original.
4. **Not yet added:** past-reunion gallery, family tree page, online payment, a real RSVP form with a database.
5. **File size** ~700 KB because images live inside the file. Fine at this scale; if many photos get added they should move to a separate images folder.

## Making small edits

The file opens in any text editor. Content sits under marked comment headers (`<!-- ===== EVENTS ===== -->`). Every color is defined once in the `:root` block at the top — change a hex there and it updates sitewide.
