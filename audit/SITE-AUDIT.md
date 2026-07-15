# SupplyNow.io — Full-Site Messaging Audit

**Date:** July 4, 2026 · **Scope:** all 7 pages (`/`, `/restaurants`, `/suppliers`, `/network`, `/press`, `/contact`, `/privacy`) · **Method:** per-page deep audits + cross-page consistency/funnel/SEO analysis; every high-severity finding adversarially verified against the raw HTML (28 confirmed, 6 rejected).

> **Note:** this audit covers the *current* site (the "Every mile cold. Every mile paid." distributor/manufacturer positioning). The earlier `demo/index.html` in this repo was built against the previous version of the homepage and is now historical.

## Verdict

**C+ — Excellent copywriting instincts and genuinely differentiated positioning, undermined by a site that repeatedly contradicts its own numbers, routes every warm prospect back to the homepage to convert, and offers zero customer-sourced proof for its boldest claims.**

What this site does well is rare for a seed-stage logistics company: it argues with numbers instead of adjectives. "Every mile cold. Every mile paid." encodes both value props in eight words; the pages quantify everything (20–25% under in-house, $98 vs $126/hr, 12 months zero temperature incidents, a timed 5-step onboarding); the offer is properly de-risked ("one lane, then you decide"); and the whole site drives one conversion action with founder-direct fallbacks. The segment pages are written in disciplined buyer-POV language most competitors never achieve. The raw material here is B+ copy.

The single biggest theme holding it back is self-contradiction. The target reader is a skeptical ops buyer whose job is catching discrepancies — and the site hands them a dozen: the quote SLA is "one business hour" on the form and "24–48 hr" two inches away; "no contract, no fixed commitment" sits on the same pages as "on a retainer" service cards; "nine Midwest metros" includes Wilkes-Barre, Pennsylvania; the Q4 expansion is simultaneously live, launching this quarter, and launching in an undated Q4; the calculator server-renders "$0" of recoverable margin; and the footer disclaims every figure as "unaudited" on pages whose whole thesis is "the record wins the dispute." Each is cheap to fix individually, but collectively they teach exactly the reader you're courting to discount every number on the site. Related: the strongest asset — Restaurant Depot — is asserted via a self-authored fake blockquote with no permission signal, no numbers, no case study, while the only testimonial is an anonymous prospect on a first call. The claims outrun the proof.

The second theme is funnel architecture that leaks at the moment of highest intent. Fourteen primary CTAs across six pages route off-page to the homepage's /#quote anchor — a prospect just sold the manufacturer story gets dumped mid-scroll into a generic form. The two forms are inverted (the structured lane-quote form lives on the homepage; /contact, titled "Get a Cold-Chain Lane Quote," collects only name/email/message). Nav labels contradict their slugs ("For Distributors" → /restaurants), the restaurant/caterer segment has no path anywhere, no lead carries source attribution, and the footer promises "Results" that resolve to a three-stat band. Fix the contradictions first (hours of copyediting), then the funnel plumbing (days of component reuse), then invest in the one asset money can't shortcut: a permissioned customer proof point.

## Page scores

| Page | Score | One-line reason |
|---|---|---|
| `/home` (home) | 7/10 | The site's best page — sharp headline, quantified claims, strong objection handling — but the SLA contradiction at the conversion point, the $0 calculator, and investor-only proof cap it. |
| `/restaurants` | 5/10 | Strong buyer-POV distributor copy sabotaged by living on the wrong slug, a self-authored fake testimonial, a Midwest-vs-Atlanta geography contradiction inside its own Proof section, and CTAs that convert on a different page. |
| `/suppliers` | 6.5/10 | Best headline and risk-narrative on the site, undone by the retainer-vs-no-contract pricing contradiction, zero named proof, and all conversion routed to the homepage. |
| `/network` | 6/10 | Differentiated wedge story and clean structure, but its centerpiece pitches SupplyNow's own margin to the customer, and its flagship numbers (Wilkes-Barre as Midwest, km, undated Q4, six of nine metros named) don't survive a logistics-literate reader. |
| `/press` | 6/10 | Honest, click-verifiable third-party links, but 19-month-old newest item under a 'since day one' claim, scrambled ordering, duplicates/filler, and nothing for the journalists in its own title. |
| `/contact` | 6.5/10 | Great response-time promise and risk reversal, but the form doesn't collect the four inputs the H1 asks for, there's zero proof at the decision moment, and the nav routes converts away from the capture page. |
| `/privacy` | 3/10 | Four-years-stale generator boilerplate that legally covers only a mobile app, riddled with corrupted apostrophes, two conflicting company addresses, and an unclickable contact email — neglect on the one page whose only message is 'we are careful.' |

## Prioritized roadmap (impact-per-effort for a seed-stage team)

### 1. [S]

**Pages:** home, restaurants, suppliers, network, contact  
**Action:** One-truth contradiction sweep (a single copyediting session): pick one quote SLA and use the identical sentence everywhere — either change home's step-2 chip to '1 business hr' or the form/contact copy to 'within one business day'; reconcile retainer vs no-contract with 'Usage-based — per load and per mile, no contract to start. Recovery & Redelivery is the one exception: an optional standing retainer so a truck is already yours the day a load is refused.'; date the expansion as one sentence used verbatim ('Opening Q4 2026: Atlanta · Orlando · Miami · Dallas–Fort Worth'); delete home's 'lock your lane before the network fills' scarcity line and the 'Lock a lane' CTA; delete both 'never price before value' lines.  
**Why:** Highest impact-per-hour on the site: every contradiction is visible to the skeptical ops buyer in a single glance and each one discounts every other number. Source: confirmed cross:consistency SLA/retainer/expansion findings + page:home scarcity and CTA-label findings.

### 2. [S]

**Pages:** home, privacy  
**Action:** Fix the two literal breakages: server-render the empty-mile calculator defaults ($305,760 in #emYear, $25,480 in #emMonth) so the page never displays '$0' recoverable margin; add the missing href to the privacy page's contact email (mailto:aaron@supplynow.org — the page's only in-body action is currently unclickable).  
**Why:** The calculator saying '$0' directly under the backhaul-is-worth-money claim is the page arguing against itself; the dead privacy mailto is the one place on the site where a click does literally nothing. Source: confirmed page:home calculator and page:privacy dead-anchor findings.

### 3. [S]

**Pages:** network, home, restaurants, suppliers  
**Action:** Settle the footprint claim once: name all nine metros on /network (kill 'and more'), pick a regional label that survives Wilkes-Barre ('nine metros, Midwest to Mid-Atlantic' or drop Wilkes-Barre from Midwest framing), echo the named list on both segment pages under the stat bands with 'Not on the list? Ask — new metros open quarterly.', and convert 1,454 km to ~904 miles in both telemetry captions.  
**Why:** 'Do you cover my geography?' is the buyer's #1 qualifying question and is currently unanswerable — while the geography that IS stated contradicts itself. Logistics buyers know where Wilkes-Barre is and think in miles. Source: confirmed cross:consistency footprint finding + funnel coverage-gap and units findings.

### 4. [S]

**Pages:** all 7  
**Action:** Replace the blanket 'Figures shown are unaudited' footer disclaimer with a methodology line that adds credibility: 'Performance figures reflect internal network tracking, July 2025–June 2026. Ask us for the raw per-load temperature logs.' Suppress the line entirely on pages with no figures (contact, press, privacy).  
**Why:** One shared-footer edit stops the site from legally disclaiming its own strongest proof (zero incidents, 20–25%, $98 vs $126) at the last moment before a decision. Source: confirmed page:suppliers and page:network disclaimer findings.

### 5. [M]

**Pages:** home, restaurants  
**Action:** Repair the Restaurant Depot proof: replace the self-authored blockquote on /restaurants with a plain, permissioned results claim outside quote markup ('Daily last-mile for Restaurant Depot across nine metros. Zero temperature incidents in 12 months.'), replace the homepage's anonymous prospect quote ('— a national distributor's VP, first call') with a named customer quote plus a result — or cut it and add one substantiated Restaurant Depot line to the proof band. Get written permission for the name in the same effort.  
**Why:** The site's single strongest asset currently rests on one unsupported clause and a fake testimonial format savvy buyers recognize instantly — and the name-drop is legally risky if unapproved. Source: confirmed page:home proof-gap and page:restaurants self-quote findings.

### 6. [M]

**Pages:** restaurants, suppliers, network, contact  
**Action:** Embed the existing homepage quote-form component at the bottom of /restaurants, /suppliers, and /network with a local id='quote'; change all their CTA hrefs from '/#quote' to '#quote'; add hidden segment (distributor/manufacturer/network) and source_page fields. Same session: put the structured lane fields (origin, stops, temperature select, cadence select) on /contact with button 'Get my lane quote', and repoint contact's own nav CTA to the on-page form.  
**Why:** Fourteen primary CTA clicks currently ship the warmest prospects off-page into a generic form with zero attribution; this converts them where they were sold and pre-qualifies every lead, protecting the one-hour follow-up promise. Source: confirmed cross:funnel off-page-CTA and inverted-forms findings + page:contact promise/mechanism mismatch.

### 7. [M]

**Pages:** all 7 (nav) + new redirects  
**Action:** Re-slug /restaurants → /distributors and /suppliers → /manufacturers with 301s; update the shared nav, homepage segment cards, footers, canonicals, and og:url in one deploy. Then decide the restaurant question explicitly: if restaurants/caterers are still served, add one recovery line sitewide ('Restaurant or caterer? Text us your order list — same-day wholesale sourcing and delivery') and a real page; if not, put a short explainer at the 301 target so legacy traffic isn't silently bounced.  
**Why:** Fixes the label/URL mismatch that reads as a broken site on every page, stops distributor content ranking on a restaurant slug, and resolves the orphaned core segment. Source: confirmed page:restaurants slug/audience and cross:funnel segment-selection findings.

### 8. [M]

**Pages:** all 7  
**Action:** Ship the SEO baseline: rewrite all 7 title tags keyword-first with geo modifiers (home: 'Refrigerated Last-Mile Delivery Network — Cleveland & the Midwest | SupplyNow'; keep taglines in og:title), trim the four over-length meta descriptions to ≤155 chars with proof up front, add sitewide JSON-LD Organization/LocalBusiness (name, Cleveland address, phone, LinkedIn, areaServed = the nine metros), and add @astrojs/sitemap + robots.txt.  
**Why:** The site is currently invisible for every non-brand query a Cleveland cold-chain buyer would type — no geo or category keyword exists in any indexable metadata, and there is no entity for Google to attach the business to. Source: confirmed cross:seo keyword and structured-data findings.

### 9. [S]

**Pages:** network  
**Action:** Flip /network's economics section to customer POV: retitle 'Margin as a science' → eyebrow 'Your delivered cost', H2 'Dense routes cost less to run. You keep the difference.'; rewrite the ≈18-hours card ('so your rate isn't paying for idle iron') and the video caption ('Density is why it costs less. Every metro feeds the next.'); fix the meta description's 'margin engineered as a science'.  
**Why:** The middle of the coverage page currently pitches SupplyNow's P&L to the person paying it — investor-deck framing at the proof-of-capability step. Source: confirmed page:network margin-framing finding.

### 10. [S]

**Pages:** home, network, restaurants, suppliers  
**Action:** Substantiate the zero-incident claim with mechanism, using one sentence sitewide: 'Sensor-logged temperature on every leg — timestamped, exportable, shared on request. Twelve months, zero temperature incidents.' Standardize on 'temperature incidents' (drop 'excursions') everywhere, and add one operator-vetting sentence to /network: insurance floor, cold-chain inspection, sensor kit on every load.  
**Why:** A food-safety-grade claim with no stated method is exactly what a manufacturer's QA lead will probe; the mechanism sentence plus a defined 'vetted' turns the boldest claim from assertion into evidence. Source: confirmed page:network zero-excursions finding + funnel vetting-content gap.

### 11. [M]

**Pages:** all 7 (footer) + home or new /results  
**Action:** Create one customer-proof asset and honor the 'Results' promise: a short case block (even anonymized with three concrete details — product category, dollars at risk, hours to recovery) or a /results page with one permissioned quote; point the footer 'Results' link at it. Until it exists, relabel the footer link 'Track record'.  
**Why:** The IA promises results, delivers a stat band, and has zero customer-sourced evidence anywhere — the single content gap that gates conversion for diligence-driven cold-chain buyers. Source: confirmed cross:funnel missing-customer-proof and page:suppliers no-third-party-proof findings.

### 12. [M]

**Pages:** privacy  
**Action:** Rewrite the privacy policy against current operations: define the Service as the website + text/WhatsApp ordering (not just a downloadable app), describe data actually collected (order lists, delivery addresses, order history), add Cookies and Your Privacy Rights sections, fix all 8+ corrupted apostrophes ('Children"s' → 'Children's'), reconcile the 4614 Prospect Ave vs 2800 Euclid Ave address, demote the six extra H1s to H2s, and update 'Last updated' to July 2026 only after the content is true.  
**Why:** A 2022 app-only policy full of broken characters is a guaranteed vendor-security-questionnaire flag from exactly the legal/ops reviewers this page exists to satisfy. Source: confirmed page:privacy staleness, scope, and corruption findings.

### 13. [S]

**Pages:** all 7 (email), contact  
**Action:** Unify the contact identity: display aaron@supplynow.io everywhere (alias to the .org inbox), add an SMS link 'Text us: (216) 548-7070' ahead of WhatsApp on /contact, and add a two-line founder intro on /contact ('Aaron, founder — Techstars '24, Forbes 30 Under 30 (Cleveland). He quotes every lane himself.') so all six 'Talk to Aaron' CTAs inherit meaning.  
**Why:** The .io/.org mismatch pattern-matches to phishing at the exact touchpoints asking strangers for their work email; the founder intro converts an oddly familiar CTA into a credibility asset already sitting unused on /press. Source: confirmed cross:consistency email-domain finding + contact/funnel Talk-to-Aaron findings.

### 14. [S]

**Pages:** press  
**Action:** Refresh /press in one pass: sort all three lists newest-first with 'Mon YYYY' dates, cut the PR Newswire duplicate, move the two visa stories to a founder sub-list, change the CTA labels to match the sitewide standard, replace '← Back to home' with 'Talk to Aaron →', and if no 2025–26 coverage exists, rewrite the subhead so it stops promising recency ('Forbes 30 Under 30 (Cleveland). Techstars '24. The public record behind the network we run today.'). Add a small media block: contact email, one-paragraph boilerplate, logo download.  
**Why:** A trust page whose newest item is 19 months old under a 'since day one' claim reads as a company the press stopped following — the opposite of its job — and it currently serves journalists nothing. Source: confirmed page:press staleness finding + medium curation/media-kit findings.

### 15. [S]

**Pages:** thanks, home, contact (form config)  
**Action:** Verify and upgrade the post-submit path: confirm /thanks restates the promise ('Got it — Aaron replies within one business hour, Mon–Sat 7am–6pm ET'), offers one bridge action (WhatsApp or 'see the network →'), and enable the form endpoint's captcha (or move to a first-party /api/contact) so spam doesn't erode the reply-time promise.  
**Why:** The moment after conversion is where the SLA promise is either cemented or broken, and captcha-disabled free-tier form plumbing invites junk into the founder inbox that competes with real one-hour replies. Source: page:home form-plumbing finding + cross:funnel /thanks finding.

## Quick wins (under an hour, total)

- [ ] Pick one quote SLA and make the home form and step-2 chip agree (one-line edit in two places)
- [ ] Add the missing mailto: href to the privacy page's contact email
- [ ] Delete the 'Lock a lane' CTA and the 'lock your lane before the network fills' scarcity line on home
- [ ] Convert '1,454 km' to '~904 miles' in both telemetry captions (home, network)
- [ ] Change 'Atlanta · Orlando · Miami · Texas' to '...Dallas–Fort Worth' and date every 'Q4' as 'Q4 2026' (home, restaurants, suppliers, network)
- [ ] Delete both 'never price before value' / 'price never leads' lines (restaurants, suppliers)
- [ ] Global find-and-replace the corrupted apostrophes in privacy.html ("s → 's, incl. 'Children"s Privacy')
- [ ] Rename the hero toggle button 'Default' to 'Overview' on home
- [ ] Replace the footer 'unaudited figures' disclaimer with the dated methodology line (one shared-footer edit)
- [ ] Change the two '← Back to home' hero CTAs on /network and /press to 'Talk to Aaron →'
- [ ] Delete '· GFS Food Foundry' from the home Recognized-by line (logo already carries it)

## Confirmed high-severity findings (survived adversarial verification)

<details><summary><b>[page:home]</b> Direct numeric contradiction at the conversion point: the form promises a quote in one business hour while step 2 of the adjacent rail promises 24–48 …</summary>

**Issue:** Direct numeric contradiction at the conversion point: the form promises a quote in one business hour while step 2 of the adjacent rail promises 24–48 hours — a skeptical ops buyer sees the conflict in a single glance and discounts every other number on the page.

**Evidence (verbatim):** `Tell us the lane. We come back with capacity and a number within one business hour.`

**Fix:** Pick one truth and use it in both places. If the hour is real, change step 2's time chip from "24–48 hr" to "1 business hr". If not, change the form sub-copy to: "Tell us the lane. We come back with capacity and a number within one business day."

</details>

<details><summary><b>[page:home]</b> The calculator's result panel is server-rendered as $0/year and $0/month — before hydration, with JS blocked, or on any script failure, the page liter…</summary>

**Issue:** The calculator's result panel is server-rendered as $0/year and $0/month — before hydration, with JS blocked, or on any script failure, the page literally says the recoverable margin is zero, directly under the claim that the backhaul is worth money. It also contradicts its own footer, which already shows computed miles (4,200).

**Evidence (verbatim):** `&lt;p class="em-figure tnum" id="emYear" data-astro-cid-j7pv25f6&gt;$0&lt;/p&gt;`

**Fix:** Server-render the outputs for the default inputs (12 trucks × 350 mi × $1.40 × 52): render "$305,760" in #emYear and "$25,480" in #emMonth so the static HTML is always correct, then let JS update from there.

</details>

<details><summary><b>[page:home]</b> Proof/credibility gap: the only logo strip is investors and accelerators ("Backed by"), and the sole testimonial is an anonymous quote from a prospect…</summary>

**Issue:** Proof/credibility gap: the only logo strip is investors and accelerators ("Backed by"), and the sole testimonial is an anonymous quote from a prospect on a first sales call — not a customer with results. For a page claiming Restaurant Depot runs it daily, there is zero customer-sourced evidence.

**Evidence (verbatim):** `— a national distributor's VP, first call`

**Fix:** Replace the prospect quote with a named, permissioned customer quote plus a result (e.g., "— Ops Director, [Customer], 14 lanes/week on the network"). If none is available yet, cut the figure block entirely and instead add one substantiated Restaurant Depot line to the proof band: "Daily lanes for Restaurant Depot across 9 metros — 12 months, zero temperature incidents."

</details>

<details><summary><b>[page:restaurants]</b> Slug/audience mismatch: the page lives at /restaurants but every word targets distributors, and the site nav labels this URL "For Distributors". Resta…</summary>

**Issue:** Slug/audience mismatch: the page lives at /restaurants but every word targets distributors, and the site nav labels this URL "For Distributors". Restaurant-intent visitors (a core SupplyNow segment) land on freight-network copy with zero relevance; distributor prospects get a URL that contradicts what they're reading. There is no restaurant page anywhere in the nav.

**Evidence (verbatim):** `&lt;link rel="canonical" href="https://www.supplynow.io/restaurants/"&gt; … &lt;p class="eyebrow" data-astro-cid-ah56de4j&gt;For distributors&lt;/p&gt; … &lt;a href="/restaurants" class="nav-link text-[0.92rem] text-ink/80 transition-colors hover:text-ink"&gt;For Distributors&lt;/a&gt;`

**Fix:** Move this page to /distributors and 301 /restaurants → /distributors. Then build a real restaurant page at /restaurants with restaurant-POV messaging, e.g. H1: "Text us your order list. We shop 30+ wholesalers and deliver same-day, refrigerated." Also rename og-distributors.jpg references and fix the sibling mismatch ("For Manufacturers" → /suppliers) at the same time.

</details>

<details><summary><b>[page:restaurants]</b> The "Proof" blockquote is not a testimonial — it is SupplyNow's own marketing sentence dressed in quote formatting, attributed to no one, while name-d…</summary>

**Issue:** The "Proof" blockquote is not a testimonial — it is SupplyNow's own marketing sentence dressed in quote formatting, attributed to no one, while name-dropping a major brand ("Restaurant Depot trusts us") with no visible authorization, logo, or spokesperson. Savvy B2B buyers recognize self-quotes and discount the whole proof section; the brand claim is also legally risky if unapproved.

**Evidence (verbatim):** `&lt;p class="eyebrow" data-astro-cid-ah56de4j&gt;Proof&lt;/p&gt; &lt;blockquote class="mt-6 font-serif text-[clamp(1.5rem,3vw,2.1rem)] leading-snug tracking-[-0.012em] text-ink" data-astro-cid-ah56de4j&gt;
Restaurant Depot trusts us with daily last-mile across nine Midwest metros — zero
          temperature incidents over twelve months.
&lt;/blockquote&gt;`

**Fix:** Either get a real attributed quote ("'They run our daily last-mile across nine metros and we haven't had a single temp incident.' — [Name], Regional Ops Manager, Restaurant Depot") or reformat as a plain results claim outside blockquote markup: "Daily last-mile for Restaurant Depot across nine metros. Zero temperature incidents in 12 months." — with their written permission for the name.

</details>

<details><summary><b>[page:suppliers]</b> Direct pricing-model contradiction: two of the three services are sold 'on a retainer' with a 'Retainer coverage' chip, while the closing offer promis…</summary>

**Issue:** Direct pricing-model contradiction: two of the three services are sold 'on a retainer' with a 'Retainer coverage' chip, while the closing offer promises no fixed commitment and no contract — a diligence-minded ops buyer will catch this and distrust the rest of the page.

**Evidence (verbatim):** `How you pay: usage-based — you pay for the loads and miles you actually use. No fleet to carry, no fixed commitment.`

**Fix:** Reconcile the two models explicitly in the 'How you pay' block: 'How you pay: usage-based — per load and per mile on scheduled lanes, no fixed commitment, no contract to start. Recovery & Redelivery is the one exception: an optional standing retainer so a truck is already yours the day a load gets refused.'

</details>

<details><summary><b>[page:suppliers]</b> The footer legally disclaims the exact proof the entire page is built on. The core argument is 'the record is what wins the dispute,' then the site's …</summary>

**Issue:** The footer legally disclaims the exact proof the entire page is built on. The core argument is 'the record is what wins the dispute,' then the site's own fine print says its figures are unaudited — undercutting the zero-incident record, the 9-metro claim, and the case study in one line.

**Evidence (verbatim):** `Figures shown are unaudited and provided for informational purposes.`

**Fix:** Replace the blanket disclaimer with a methodology line that adds credibility instead of subtracting it: 'Temperature record: continuous sensor logs on every load; an incident is any reading outside the contracted band. Ask us for the raw per-load logs.' If legal insists on a disclaimer, scope it ('Metro counts approximate') rather than disclaiming all figures.

</details>

<details><summary><b>[page:suppliers]</b> Zero named or third-party proof on the page: no customer names or logos, no customer count, and none of the company's real credibility assets (Techsta…</summary>

**Issue:** Zero named or third-party proof on the page: no customer names or logos, no customer count, and none of the company's real credibility assets (Techstars, Forbes 30 Under 30 founder, ~200 customers) appear anywhere. For a claim this bold ('zero incidents'), the page asks to be taken entirely on its own word.

**Evidence (verbatim):** `9 Midwest metros · live temp & route monitoring · clean per-load records · operating since 2023.`

**Fix:** Add a credibility strip under the proof tiles: '200+ food businesses move product on the SupplyNow network · Techstars-backed · Founder named to Forbes 30 Under 30 · As seen in [press outlet]' — and link 'Press' from the body, not just the footer.

</details>

<details><summary><b>[page:suppliers]</b> All three primary 'Quote a lane' CTAs route off this segment page to a homepage anchor (/#quote), dumping a manufacturer prospect into a generic form …</summary>

**Issue:** All three primary 'Quote a lane' CTAs route off this segment page to a homepage anchor (/#quote), dumping a manufacturer prospect into a generic form and losing the page's manufacturer-specific framing mid-conversion.

**Evidence (verbatim):** `Quote a lane`

**Fix:** Embed the quote form on /suppliers itself (make the CTA href '#quote' local) with manufacturer-specific fields — origin dock, temp band (frozen/refrigerated), stops per week, metros — and pre-fill segment='manufacturer' so Aaron's follow-up is contextual.

</details>

<details><summary><b>[page:network]</b> The page's centerpiece section is framed around SupplyNow's own profitability, not the customer's outcome. 'Margin as a science' as a section header o…</summary>

**Issue:** The page's centerpiece section is framed around SupplyNow's own profitability, not the customer's outcome. 'Margin as a science' as a section header on a customer-facing page reads as 'we've engineered how much we make off you' — pitch-deck framing pointed at the wrong audience.

**Evidence (verbatim):** `Margin as a science`

**Fix:** Reframe the section from company economics to customer delivered cost. Eyebrow: 'Your delivered cost'. H2: 'Dense routes cost less to run. You keep the difference.' Keep the lever cards but flip each payoff line to the reader (the lead paragraph's 'that saving is shared, not kept' already shows the right move — make it the section's headline idea, not a footnote).

</details>

<details><summary><b>[page:network]</b> A food-safety-grade claim ('zero excursions' over twelve months) is asserted with no substantiation — no monitoring method, no logger vendor, no audit…</summary>

**Issue:** A food-safety-grade claim ('zero excursions' over twelve months) is asserted with no substantiation — no monitoring method, no logger vendor, no audit trail — and is then directly undercut by the footer's own disclaimer that figures are unaudited. A QA manager at a manufacturer will probe exactly this claim.

**Evidence (verbatim):** `Live temperature on every leg.Twelve months, zero excursions.`

**Fix:** Back the claim with its mechanism: 'Sensor-logged temperature on every leg — timestamped, exportable, shared on request. Twelve months without a single out-of-temp delivery.' Then remove or narrow the footer disclaimer so it doesn't contradict the page's strongest trust claim.

</details>

<details><summary><b>[page:network]</b> Every primary CTA ('Quote a lane') navigates away from this page to a homepage anchor. The conversion action requires a full page change back to '/', …</summary>

**Issue:** Every primary CTA ('Quote a lane') navigates away from this page to a homepage anchor. The conversion action requires a full page change back to '/', losing the network-page context, adding load time, and creating back-button confusion — a classic leak on the page's only conversion path.

**Evidence (verbatim):** `&lt;a href="/#quote" class="cta-primary" data-astro-cid-ef4fiqgb&gt;Quote a lane&lt;/a&gt;`

**Fix:** Embed the quote form at the bottom of /network (give this page its own #quote section) or route to a dedicated /quote page. At minimum, pass context so the form knows the visitor came from the network page (e.g. /#quote?src=network) and pre-select 'lane quote'.

</details>

<details><summary><b>[page:press]</b> Staleness undercuts the page's central claim. Today is July 2026; the newest item anywhere on the page is the Techstars Fall 2024 cohort (~19 months o…</summary>

**Issue:** Staleness undercuts the page's central claim. Today is July 2026; the newest item anywhere on the page is the Techstars Fall 2024 cohort (~19 months old) and 11 of 13 items are from 2022–2023 — yet the hero claims continuous coverage 'since day one.' To a diligencing buyer or journalist this reads as a company the press stopped following, the opposite of the intended message.

**Evidence (verbatim):** `A founder and a company the press has followed since day one.`

**Fix:** Add any 2025–2026 coverage, award, or talk (even a podcast) to the top of each list. If none exists, rewrite the subhead so it doesn't promise recency: 'Forbes 30 Under 30. Techstars ’24. The public record behind the 200+ kitchens we supply today.' — anchoring credibility to current operations instead of a dated press trail.

</details>

<details><summary><b>[page:contact]</b> Promise/mechanism mismatch: the H1, meta, and hero all promise a lane quote from four specific inputs (origin, stops, temperature, cadence), but the f…</summary>

**Issue:** Promise/mechanism mismatch: the H1, meta, and hero all promise a lane quote from four specific inputs (origin, stops, temperature, cadence), but the form is a generic name/email/message form — the visitor must compose all four data points as freeform prose in one textarea. This adds cognitive friction at the exact conversion moment, produces incomplete submissions that force a follow-up email before a quote can be given, and quietly breaks the one-business-hour promise.

**Evidence (verbatim):** `Tell us the lane — origin, stops, temperature, cadence — or whatever's on your mind.`

**Fix:** Replace the generic form with structured quote fields matching the promise: Origin (city or ZIP), Stops per run (number), Temperature (select: Frozen −10°F / Refrigerated 34–40°F / Ambient), Cadence (select: Daily / 3–5x per week / Weekly / One-time), plus an optional notes field. Change the button to "Get my lane quote" and keep a small "Just have a question? Email aaron@supplynow.org" escape hatch below.

</details>

<details><summary><b>[page:privacy]</b> The page's only in-body action — the privacy contact email — is a dead anchor with no href. A reader who wants to exercise privacy rights or ask a dil…</summary>

**Issue:** The page's only in-body action — the privacy contact email — is a dead anchor with no href. A reader who wants to exercise privacy rights or ask a diligence question cannot click it; on some renderers it doesn't even look like a link.

**Evidence (verbatim):** `By email: &lt;a&gt;aaron@supplynow.org&lt;/a&gt;`

**Fix:** Add the href: By email: <a href="mailto:aaron@supplynow.org">aaron@supplynow.org</a>. Better: create a role address on the site's own domain and use it here and in the footer — 'By email: privacy@supplynow.io'.

</details>

<details><summary><b>[page:privacy]</b> Pervasive character corruption: every possessive apostrophe renders as a stray double-quote (8+ instances, including a section heading 'Children"s Pri…</summary>

**Issue:** Pervasive character corruption: every possessive apostrophe renders as a stray double-quote (8+ instances, including a section heading 'Children"s Privacy'). A legal document full of broken characters reads as neglect to exactly the diligence-minded reader this page serves.

**Evidence (verbatim):** `Usage Data may include information such as Your Device"s Internet Protocol address (e.g. IP address)`

**Fix:** Global find-and-replace "s → 's across the document (Device's, Company's, Children's Privacy, parent's, third party's, application's, Service Provider's), then proofread the full text once.

</details>

<details><summary><b>[page:privacy]</b> The policy is nearly four years stale — 'August 06, 2022' — while the site footer says © 2026. It predates the current business (distributor network, …</summary>

**Issue:** The policy is nearly four years stale — 'August 06, 2022' — while the site footer says © 2026. It predates the current business (distributor network, WhatsApp ordering, ~200 customers), and any vendor-security questionnaire will flag a policy untouched since 2022.

**Evidence (verbatim):** `Last updated: August 06, 2022`

**Fix:** Actually review the policy against current data practices, then update the line to 'Last updated: July 2026'. Do not just bump the date — the content must match today's operations or the mismatch becomes a legal problem instead of a cosmetic one.

</details>

<details><summary><b>[cross:consistency]</b> The quote-turnaround SLA changes by a factor of up to 48x depending on which page you read: the home form and restaurants closing promise a number wit…</summary>

**Issue:** The quote-turnaround SLA changes by a factor of up to 48x depending on which page you read: the home form and restaurants closing promise a number within one business hour, the home onboarding rail says 24–48 hours for the exact same step, and the contact page states the promise twice with different strength (hedged in the hero, absolute at the form).

**Evidence (verbatim):** `home (#quote form sub-copy): "Tell us the lane. We come back with capacity and a number within one business hour." vs home (steps rail, step 2 'Confirm'): "We come back with capacity and a number." with time chip "24–48 hr". restaurants (closing): "…one business hour. We talk service and value first; price never leads." contact (hero): "give us the route and we come back with capacity and a number`

**Fix:** Pick one SLA and one phrasing — e.g. "We come back with capacity and a number within one business day" (or, if the hour is real, change the home rail chip to "1 business hr") — and reuse the identical sentence on home, restaurants, and contact, including matching the hedge level (either 'usually' everywhere or nowhere).

</details>

<details><summary><b>[cross:consistency]</b> The flagship footprint claim contradicts itself across four pages: restaurants, suppliers, and network all say "nine Midwest metros," but the network …</summary>

**Issue:** The flagship footprint claim contradicts itself across four pages: restaurants, suppliers, and network all say "nine Midwest metros," but the network page's own metro list includes Wilkes-Barre (northeastern Pennsylvania — Mid-Atlantic, not Midwest), while the home page quietly hedges to "Ohio and neighboring states" even though its stat band still says "Midwest metros." No page ever names all nine.

**Evidence (verbatim):** `restaurants: "Restaurant Depot trusts us with daily last-mile across nine Midwest metros — zero temperature incidents…"; suppliers (hero microcopy): "9 Midwest metros · live temp & route monitoring · clean per-load records · operating since 2023."; network (Today card H3 "Nine Midwest metros" with body): "Cleveland, Detroit, Akron, Columbus, Indianapolis, Wilkes-Barre and more — anchored by Restau`

**Fix:** Name all nine metros once on /network, choose one regional label that fits the actual list (e.g. "nine metros, Midwest to Mid-Atlantic" or drop Wilkes-Barre from the Midwest framing), and propagate that exact label to home, restaurants, and suppliers.

</details>

<details><summary><b>[cross:consistency]</b> The four expansion markets are simultaneously live, launching this quarter (Q3), and launching in Q4, depending on the page: the restaurants figcaptio…</summary>

**Issue:** The four expansion markets are simultaneously live, launching this quarter (Q3), and launching in Q4, depending on the page: the restaurants figcaption reads as if Atlanta, Orlando, and Miami are already operating with only Texas pending, while home, suppliers, and network all present all four as a future Q4 expansion — and home separately says the metros are being added "this quarter" on a site viewed in July (Q3). No mention carries a year.

**Evidence (verbatim):** `restaurants (Proof figcaption): "Operating since 2023 · Atlanta · Orlando · Miami · Texas next in Q4" (reads as A/O/M live now). home: "Next: Atlanta · Orlando · Miami · Texas in Q4." and "adding four metros this quarter — lock your lane before the network fills." suppliers (How it works step 3): "including Q4 expansion into Atlanta, Orlando, Miami, and Texas". network: chip "+4 Q4 expansion" and `

**Fix:** Write one dated roadmap sentence — "Opening Q4 2026: Atlanta · Orlando · Miami · Dallas–Fort Worth" — and use it verbatim on all four pages; delete home's "this quarter" scarcity line and restructure the restaurants figcaption so expansion markets can't be read as current operations.

</details>

<details><summary><b>[cross:consistency]</b> The commercial model contradicts itself across pages: contact, home, and the suppliers closing card promise no contract and no fixed commitment (suppl…</summary>

**Issue:** The commercial model contradicts itself across pages: contact, home, and the suppliers closing card promise no contract and no fixed commitment (suppliers explicitly says pricing is purely usage-based), while the service cards on both restaurants and suppliers sell recovery service "on a retainer" — a standing fixed commitment — with suppliers even displaying a "Retainer coverage" chip.

**Evidence (verbatim):** `contact (hero): "No contract to start — one lane, then you decide."; suppliers (Get started card): "usage-based — you pay for the loads and miles you actually use. No fleet to carry, no fixed commitment." and "One real load, tracked and documented, then you decide. No contract to start." vs suppliers (service card): "Same-day recovery for refused, missed, or rush loads — in-temp, on a retainer" pl`

**Fix:** Reconcile in the How-you-pay copy on both segment pages: "Usage-based — per load and per mile, no contract to start. Recovery & Redelivery is the one exception: an optional standing retainer so a truck is already yours the day a load is refused." Use the same wording on restaurants and suppliers.

</details>

<details><summary><b>[cross:consistency]</b> The site describes three different companies depending on the page: the marketing pages sell a B2B refrigerated freight network ("Asset-light cold-cha…</summary>

**Issue:** The site describes three different companies depending on the page: the marketing pages sell a B2B refrigerated freight network ("Asset-light cold-chain logistics" in every footer), the press page's coverage brands SupplyNow as a procurement fixer, and the privacy policy legally defines the entire Service as a downloadable mobile app — while the nav on all 7 pages labels segment links with audiences ("For Distributors", "For Manufacturers") that contradict their legacy slugs (/restaurants, /suppliers) from the earlier procurement era.

**Evidence (verbatim):** `All 7 footers: "Asset-light cold-chain logistics." press (In the press, row 1): "Crain's Cleveland — SupplyNow aims to fix procurement challenges — Nov 2022". privacy (Definitions): "Service refers to the Application." where Application "means the software program provided by [the Company]… downloaded by You on any electronic" device. All 7 pages' nav: &lt;a href="/restaurants"&gt;For Distributors`

**Fix:** Commit to the current positioning in one sentence, re-slug /restaurants→/distributors and /suppliers→/manufacturers with 301s, rewrite the privacy Service definition to cover the website and current freight/ordering operations, and add a one-line note on the press page framing the 2022 procurement coverage as the company's origin story.

</details>

<details><summary><b>[cross:funnel]</b> Every mid-funnel page routes its primary conversion CTA off-page to a homepage anchor. Fourteen primary 'Quote a lane' clicks across six pages (/resta…</summary>

**Issue:** Every mid-funnel page routes its primary conversion CTA off-page to a homepage anchor. Fourteen primary 'Quote a lane' clicks across six pages (/restaurants x3, /suppliers x3, /network x3, /press x3, /contact nav x1, /privacy nav x1) all resolve to /#quote — no page except the homepage has a quote form or a local #quote target. The anchors themselves are NOT dead (verified: id="quote", id="proof", id="how" all exist in home.html), but a prospect who has just been sold the distributor, manufacturer, or network story is dumped mid-scroll into the generic homepage form, losing all segment context and adding a full page load at the moment of highest intent.

**Evidence (verbatim):** `Grep of all 7 HTML files: only home.html contains id="quote". restaurants.html, suppliers.html, network.html each contain 3x &lt;a href="/#quote" class="cta-primary"&gt;Quote a lane&lt;/a&gt; (hero, nav, closing); press.html has &lt;a href="/#quote" class="cta-primary"&gt;Get a lane quote&lt;/a&gt; twice plus the nav CTA. None carries a query param or fragment beyond the bare "/#quote".`

**Fix:** The structured quote form already exists as a component on the homepage — embed it at the bottom of /restaurants, /suppliers, and /network with a local id="quote", change those pages' CTA hrefs from "/#quote" to "#quote", and add a hidden input (segment=distributor|manufacturer|network) so submissions arrive pre-qualified. If embedding is deferred, at minimum append ?src=<page> to every /#quote href and read it into a hidden form field.

</details>

<details><summary><b>[cross:funnel]</b> The funnel's two forms are inverted: the homepage #quote form is the structured lane-quote form (lane, temperature class, cadence, timing), while /con…</summary>

**Issue:** The funnel's two forms are inverted: the homepage #quote form is the structured lane-quote form (lane, temperature class, cadence, timing), while /contact — the page whose title tag is literally 'Get a Cold-Chain Lane Quote' and whose H1 is 'Tell us the lane.' — has only a generic name/email/company/phone/message form. Every sitewide secondary CTA ('Talk to Aaron →' on restaurants x2, suppliers x2, network, press) drains into this weaker form, so warm leads who chose the personal route submit LESS quotable data than cold homepage visitors. Worse, /contact's own nav shows a primary 'Quote a lane' button that navigates AWAY from the contact page back to /#quote, splitting conversions on the one page whose only job is capture.

**Evidence (verbatim):** `home.html form fields: &lt;input type="text" name="lane" required placeholder="e.g. Cleveland → Columbus, ~12 stops"&gt;, &lt;select name="temperature_class" required&gt;, name="volume_cadence", name="timing". contact.html form fields: only name/email/company/phone/message, hidden _subject="New message — supplynow.io/contact". contact.html nav: &lt;a href="/#quote" class="cta-primary !px-5 !py-2.5`

**Fix:** Reuse the homepage form component on /contact (same lane/temperature/cadence fields, same _subject="New lane quote"), keep a small free-text notes field for non-quote messages, and on /contact only repoint the nav CTA to the on-page form (href="#message" or an id on the quote-card) so no visitor is ever routed off the capture page.

</details>

<details><summary><b>[cross:funnel]</b> Segment self-selection — the nav's core IA job — is broken in both directions: labels contradict slugs on all 7 pages ('For Distributors' → /restauran…</summary>

**Issue:** Segment self-selection — the nav's core IA job — is broken in both directions: labels contradict slugs on all 7 pages ('For Distributors' → /restaurants, 'For Manufacturers' → /suppliers), and the restaurant/caterer segment has no path anywhere in the architecture — no nav item, no page, no footer link, no recovery line. Legacy restaurant-intent traffic (old links, bookmarks, SEO for the /restaurants slug) lands on distributor freight copy with nothing for them; distributor prospects see a URL that says 'restaurants' and read it as a mis-link. The segment split happens at the right moment (top nav + homepage hero cards) but sends both audiences through mislabeled doors.

**Evidence (verbatim):** `Identical nav block in all 7 files: &lt;a href="/restaurants" class="nav-link ..."&gt;For Distributors&lt;/a&gt; &lt;a href="/suppliers" class="nav-link ..."&gt;For Manufacturers&lt;/a&gt;. restaurants.html canonical: https://www.supplynow.io/restaurants/ with eyebrow 'For distributors'. No file contains any link labeled for restaurants or caterers.`

**Fix:** Re-slug to /distributors and /manufacturers with 301s from /restaurants and /suppliers; update the shared nav component and the homepage segment cards. Then decide the restaurant question explicitly: if restaurants/caterers are still served, add one nav or footer entry pointing to a real restaurant page; if not, put a one-paragraph explainer + contact route at the 301 target so legacy traffic isn't silently converted into distributor bounce.

</details>

<details><summary><b>[cross:funnel]</b> The site's costliest MISSING content is customer proof, and the IA actively promises it then fails to deliver: every page's footer links 'Results' to …</summary>

**Issue:** The site's costliest MISSING content is customer proof, and the IA actively promises it then fails to deliver: every page's footer links 'Results' to /#proof, which is a three-stat band on the homepage (20-25%, 9 metros, 0 incidents) — not results. Across all seven pages there is no case study, no named customer quote, and no customer-outcome page; /press carries only company awards. For a diligence-driven cold-chain buyer, this absence gates conversion in a way the other classic missing pages do not: a pricing page is fine to skip (the model is quote-driven and $98/hr + 20-25% anchors are already published), and a dedicated FAQ page is fine to skip (two FAQs exist on home) — but 'Results' pointing at a stat band is a promise the funnel breaks.

**Evidence (verbatim):** `Footer on all 7 pages: &lt;a href="/#proof"&gt;Results&lt;/a&gt; (verified id="proof" exists only on home.html as the stat band). Home audit confirms the only quote on the site is '— a national distributor's VP, first call' (a prospect, not a customer). press.html contains 13 outbound award/press links and zero customer references.`

**Fix:** Create one customer-proof asset — a short Restaurant Depot case block or a /results page with one permissioned quote plus lane-level numbers — and point the footer 'Results' link at it. Until it exists, relabel the footer link 'Track record' so the IA stops promising content the site doesn't have.

</details>

<details><summary><b>[cross:seo]</b> Zero local or category keyword targeting anywhere in the indexable metadata. No title tag, meta description, or H1 on any of the 7 pages contains 'Cle…</summary>

**Issue:** Zero local or category keyword targeting anywhere in the indexable metadata. No title tag, meta description, or H1 on any of the 7 pages contains 'Cleveland', 'Ohio', 'Columbus', 'Cincinnati', or a searchable category phrase ('refrigerated delivery', 'wholesale food delivery', 'cold chain courier'). The homepage title and H1 are both pure brand taglines. For a Cleveland-based service business trying to be found for queries like 'wholesale food delivery Cleveland' or 'refrigerated last mile Ohio', the site is invisible — the only geo signals are a footer address and a form placeholder, neither of which carries ranking weight.

**Evidence (verbatim):** `home.html: &lt;title&gt;SupplyNow — Every Mile Cold. Every Mile Paid.&lt;/title&gt; and H1 'Every mile cold. Every mile paid.' The only 'Cleveland' occurrences on the homepage are placeholder="e.g. Cleveland → Columbus, ~12 stops" (form input) and the footer '2800 Euclid Ave, Suite 310&lt;br/&gt;Cleveland, OH 44115'. Grep across all 7 titles and meta descriptions: zero matches for Cleveland/Ohio/C`

**Fix:** Rewrite titles keyword-first with geo modifiers, keeping taglines in og:title for social. Home: 'Refrigerated Last-Mile Delivery Network — Cleveland & the Midwest | SupplyNow' (og:title keeps 'Every Mile Cold. Every Mile Paid.'). Restaurants→distributors page: 'Refrigerated Overflow Capacity & Dedicated Lanes for Food Distributors | SupplyNow'. Suppliers: 'Cold-Chain Delivery for Food & Beverage Manufacturers — Ohio & Midwest | SupplyNow'. Network: 'Refrigerated Delivery Coverage — Cleveland, Columbus, Detroit + 6 Metros | SupplyNow'. Work the metro names into descriptions and at least one H2 per page ('Nine Midwest metros: Cleveland, Columbus, Detroit…').

</details>

<details><summary><b>[cross:seo]</b> No structured data of any kind — zero JSON-LD, zero schema.org markup on all 7 pages — compounded by the already-verified missing sitemap.xml and robo…</summary>

**Issue:** No structured data of any kind — zero JSON-LD, zero schema.org markup on all 7 pages — compounded by the already-verified missing sitemap.xml and robots.txt (both 404). There is no Organization or LocalBusiness entity for Google to attach the name, logo, Cleveland address, phone, or service area to, so the site is forfeiting knowledge-panel eligibility, local-pack signals, and rich-result eligibility despite having every needed data point (NAP, phone, LinkedIn, logo) already sitting in the footer of every page.

**Evidence (verbatim):** `grep for 'application/ld+json' and 'schema.org' returns zero matches across home.html, restaurants.html, suppliers.html, network.html, press.html, contact.html, privacy.html. Meanwhile the footer of every page contains exactly the data schema should carry: 'Asset-light cold-chain logistics.&lt;br/&gt;2800 Euclid Ave, Suite 310&lt;br/&gt;Cleveland, OH 44115', tel:+12165487070, mailto:aaron@supplyno`

**Fix:** Add a sitewide JSON-LD block (in the shared layout head): Organization + LocalBusiness (@type: 'LocalBusiness' or 'MovingCompany'/'Service') with name 'SupplyNow, Inc.', url 'https://www.supplynow.io', logo, address {streetAddress: '2800 Euclid Ave, Suite 310', addressLocality: 'Cleveland', addressRegion: 'OH', postalCode: '44115'}, telephone '+1-216-548-7070', email, sameAs [LinkedIn], and areaServed listing the nine metros. The site is Astro — add @astrojs/sitemap to generate sitemap.xml at build, and ship a robots.txt with 'Sitemap: https://www.supplynow.io/sitemap-index.xml'. On press.html, additionally consider ItemList of the 13 coverage links.

</details>

## Appendix: per-page detail

### `/home` (home) — 7/10

**Title tag:** SupplyNow — Every Mile Cold. Every Mile Paid.  
**Meta description:** Cold-chain last mile for food distributors and manufacturers — a vetted refrigerated network that turns the empty ride home into delivered, in-temperature loads. Twelve months, zero temperature incidents. Restaurant Depot runs it daily.  
**Funnel job:** Primary demand-gen / conversion page: convince ops and supply-chain leaders at food distributors and manufacturers that SupplyNow's vetted refrigerated network beats owning trucks, brokers, courier apps, or 3PLs — and convert them into a low-risk "quote a lane" pilot lead via the on-page form (with WhatsApp/founder-email fallbacks). Target reader: a skeptical fleet/ops decision-maker evaluating cost per delivered mile and cold-chain risk.

**Strengths:**
- Sharp, differentiated headline that encodes both value props in eight words: "Every mile cold. Every mile paid."
- Quantified claims throughout rather than adjectives: 20–25% under in-house cost, $98 vs $126/hr, 0 incidents in 12 months, 9 metros, timed 5-step onboarding
- Low-risk offer framing at the conversion point: "No contract to start — one lane, then you decide." plus a pilot-with-scorecard structure
- Single conversion goal (#quote) reinforced by CTAs in every section, a short 3-required-field form, and low-friction fallbacks (WhatsApp, founder email, "Talk to Aaron")
- Strong objection handling: "Why not just use a broker or a load board?" / "Why not build our own fleet?" FAQ plus a 6-row comparison table against all four real alternatives
- Interactive empty-mile calculator turns the pitch into the prospect's own numbers, with honest framing: "these are your inputs, not ours"
- Audience segmentation done in-page: hero toggle, paired distributor/manufacturer cards, and segment-specific emotional copy ("No more drivers missing routes. No more angry calls.")
- Scannable structure: eyebrows, short sections, stat band, chips, numbered steps with time estimates, and a mobile "Swipe to compare →" hint on the wide table
- Named anchor customer (Restaurant Depot) and credible institutional signals (Techstars, Gordon Food Service, Forbes 30 Under 30, Crain's) above the fold

**Top 3 fixes:**
1. Kill the turnaround contradiction at the conversion point: make the form's "within one business hour" and step 2's "24–48 hr" say the same thing (one number, both places) — this is the cheapest trust repair on the page.
1. Server-render real defaults in the empty-mile calculator so it never displays "$0": render $305,760/yr and $25,480/mo (matching the 12-truck × 350-mile × $1.40 defaults) in the static HTML, with JS updating from there.
1. Replace investor-only proof with customer proof: swap the anonymous "first call" prospect quote for a named customer quote with a result, and substantiate the Restaurant Depot claim with a number and (with permission) a logo or case-study link — it is the page's strongest asset and currently rests on one unsupported clause.

**All issues:** 3 high · 14 medium · 10 low

<details><summary><b>HIGH</b> — Direct numeric contradiction at the conversion point: the form promises a quote in one business hour while step 2 of the adjacent rail promi…</summary>

**Issue:** Direct numeric contradiction at the conversion point: the form promises a quote in one business hour while step 2 of the adjacent rail promises 24–48 hours — a skeptical ops buyer sees the conflict in a single glance and discounts every other number on the page.

**Evidence:** `Tell us the lane. We come back with capacity and a number within one business hour.`

**Fix:** Pick one truth and use it in both places. If the hour is real, change step 2's time chip from "24–48 hr" to "1 business hr". If not, change the form sub-copy to: "Tell us the lane. We come back with capacity and a number within one business day."

</details>

<details><summary><b>HIGH</b> — The calculator's result panel is server-rendered as $0/year and $0/month — before hydration, with JS blocked, or on any script failure, the …</summary>

**Issue:** The calculator's result panel is server-rendered as $0/year and $0/month — before hydration, with JS blocked, or on any script failure, the page literally says the recoverable margin is zero, directly under the claim that the backhaul is worth money. It also contradicts its own footer, which already shows computed miles (4,200).

**Evidence:** `&lt;p class="em-figure tnum" id="emYear" data-astro-cid-j7pv25f6&gt;$0&lt;/p&gt;`

**Fix:** Server-render the outputs for the default inputs (12 trucks × 350 mi × $1.40 × 52): render "$305,760" in #emYear and "$25,480" in #emMonth so the static HTML is always correct, then let JS update from there.

</details>

<details><summary><b>HIGH</b> — Proof/credibility gap: the only logo strip is investors and accelerators ("Backed by"), and the sole testimonial is an anonymous quote from …</summary>

**Issue:** Proof/credibility gap: the only logo strip is investors and accelerators ("Backed by"), and the sole testimonial is an anonymous quote from a prospect on a first sales call — not a customer with results. For a page claiming Restaurant Depot runs it daily, there is zero customer-sourced evidence.

**Evidence:** `— a national distributor's VP, first call`

**Fix:** Replace the prospect quote with a named, permissioned customer quote plus a result (e.g., "— Ops Director, [Customer], 14 lanes/week on the network"). If none is available yet, cut the figure block entirely and instead add one substantiated Restaurant Depot line to the proof band: "Daily lanes for Restaurant Depot across 9 metros — 12 months, zero temperature incidents."

</details>

<details><summary><b>MEDIUM</b> — Manufactured scarcity that contradicts the page's own no-commitment promise: you cannot ask buyers to "lock" a lane before the network "fill…</summary>

**Issue:** Manufactured scarcity that contradicts the page's own no-commitment promise: you cannot ask buyers to "lock" a lane before the network "fills" while the form section says there is no contract and one lane to start. Ops buyers recognize the pattern and it erodes the trust the zero-incident record builds.

**Evidence:** `We’re adding four metros this quarter — lock your lane before the network fills.`

**Fix:** Replace with a real, non-coercive urgency line: "Four new metros come online next quarter — lanes quoted now are priced into the launch route map." Change the "Lock a lane" CTA to "Quote a lane" to match the rest of the page.

</details>

<details><summary><b>MEDIUM</b> — Timing contradiction in the expansion story: the scarcity line says the four metros are being added "this quarter" while the line directly a…</summary>

**Issue:** Timing contradiction in the expansion story: the scarcity line says the four metros are being added "this quarter" while the line directly above says they come "in Q4" — on a page viewed in July (Q3), both cannot be true.

**Evidence:** `Next: Atlanta · Orlando · Miami · Texas in Q4.`

**Fix:** Align both statements to one date: "Next: Atlanta · Orlando · Miami · Dallas–Fort Worth — opening Q4." and "We're standing up four new metros in Q4 — quote a lane now to be on the first route map."

</details>

<details><summary><b>MEDIUM</b> — Nav labels contradict their URLs — "For Distributors" links to /restaurants and "For Manufacturers" links to /suppliers. Anyone hovering the…</summary>

**Issue:** Nav labels contradict their URLs — "For Distributors" links to /restaurants and "For Manufacturers" links to /suppliers. Anyone hovering the link (or reading the URL after clicking) sees a page about restaurants when they were promised distributors; it reads like a leftover from an older site and muddies SEO signals.

**Evidence:** `&lt;a href="/restaurants" class="nav-link text-[0.92rem] text-ink/80 transition-colors hover:text-ink"&gt;For Distributors&lt;/a&gt;`

**Fix:** Move the pages to /distributors and /manufacturers with 301 redirects from /restaurants and /suppliers, and update all hrefs (nav, both segment cards, footer).

</details>

<details><summary><b>MEDIUM</b> — The hero video's badge calls the network view "illustrative" while the caption beneath it cites precise operational data (10 routes, 46 stop…</summary>

**Issue:** The hero video's badge calls the network view "illustrative" while the caption beneath it cites precise operational data (10 routes, 46 stops, 1,454 km) — the reader cannot tell whether they are looking at real evidence or a rendering, which weakens both.

**Evidence:** `Live network · illustrative`

**Fix:** Commit to one. If the data is real: change the badge to "Network replay · June 2026". If it is a visualization: keep "Illustrative" but soften the caption to "A typical Tuesday on the network — every load in-temp." and drop the fake-precise numbers.

</details>

<details><summary><b>MEDIUM</b> — The strongest proof asset on the page — Restaurant Depot — is asserted in one clause with no logo, no case study, no numbers attached, and n…</summary>

**Issue:** The strongest proof asset on the page — Restaurant Depot — is asserted in one clause with no logo, no case study, no numbers attached, and no substantiation anywhere on the page; it carries the whole hero and meta description on trust alone.

**Evidence:** `Restaurant Depot runs it daily.`

**Fix:** Add a one-block proof module after the stat band (with permission): "Restaurant Depot has run daily lanes on the network since 2025 — [N] routes/week across [N] metros, zero temperature incidents. Read the case study →". If permission for a logo/case study is not secured, keep the claim but attach a number: "Restaurant Depot runs daily routes on the network across nine metros."

</details>

<details><summary><b>MEDIUM</b> — Meta description is ~245 characters — Google truncates around 155–160, so the SERP snippet cuts off mid-argument and both proof points (zero…</summary>

**Issue:** Meta description is ~245 characters — Google truncates around 155–160, so the SERP snippet cuts off mid-argument and both proof points (zero incidents, Restaurant Depot) are likely lost.

**Evidence:** `Cold-chain last mile for food distributors and manufacturers — a vetted refrigerated network that turns the empty ride home into delivered, in-temperature loads. Twelve months, zero temperature incidents. Restaurant Depot runs it daily.`

**Fix:** Rewrite to ~150 chars with proof up front: "Refrigerated last-mile for food distributors & manufacturers. Vetted reefer network, live temp tracking — 12 months, zero incidents. Quote a lane."

</details>

<details><summary><b>MEDIUM</b> — Unit inconsistency: the hero caption reports the network's day in kilometers while every other number on the page — including the calculator…</summary>

**Issue:** Unit inconsistency: the hero caption reports the network's day in kilometers while every other number on the page — including the calculator the reader is asked to fill in — uses miles. US trucking audiences think in miles; km reads foreign and slightly off.

**Evidence:** `One June Tuesday on the network — 10 routes · 46 stops · 1,454 km · every load in-temp.`

**Fix:** Convert: "One June Tuesday on the network — 10 routes · 46 stops · 903 miles · every load in-temp."

</details>

<details><summary><b>MEDIUM</b> — Cryptic shorthand in the comparison table: "$126/hr-class" is not a term ops buyers use — it forces the reader to decode the page's own cost…</summary>

**Issue:** Cryptic shorthand in the comparison table: "$126/hr-class" is not a term ops buyers use — it forces the reader to decode the page's own cost anchor at the exact moment it should land hardest.

**Evidence:** `Full burden ($126/hr-class)`

**Fix:** Rewrite the cell as: "Full burden — about $126/hr all-in" (matching the $98-vs-$126 framing used later in The Model section).

</details>

<details><summary><b>MEDIUM</b> — The flywheel section is written in investor-deck language, not customer language — "anchor demand," "route density," and "shared margin" des…</summary>

**Issue:** The flywheel section is written in investor-deck language, not customer language — "anchor demand," "route density," and "shared margin" describe SupplyNow's business model mechanics, and the customer benefit (your price drops over time) is left implicit.

**Evidence:** `Anchor demand builds route density; density lowers delivered cost; the savings get shared; shared savings pull in the next anchor.`

**Fix:** Reframe the lead customer-first: "The more loads that share your routes, the cheaper every delivered mile gets — and we pass the density savings back to you. Spot markets reset to zero every morning. Your lane compounds."

</details>

<details><summary><b>MEDIUM</b> — The hero segment toggle exposes the developer default state as a visible button label — "Default" is interface plumbing, not a choice a dist…</summary>

**Issue:** The hero segment toggle exposes the developer default state as a visible button label — "Default" is interface plumbing, not a choice a distributor or manufacturer would recognize as theirs.

**Evidence:** `&lt;button type="button" class="seg-btn" data-seg="default" aria-pressed="true" data-astro-cid-j7pv25f6&gt;Default&lt;/button&gt;`

**Fix:** Rename the first segment to "Overview" (or "Both"), keeping "For distributors" and "For manufacturers" as-is.

</details>

<details><summary><b>MEDIUM</b> — Three different CTA labels point at the same #quote form — "Quote a lane," "Recover this lane →," and "Lock a lane" — which makes them read …</summary>

**Issue:** Three different CTA labels point at the same #quote form — "Quote a lane," "Recover this lane →," and "Lock a lane" — which makes them read as three different commitments; "Lock" in particular implies a contract the page elsewhere says doesn't exist.

**Evidence:** `Lock a lane`

**Fix:** Standardize the primary verb: keep "Quote a lane" everywhere; the calculator CTA may stay contextual as "Quote this lane →". Delete "Lock a lane".

</details>

<details><summary><b>MEDIUM</b> — A hard-coded stat labeled "today" in static HTML: "47 lanes scored today" will be identical tomorrow, next week, and next year — the first p…</summary>

**Issue:** A hard-coded stat labeled "today" in static HTML: "47 lanes scored today" will be identical tomorrow, next week, and next year — the first prospect who visits twice sees the same "today" number and correctly concludes the "live" panel is decorative.

**Evidence:** `47&lt;/b&gt; lanes scored today`

**Fix:** Either wire the chip to real data or change the label to a claim that can't go stale: "1,400+ lanes scored to date". Also change the adjacent panel caption "Intelligent fleet network · live" to "Intelligent fleet network" if it is not actually live.

</details>

<details><summary><b>MEDIUM</b> — Contact email domain doesn't match the site domain — the site is supplynow.io but every email link is @supplynow.org; to a first-time B2B vi…</summary>

**Issue:** Contact email domain doesn't match the site domain — the site is supplynow.io but every email link is @supplynow.org; to a first-time B2B visitor this mismatch pattern-matches to phishing or sloppiness, right where they're being asked to hand over their work email.

**Evidence:** `aaron@supplynow.org`

**Fix:** Use aaron@supplynow.io everywhere on the site (keep .org as a receiving alias if that's the real inbox).

</details>

<details><summary><b>MEDIUM</b> — Two of the company's served segments — restaurants and caterers (the original text-your-order procurement customers) — have no path anywhere…</summary>

**Issue:** Two of the company's served segments — restaurants and caterers (the original text-your-order procurement customers) — have no path anywhere on this page; the page addresses only distributors and manufacturers, and the /restaurants URL now serves distributor content, so returning restaurant customers land with nothing for them.

**Evidence:** `For food distributors &amp; manufacturers`

**Fix:** If restaurants/caterers are still served, add one recovery line above the footer: "Restaurant or caterer? Text us your order list — same-day wholesale sourcing and delivery → Get started". If they are no longer served, redirect legacy restaurant traffic to a short explainer page instead of distributor copy.

</details>

<details><summary><b>LOW</b> — The default hero subhead tries to carry both audiences and three proof points in one breath — and the headline's "paid" promise only applies…</summary>

**Issue:** The default hero subhead tries to carry both audiences and three proof points in one breath — and the headline's "paid" promise only applies to distributors (manufacturers don't have an empty ride home), so half the traffic gets a promise that isn't for them until they find the toggle below the CTAs.

**Evidence:** `Cold-chain last mile for food distributors and manufacturers — a vetted refrigerated network that turns the empty ride home into delivered, in-temperature loads.`

**Fix:** Move the segment toggle above the CTA row and tighten the default subhead: "A vetted refrigerated network across nine Midwest metros. Distributors: your empty miles come home paid. Manufacturers: your product arrives in-temp, documented. No trucks to buy."

</details>

<details><summary><b>LOW</b> — Conversion plumbing risks on the form: it posts to a third-party endpoint with captcha explicitly disabled (spam leads will hit the founder …</summary>

**Issue:** Conversion plumbing risks on the form: it posts to a third-party endpoint with captcha explicitly disabled (spam leads will hit the founder inbox), and the post-submit redirect targets a /thanks page whose existence should be verified — a 404 after submission kills the lead's confidence at the peak moment.

**Evidence:** `&lt;input type="hidden" name="_captcha" value="false" data-astro-cid-j7pv25f6&gt;`

**Fix:** Confirm https://www.supplynow.io/thanks resolves with a real confirmation message ("Got it — you'll hear from Aaron within one business day"), and enable the endpoint's captcha or add server-side rate limiting alongside the existing honeypot. (Also note the code comment says "FormSpark" but the action is formsubmit.co — clean up so the next editor doesn't break it.)

</details>

<details><summary><b>LOW</b> — GFS Food Foundry appears twice in the same proof band — once as a logo in the "Backed by" row and again as plain text at the end of the "Rec…</summary>

**Issue:** GFS Food Foundry appears twice in the same proof band — once as a logo in the "Backed by" row and again as plain text at the end of the "Recognized by" line — which reads as padding the credential list.

**Evidence:** `Crain’s Cleveland · GFS Food Foundry`

**Fix:** Delete "· GFS Food Foundry" from the Recognized-by line; the logo already carries it.

</details>

<details><summary><b>LOW</b> — The "Backed by" label lumps investors (Techstars, Comeback Capital) with a strategic partner/accelerator (Gordon Food Service / GFS Food Fou…</summary>

**Issue:** The "Backed by" label lumps investors (Techstars, Comeback Capital) with a strategic partner/accelerator (Gordon Food Service / GFS Food Foundry), leaving the strongest industry signal — GFS — ambiguous: backer, partner, or customer?

**Evidence:** `Backed by`

**Fix:** Split the attribution: "Backed by Techstars & Comeback Capital · Built with Gordon Food Service's Food Foundry" — the GFS relationship is worth naming precisely.

</details>

<details><summary><b>LOW</b> — Opaque idiom in the accountability row: "owns the box" is ambiguous (the truck box? the problem?) in the one row whose entire job is removin…</summary>

**Issue:** Opaque idiom in the accountability row: "owns the box" is ambiguous (the truck box? the problem?) in the one row whose entire job is removing ambiguity about who is accountable.

**Evidence:** `One party owns the box`

**Fix:** Replace with: "One accountable party: us".

</details>

<details><summary><b>LOW</b> — Steps 03 and 04 of the lane walkthrough overlap — Deliver already promises "clean reconciliation per stop," then Reconcile restates it with …</summary>

**Issue:** Steps 03 and 04 of the lane walkthrough overlap — Deliver already promises "clean reconciliation per stop," then Reconcile restates it with a circular tagline that defines clean docs as clean proof.

**Evidence:** `The lane closes out with documented records — clean docs become clean delivery proof.`

**Fix:** Remove "with clean reconciliation per stop" from step 03, and make step 04 concrete: "Signed PODs and temp logs for every stop — proof you can forward straight to your customer."

</details>

<details><summary><b>LOW</b> — Both FAQ answers are single ~90-word paragraphs — the densest text on an otherwise scannable page, at the exact section where a skimming ops…</summary>

**Issue:** Both FAQ answers are single ~90-word paragraphs — the densest text on an otherwise scannable page, at the exact section where a skimming ops leader looks for a fast answer.

**Evidence:** `A broker sells you a truck for today. Every load is a new stranger — a new spot rate, a new gamble on whose reefer got serviced, and when something melts, no one owns it.`

**Fix:** Split each answer into two short paragraphs (problem / our answer) and bold the closing proof line ("twelve months, zero temperature incidents" and "Own the customer. Direct the capacity. Skip the depreciation.").

</details>

<details><summary><b>LOW</b> — Title tag is pure brand tagline with no category keyword a cold searcher would type ("refrigerated last mile," "cold chain delivery"), limit…</summary>

**Issue:** Title tag is pure brand tagline with no category keyword a cold searcher would type ("refrigerated last mile," "cold chain delivery"), limiting non-brand SERP relevance for the page that should rank for the category.

**Evidence:** `SupplyNow — Every Mile Cold. Every Mile Paid.`

**Fix:** Change to: "Cold-Chain Last-Mile Delivery Network | SupplyNow" and keep "Every Mile Cold. Every Mile Paid." in og:title for social shares.

</details>

<details><summary><b>LOW</b> — "Texas" is a state listed in a series of metros (Atlanta, Orlando, Miami are cities) — small, but it's exactly the kind of imprecision the r…</summary>

**Issue:** "Texas" is a state listed in a series of metros (Atlanta, Orlando, Miami are cities) — small, but it's exactly the kind of imprecision the rest of the page avoids.

**Evidence:** `Atlanta · Orlando · Miami · Texas`

**Fix:** Name the metro: "Atlanta · Orlando · Miami · Dallas–Fort Worth".

</details>

<details><summary><b>LOW</b> — The footer disclaimer quietly undercuts every stat on the page ("unaudited") without giving the reader anything to hold onto — a date range …</summary>

**Issue:** The footer disclaimer quietly undercuts every stat on the page ("unaudited") without giving the reader anything to hold onto — a date range or method would keep the honesty while preserving the numbers' weight.

**Evidence:** `Figures shown are unaudited and provided for informational purposes.`

**Fix:** Replace with: "Performance figures reflect internal network tracking, July 2025–June 2026."

</details>

### `/restaurants` — 5/10

**Title tag:** SupplyNow — Distributor Services: Grow Without Buying Trucks  
**Meta description:** SupplyNow gives food distributors overflow capacity, empty-mile backhaul, recovery delivery, and dedicated lanes on a vetted refrigerated network — tracked end to end, ~20–25% below in-house cost, off your balance sheet.  
**Funnel job:** Mid-funnel segment landing page for solution-aware food-distributor owners and ops/fleet leaders. Its job is to convert them into a low-commitment pilot: request a single lane quote ("Quote a lane") or book a founder conversation ("Talk to Aaron"). Critically, this distributor page lives on the /restaurants slug — so it also (accidentally) receives restaurant-intent traffic it does nothing to serve, even though restaurants are a core SupplyNow segment.

**Strengths:**
- H1 is benefit-led, customer-POV, and concrete: "Grow into new stores and metros — without buying trucks." — names the buyer's growth goal and kills the capex objection in one line.
- Consistent second-person framing throughout ("your fleet", "your books", "measured on your own numbers", "You keep the customer relationship; we run the trucks") — company-POV copy is nearly absent.
- Clear, disciplined two-CTA hierarchy (primary "Quote a lane" + ghost "Talk to Aaron") repeated identically at hero and close — no competing asks.
- Unusually specific economics for a logistics page: $98/hr vs $126 in-house, 20–25%, quote back "within one business hour", and named KPIs ("on-time, in-temp, cost per stop, and backhaul miles recovered").
- Strong land-and-expand risk reversal: "One lane first. Then a set. Then a metro." plus "No fixed commitment to start." lowers the pilot threshold.
- Offer cards use a scannable "Who it's for / What's included" structure with a serif payoff line each — easy to self-select into one of the four services.
- Sharp competitive wedge vs load boards: "A load board sells you a truck for a day; we run your lane every day, and review the numbers with you monthly."
- The interactive empty-mile diagram (empty return leg → paid backhaul) turns the core economic argument into a visual, with a reduced-motion fallback — good scan-ability and accessibility instincts.

**Top 3 fixes:**
1. Fix the slug/audience collision: publish this page at /distributors with a 301 from /restaurants, align the nav labels to their slugs (/distributors, /manufacturers), and build a genuine restaurant page at /restaurants ("Text us your order list. We shop 30+ wholesalers and deliver same-day, refrigerated.") — right now a core customer segment has no page and this page has the wrong URL.
1. Repair the proof stack: reconcile "nine Midwest metros" with the Atlanta/Orlando/Miami figcaption (name the real metros), turn the self-authored "Restaurant Depot trusts us" blockquote into either a genuinely attributed customer quote or a plain, permissioned results claim, state it once instead of twice, and delete or source the "unaudited figures" footer disclaimer.
1. Make the primary CTA convert on-page: embed the lane-quote form (origin, stops, temperature, cadence) on this page and point all three "Quote a lane" buttons to the on-page #quote anchor instead of shipping hot prospects back to the homepage.

**All issues:** 4 high · 8 medium · 7 low

<details><summary><b>HIGH</b> — Slug/audience mismatch: the page lives at /restaurants but every word targets distributors, and the site nav labels this URL "For Distributo…</summary>

**Issue:** Slug/audience mismatch: the page lives at /restaurants but every word targets distributors, and the site nav labels this URL "For Distributors". Restaurant-intent visitors (a core SupplyNow segment) land on freight-network copy with zero relevance; distributor prospects get a URL that contradicts what they're reading. There is no restaurant page anywhere in the nav.

**Evidence:** `&lt;link rel="canonical" href="https://www.supplynow.io/restaurants/"&gt; … &lt;p class="eyebrow" data-astro-cid-ah56de4j&gt;For distributors&lt;/p&gt; … &lt;a href="/restaurants" class="nav-link text-[0.92rem] text-ink/80 transition-colors hover:text-ink"&gt;For Distributors&lt;/a&gt;`

**Fix:** Move this page to /distributors and 301 /restaurants → /distributors. Then build a real restaurant page at /restaurants with restaurant-POV messaging, e.g. H1: "Text us your order list. We shop 30+ wholesalers and deliver same-day, refrigerated." Also rename og-distributors.jpg references and fix the sibling mismatch ("For Manufacturers" → /suppliers) at the same time.

</details>

<details><summary><b>HIGH</b> — The Proof section contradicts itself on geography: the blockquote claims "nine Midwest metros" while the figcaption two lines below lists At…</summary>

**Issue:** The Proof section contradicts itself on geography: the blockquote claims "nine Midwest metros" while the figcaption two lines below lists Atlanta, Orlando, and Miami — none of which are Midwest. A distributor doing basic diligence reads this as fabricated or sloppy proof, and it poisons every other number on the page.

**Evidence:** `Restaurant Depot trusts us with daily last-mile across nine Midwest metros — zero temperature incidents over twelve months. … Operating since 2023 · Atlanta · Orlando · Miami · Texas next in Q4`

**Fix:** Pick one true footprint and name it everywhere. E.g. figcaption: "Operating since 2023 · Cleveland · Columbus · Cincinnati · Detroit · Pittsburgh · Indianapolis · Chicago · Louisville · Nashville" (the actual nine), and delete the Atlanta/Orlando/Miami line — or if the Southeast is real, change every "Midwest" reference to match. Every geographic claim on the page must reconcile.

</details>

<details><summary><b>HIGH</b> — The "Proof" blockquote is not a testimonial — it is SupplyNow's own marketing sentence dressed in quote formatting, attributed to no one, wh…</summary>

**Issue:** The "Proof" blockquote is not a testimonial — it is SupplyNow's own marketing sentence dressed in quote formatting, attributed to no one, while name-dropping a major brand ("Restaurant Depot trusts us") with no visible authorization, logo, or spokesperson. Savvy B2B buyers recognize self-quotes and discount the whole proof section; the brand claim is also legally risky if unapproved.

**Evidence:** `&lt;p class="eyebrow" data-astro-cid-ah56de4j&gt;Proof&lt;/p&gt; &lt;blockquote class="mt-6 font-serif text-[clamp(1.5rem,3vw,2.1rem)] leading-snug tracking-[-0.012em] text-ink" data-astro-cid-ah56de4j&gt;
Restaurant Depot trusts us with daily last-mile across nine Midwest metros — zero
          temperature incidents over twelve months.
&lt;/blockquote&gt;`

**Fix:** Either get a real attributed quote ("'They run our daily last-mile across nine metros and we haven't had a single temp incident.' — [Name], Regional Ops Manager, Restaurant Depot") or reformat as a plain results claim outside blockquote markup: "Daily last-mile for Restaurant Depot across nine metros. Zero temperature incidents in 12 months." — with their written permission for the name.

</details>

<details><summary><b>HIGH</b> — The primary CTA "Quote a lane" (used 3x, including the navbar and the closing section) navigates away from this page to a homepage anchor (/…</summary>

**Issue:** The primary CTA "Quote a lane" (used 3x, including the navbar and the closing section) navigates away from this page to a homepage anchor (/#quote). The page builds a distributor-specific case, then dumps the converting visitor onto the generic homepage mid-scroll; if #quote doesn't exist there, it's a dead anchor landing at the top of the homepage.

**Evidence:** `&lt;a href="/#quote" class="cta-primary" data-astro-cid-ah56de4j&gt;Quote a lane&lt;/a&gt;`

**Fix:** Embed the lane-quote form on this page (fields: origin, stops, temperature, cadence — mirroring the copy "Origin, stops, temperature, cadence") and point all three CTAs to "#quote" on-page. If the form must stay on the homepage, at minimum link to "/#quote" only after verifying the anchor exists, and change the closing-section CTA to the on-page form.

</details>

<details><summary><b>MEDIUM</b> — The flagship proof claim is duplicated nearly verbatim (hero fine print vs Proof blockquote) with drifted wording — "in twelve months" vs "o…</summary>

**Issue:** The flagship proof claim is duplicated nearly verbatim (hero fine print vs Proof blockquote) with drifted wording — "in twelve months" vs "over twelve months". Repetition wastes the hero's scarcest real estate and the drift signals copy that wasn't proofread against itself.

**Evidence:** `Restaurant Depot trusts us with daily last-mile across nine Midwest metros — zero
        temperature incidents in twelve months.`

**Fix:** State the claim once, in the Proof section. Rewrite the hero fine print to carry only the differentiator: "A load board sells you a truck for a day. We run your lane every day — and review the numbers with you monthly."

</details>

<details><summary><b>MEDIUM</b> — "$126 in-house" is stated as a universal fact about the reader's own cost structure. Every distributor knows their in-house cost per hour, a…</summary>

**Issue:** "$126 in-house" is stated as a universal fact about the reader's own cost structure. Every distributor knows their in-house cost per hour, and the moment it isn't $126, the claim (and the paired $98) collapses. Unsourced precision invites the exact scrutiny it can't survive — and the footer then concedes the figures are "unaudited".

**Evidence:** `Each runs on the same network, tracked end to
        end, at roughly $98 per hour versus $126 in-house.`

**Fix:** Anchor the comparison to a source and a range: "roughly $98 per hour on the network — versus the $115–135/hr most distributors we've audited actually run in-house once drivers, fuel, insurance, and idle time are counted. We'll run the math on your lane before you commit."

</details>

<details><summary><b>MEDIUM</b> — The page repeatedly claims price never leads — while leading with price. The hero's emphasized close is "roughly 20–25% below your in-house …</summary>

**Issue:** The page repeatedly claims price never leads — while leading with price. The hero's emphasized close is "roughly 20–25% below your in-house cost", the services lead quotes $98 vs $126, yet two later sections insist the opposite, in two near-duplicate sentences ("never price before value" / "price never leads"). The posture contradicts the page's own behavior and the duplicate phrasing is redundant.

**Evidence:** `We talk volume and service first — never price before value.`

**Fix:** Keep the price claims (they're the page's strongest hooks) and delete both posture lines. Replace the second instance with a service commitment instead: "Origin, stops, temperature, cadence — we come back with capacity, a number, and the service plan behind it within one business hour."

</details>

<details><summary><b>MEDIUM</b> — The stats band's second tile renders a bare "0" as its headline value. At scan speed, a lone zero in a metrics row reads as missing data or …</summary>

**Issue:** The stats band's second tile renders a bare "0" as its headline value. At scan speed, a lone zero in a metrics row reads as missing data or a template bug rather than the safety record it's meant to brag about — the classic zero-that-reads-as-broken.

**Evidence:** `&lt;div class="tnum text-[1.6rem] font-semibold" data-astro-cid-ah56de4j&gt;0&lt;/div&gt; &lt;div class="mt-1 text-[0.84rem] text-subtle" data-astro-cid-ah56de4j&gt;Temp incidents · 12 months&lt;/div&gt;`

**Fix:** Make the zero unambiguous and proud: value "Zero" with label "temp incidents in 12 months" (mirroring the prose, which already spells out "zero temperature incidents").

</details>

<details><summary><b>MEDIUM</b> — Coverage ambiguity: "nine Midwest metros" is cited three times but the metros are never named, and the only cities listed (Atlanta, Orlando,…</summary>

**Issue:** Coverage ambiguity: "nine Midwest metros" is cited three times but the metros are never named, and the only cities listed (Atlanta, Orlando, Miami) contradict it. A distributor's first qualifying question — "do you cover my geography?" — is unanswerable from this page, which suppresses quote requests.

**Evidence:** `&lt;div class="tnum text-[1.6rem] font-semibold" data-astro-cid-ah56de4j&gt;9&lt;/div&gt; &lt;div class="mt-1 text-[0.84rem] text-subtle" data-astro-cid-ah56de4j&gt;Midwest metros&lt;/div&gt;`

**Fix:** Name the metros on the page — under the stats band or in the Proof figcaption: "Cleveland · Columbus · Cincinnati · Detroit · Pittsburgh · Indianapolis · Chicago · Louisville · Nashville" (use the real list) — and add "Not on the list? Ask — the network is adding metros quarterly."

</details>

<details><summary><b>MEDIUM</b> — "Off your balance sheet" / "off your books" appears five times across the page (hero, meta description, Overflow card, Dedicated Lanes payof…</summary>

**Issue:** "Off your balance sheet" / "off your books" appears five times across the page (hero, meta description, Overflow card, Dedicated Lanes payoff line, How-it-works step 3, plus "off your books" in the hero). By the third repetition the phrase stops registering and starts reading like a tic; it also crowds out other benefits (speed, reliability, accountability).

**Evidence:** `Take a route off your balance sheet — you keep the customers, we run the trucks.`

**Fix:** Keep it twice — hero and the Dedicated Lanes payoff line. Replace the others: Overflow card → "no trucks to buy, no drivers to hire"; step 3 → "Hand us a metro — or follow us into the next one as the network grows."

</details>

<details><summary><b>MEDIUM</b> — The footer disclaimer flatly undercuts every stat the page just made ("zero temperature incidents", "20–25%", "$98 vs $126"). "Unaudited" is…</summary>

**Issue:** The footer disclaimer flatly undercuts every stat the page just made ("zero temperature incidents", "20–25%", "$98 vs $126"). "Unaudited" is the last word a skeptical buyer reads before deciding whether to trust the proof section it contradicts.

**Evidence:** `Figures shown are unaudited and provided for informational purposes.`

**Fix:** Remove it, or convert hedge into methodology: "Cost and service figures reflect SupplyNow lane data, Jan 2025–Jun 2026; we'll share the underlying scorecard for your lane on request." Specific sourcing builds trust where a blanket disclaimer destroys it.

</details>

<details><summary><b>MEDIUM</b> — "Texas next in Q4" is undated — Q4 of which year? The page footer says 2026 and it's already July; if this shipped in 2025 the claim is stal…</summary>

**Issue:** "Texas next in Q4" is undated — Q4 of which year? The page footer says 2026 and it's already July; if this shipped in 2025 the claim is stale or already false, and expansion promises that quietly expire train visitors to distrust the rest.

**Evidence:** `Operating since 2023 · Atlanta · Orlando · Miami · Texas next in Q4`

**Fix:** Date it ("Texas — Q4 2026") and calendar its removal at launch; or drop the roadmap tease entirely and only list live metros.

</details>

<details><summary><b>LOW</b> — "Talk to Aaron →" assumes the visitor knows who Aaron is — he's never introduced on the page. The company has real founder credibility (Tech…</summary>

**Issue:** "Talk to Aaron →" assumes the visitor knows who Aaron is — he's never introduced on the page. The company has real founder credibility (Techstars, Forbes 30 Under 30) that goes completely unused, so the CTA reads oddly familiar instead of impressive.

**Evidence:** `Talk to Aaron →`

**Fix:** Change the CTA to "Talk to Aaron, our founder →" and add one line near the closing CTA: "Aaron Mihaly founded SupplyNow in Cleveland in 2023 — Techstars '24, Forbes 30 Under 30. He still quotes every new lane himself." (adjust facts to reality).

</details>

<details><summary><b>LOW</b> — Insider jargon spikes in the How-it-works lead: "asset-light never means uncontrolled" is a rebuttal to an objection framed in 3PL-industry …</summary>

**Issue:** Insider jargon spikes in the How-it-works lead: "asset-light never means uncontrolled" is a rebuttal to an objection framed in 3PL-industry vocabulary; "operator-led" in the hero is similarly undefined. Ops buyers know "backhaul" and "deadhead", but these two phrases are supplier-side self-talk, not buyer language.

**Evidence:** `Every leg runs on our software,
          temperature tracked end to end — asset-light never means uncontrolled.`

**Fix:** Rewrite in the buyer's terms: "Every leg runs on our software with live temperature tracking — you get the control of your own fleet without owning one." In the hero, replace "vetted, operator-led refrigerated network" with "a vetted refrigerated network run by working operators, not a broker desk."

</details>

<details><summary><b>LOW</b> — The page's best differentiator — the load-board comparison — is buried in 0.82rem fine print under the hero CTAs, stapled to the (duplicated…</summary>

**Issue:** The page's best differentiator — the load-board comparison — is buried in 0.82rem fine print under the hero CTAs, stapled to the (duplicated) Restaurant Depot claim. The single sharpest competitive line on the page is set at the least readable size in the least prominent slot.

**Evidence:** `A load board sells you a truck for a day; we run
        your lane every day, and review the numbers with you monthly.`

**Fix:** Promote it to its own short section (or the Proof figcaption) with an H2 like "Not a load board. Not a broker." and the existing line as the body. Free the hero fine print for a single trust element (e.g. "Quotes back within one business hour").

</details>

<details><summary><b>LOW</b> — The KPI list "on-time, in-temp, cost per stop" is recited three separate times (Dedicated Lanes card, Pilot Lane card, "Measured on your dat…</summary>

**Issue:** The KPI list "on-time, in-temp, cost per stop" is recited three separate times (Dedicated Lanes card, Pilot Lane card, "Measured on your data" box), and "monthly per-branch reviews" twice more. The measurement story is a strength, but triple-stating the same list reads as padding on an otherwise tight page.

**Evidence:** `Every lane reports back on on-time, in-temp, cost per stop, and backhaul miles recovered —
          the numbers your own ops team already lives by.`

**Fix:** Keep the full list once, in the "Measured on your data" box. In the cards, reference it: Pilot Lane → "Start with one lane, measured on your scorecard from day one."; Dedicated Lanes → "with monthly per-branch scorecard reviews."

</details>

<details><summary><b>LOW</b> — Contact email domain doesn't match the site domain — the site is supplynow.io but the footer email is @supplynow.org. Careful B2B buyers (an…</summary>

**Issue:** Contact email domain doesn't match the site domain — the site is supplynow.io but the footer email is @supplynow.org. Careful B2B buyers (and their spam filters) treat cross-domain contact details as a phishing tell.

**Evidence:** `aaron@supplynow.org`

**Fix:** Display aaron@supplynow.io in the footer (alias it to the .org inbox if that's where mail actually lives), or add matching domains so every touchpoint reads consistently.

</details>

<details><summary><b>LOW</b> — Title tag leads with the brand and a generic label ("Distributor Services") instead of the search phrase a distributor would use, and the me…</summary>

**Issue:** Title tag leads with the brand and a generic label ("Distributor Services") instead of the search phrase a distributor would use, and the meta description runs ~215 characters — Google will truncate it around 160, cutting the "off your balance sheet" close.

**Evidence:** `SupplyNow — Distributor Services: Grow Without Buying Trucks`

**Fix:** Title: "Refrigerated Overflow Capacity & Dedicated Lanes for Food Distributors | SupplyNow". Meta (156 chars): "Overflow capacity, backhaul, recovery delivery, and dedicated lanes on a vetted refrigerated network — 20–25% below in-house cost. Lane quotes in one hour."

</details>

<details><summary><b>LOW</b> — The diagram toggle "Run a backhaul on it →" is styled with an arrow like the page's navigation CTAs, but it's a UI state toggle that also au…</summary>

**Issue:** The diagram toggle "Run a backhaul on it →" is styled with an arrow like the page's navigation CTAs, but it's a UI state toggle that also auto-fires after 2.2 seconds — a visitor who clicks expecting to start a backhaul gets an animation, and one who reads after the auto-flip sees the confusing inverse label "Show the empty mile ←".

**Evidence:** `Run a backhaul on it →`

**Fix:** Relabel as an obvious demo control without the CTA arrow — "See it as a paid backhaul" / "See it empty again" — and visually distinguish it from cta-primary/cta-ghost styles.

</details>

### `/suppliers` — 6.5/10

**Title tag:** SupplyNow — Cold Last-Mile for Food & Beverage Manufacturers  
**Meta description:** SupplyNow moves your product's last mile held to temperature — frozen and refrigerated delivery with a documented cold chain, a 12-month zero-temperature-incident record, and no fleet to buy. For food & beverage producers shipping to distributors, retail DCs, and stores.  
**Funnel job:** Mid-funnel segment landing page ("For Manufacturers") whose job is to convert food & beverage manufacturers' ops/supply-chain decision-makers into a lane-quote request or a founder conversation — positioning SupplyNow as an asset-light, documented cold-chain last-mile carrier (a freight-services offer distinct from the core text-to-order procurement product). Target reader: a plant/logistics manager or founder at a frozen/refrigerated CPG producer who currently self-delivers or uses unmonitored carriers and fears rejected pallets, chargebacks, and fleet capex.

**Strengths:**
- Outcome-led, customer-POV headline and relentless 'your dock / your product / your numbers' framing — almost no we-centric company talk above the fold.
- High mechanism specificity where most competitors stay vague: per-load temp records, 34–40°F safe band, pickup-to-drop monitoring, 'on-time, in-temp, cost per stop, backhaul miles recovered' as pilot metrics.
- The risk narrative mirrors the buyer's real nightmare chain verbatim: 'Rejected pallet → Freight claim → Retailer chargeback → Brand damage'.
- Low-friction, well-sequenced offer: 'Start with one lane. Earn the next.' and 'One real load, tracked and documented, then you decide. No contract to start.' — a genuinely good land-and-expand pitch.
- Excellent scannability: eyebrows, chips, numbered rails, a stat strip, and short leads — no walls of text; the closing CTA card even tells the prospect exactly what to send ('origin, stops, temperature, cadence').
- Consistent two-tier CTA system (Quote a lane / Talk to Aaron) repeated at open and close; founder-direct contact is a credible differentiator for a startup.
- Pricing model is actually explained ('usage-based — you pay for the loads and miles you actually use'), which most logistics sites hide entirely.

**Top 3 fixes:**
1. Kill the trust contradictions: reconcile 'Retainer coverage' with 'No fleet to carry, no fixed commitment' / 'No contract to start' in the How-you-pay block, delete both 'never price before value' lines in favor of a 24-hour-quote promise, and replace the footer's 'Figures shown are unaudited' disclaimer with a record-methodology line — a page whose whole thesis is 'the record wins the dispute' cannot disclaim its own record.
1. Add verifiable proof: name or quantify the case study (product, dollars at risk, hours to recovery, a pull-quote), and surface the company's real credibility assets — 200+ customers, Techstars, Forbes 30 Under 30 founder, press — in a strip under the proof tiles; also upgrade the 'Live'/'Clean' adjective tiles to real numbers like '100% of loads sensor-tracked'.
1. Keep the conversion on the page: embed a manufacturer-specific lane-quote form at #quote on /suppliers (origin dock, temp band, stops/week) instead of routing all three primary CTAs to the generic homepage anchor, and introduce Aaron in one line so 'Talk to Aaron' lands with cold traffic.

**All issues:** 4 high · 9 medium · 9 low

<details><summary><b>HIGH</b> — Direct pricing-model contradiction: two of the three services are sold 'on a retainer' with a 'Retainer coverage' chip, while the closing of…</summary>

**Issue:** Direct pricing-model contradiction: two of the three services are sold 'on a retainer' with a 'Retainer coverage' chip, while the closing offer promises no fixed commitment and no contract — a diligence-minded ops buyer will catch this and distrust the rest of the page.

**Evidence:** `How you pay: usage-based — you pay for the loads and miles you actually use. No fleet to carry, no fixed commitment.`

**Fix:** Reconcile the two models explicitly in the 'How you pay' block: 'How you pay: usage-based — per load and per mile on scheduled lanes, no fixed commitment, no contract to start. Recovery & Redelivery is the one exception: an optional standing retainer so a truck is already yours the day a load gets refused.'

</details>

<details><summary><b>HIGH</b> — The footer legally disclaims the exact proof the entire page is built on. The core argument is 'the record is what wins the dispute,' then t…</summary>

**Issue:** The footer legally disclaims the exact proof the entire page is built on. The core argument is 'the record is what wins the dispute,' then the site's own fine print says its figures are unaudited — undercutting the zero-incident record, the 9-metro claim, and the case study in one line.

**Evidence:** `Figures shown are unaudited and provided for informational purposes.`

**Fix:** Replace the blanket disclaimer with a methodology line that adds credibility instead of subtracting it: 'Temperature record: continuous sensor logs on every load; an incident is any reading outside the contracted band. Ask us for the raw per-load logs.' If legal insists on a disclaimer, scope it ('Metro counts approximate') rather than disclaiming all figures.

</details>

<details><summary><b>HIGH</b> — Zero named or third-party proof on the page: no customer names or logos, no customer count, and none of the company's real credibility asset…</summary>

**Issue:** Zero named or third-party proof on the page: no customer names or logos, no customer count, and none of the company's real credibility assets (Techstars, Forbes 30 Under 30 founder, ~200 customers) appear anywhere. For a claim this bold ('zero incidents'), the page asks to be taken entirely on its own word.

**Evidence:** `9 Midwest metros · live temp & route monitoring · clean per-load records · operating since 2023.`

**Fix:** Add a credibility strip under the proof tiles: '200+ food businesses move product on the SupplyNow network · Techstars-backed · Founder named to Forbes 30 Under 30 · As seen in [press outlet]' — and link 'Press' from the body, not just the footer.

</details>

<details><summary><b>HIGH</b> — All three primary 'Quote a lane' CTAs route off this segment page to a homepage anchor (/#quote), dumping a manufacturer prospect into a gen…</summary>

**Issue:** All three primary 'Quote a lane' CTAs route off this segment page to a homepage anchor (/#quote), dumping a manufacturer prospect into a generic form and losing the page's manufacturer-specific framing mid-conversion.

**Evidence:** `Quote a lane`

**Fix:** Embed the quote form on /suppliers itself (make the CTA href '#quote' local) with manufacturer-specific fields — origin dock, temp band (frozen/refrigerated), stops per week, metros — and pre-fill segment='manufacturer' so Aaron's follow-up is contextual.

</details>

<details><summary><b>MEDIUM</b> — 'Never price before value' is classic seller-POV sales-speak that reads as price evasion ('this will be expensive'), and it appears twice ne…</summary>

**Issue:** 'Never price before value' is classic seller-POV sales-speak that reads as price evasion ('this will be expensive'), and it appears twice nearly verbatim — in the section lead and again inside Pilot Lane step 1.

**Evidence:** `We talk volume and service first, never price before value.`

**Fix:** Cut both instances and replace the lead with a buyer-POV speed promise: 'Tell us the lane and weekly volume — you'll have a per-stop number within one business day. One lane proves the model on your own numbers, then it scales as far as you want it to.'

</details>

<details><summary><b>MEDIUM</b> — The eyebrow 'What it costs' mislabels a fear/risk section — a prospect scanning for pricing jumps here and finds a temperature chart instead…</summary>

**Issue:** The eyebrow 'What it costs' mislabels a fear/risk section — a prospect scanning for pricing jumps here and finds a temperature chart instead, which feels like a bait-and-switch and buries the actual pricing info at page bottom.

**Evidence:** `What it costs`

**Fix:** Rename the eyebrow to 'What's at stake' (the H2 'You make the product. The last mile is where it gets risked.' already carries that meaning), and let the 'Get started' card own the 'How you pay' story.

</details>

<details><summary><b>MEDIUM</b> — A dated roadmap promise is embedded in evergreen 'How it works' copy, and the list mixes three cities with a state — it will read as stale t…</summary>

**Issue:** A dated roadmap promise is embedded in evergreen 'How it works' copy, and the list mixes three cities with a state — it will read as stale the day Q4 passes and as sloppy today.

**Evidence:** `including Q4 expansion into Atlanta, Orlando, Miami, and Texas`

**Fix:** Rewrite step 3 as: 'Roll out across metros as you grow — new markets open every quarter; ask Aaron what's next on the map — without the fleet, the hiring, or the depots.' If naming markets, use parallel units: 'Atlanta, Orlando, Miami, and Dallas–Fort Worth.'

</details>

<details><summary><b>MEDIUM</b> — The proof window doesn't match the company age: 'operating since 2023' (three years) but the incident record only covers twelve months — a s…</summary>

**Issue:** The proof window doesn't match the company age: 'operating since 2023' (three years) but the incident record only covers twelve months — a skeptical buyer's first question is 'what happened before the last 12 months?'

**Evidence:** `zero temperature incidents over twelve months`

**Fix:** If the record genuinely extends further, claim it: 'zero temperature incidents since our first monitored load in 2023.' If monitoring launched later, say so and defuse the question: 'zero temperature incidents in the 12 months since sensor monitoring went on every load.'

</details>

<details><summary><b>MEDIUM</b> — Two of the four proof-strip 'stats' are adjectives ('Live', 'Clean') styled like metrics — they dilute the two real numbers (0 and 9) and ma…</summary>

**Issue:** Two of the four proof-strip 'stats' are adjectives ('Live', 'Clean') styled like metrics — they dilute the two real numbers (0 and 9) and make the strip half-empty on inspection.

**Evidence:** `Clean`

**Fix:** Replace with quantities: 'Live' tile → '100% — Loads sensor-tracked, pickup to drop'; 'Clean' tile → '1 per load — Temperature record delivered with every drop' (or 'ºF-stamped — Every stop, every load').

</details>

<details><summary><b>MEDIUM</b> — The 'Proof story' case study is anonymous and numberless — no product category, no dollar value at risk, no recovery time, no customer attri…</summary>

**Issue:** The 'Proof story' case study is anonymous and numberless — no product category, no dollar value at risk, no recovery time, no customer attribution — so the page's only narrative proof is unverifiable.

**Evidence:** `A delivery went wrong. The account didn't.`

**Fix:** Add three concrete details (even anonymized): 'A frozen-entrée maker's pallet was refused at a retail DC at 9:40am — $14K of product hours from a chargeback. Recovered same-day, redelivered in-temp by 3pm, records in the buyer's inbox that evening. The account renewed.' Ideally close with a named pull-quote from the manufacturer.

</details>

<details><summary><b>MEDIUM</b> — Segment naming is inconsistent across slug, nav, and copy: the URL says 'suppliers', the page says 'For manufacturers', the meta says 'produ…</summary>

**Issue:** Segment naming is inconsistent across slug, nav, and copy: the URL says 'suppliers', the page says 'For manufacturers', the meta says 'producers', and the nav item 'For Distributors' points at a /restaurants slug — prospects who notice URLs get mixed signals about who each page is for.

**Evidence:** `For Distributors`

**Fix:** 301 /suppliers → /manufacturers and /restaurants → /distributors so slugs match nav labels; standardize on 'manufacturers' in body copy and metadata (drop 'producers' from the meta description).

</details>

<details><summary><b>MEDIUM</b> — 'Vetted operators' is asserted twice but never defined, and the page never addresses standard cold-freight objections — carrier insurance, f…</summary>

**Issue:** 'Vetted operators' is asserted twice but never defined, and the page never addresses standard cold-freight objections — carrier insurance, food-safety compliance, chain-of-custody standards — that any retail DC shipper must clear before piloting.

**Evidence:** `run by vetted operators on the same monitoring, same documentation.`

**Fix:** Add one reassurance line to the 'Records that hold up' section: 'Every operator on the network carries [$X]M cargo and liability coverage, passes a food-handling and refrigeration-equipment inspection, and runs our sensor kit before their first load.'

</details>

<details><summary><b>MEDIUM</b> — The '9 Midwest metros' claim is never substantiated — the metros are not named anywhere on the page and there is no link to the network page…</summary>

**Issue:** The '9 Midwest metros' claim is never substantiated — the metros are not named anywhere on the page and there is no link to the network page from the claim, while the only address shown is Cleveland; the geography story asks for trust it doesn't earn.

**Evidence:** `9 Midwest metros`

**Fix:** Link the claim to /network and name anchors inline: '9 Midwest metros — Cleveland, Columbus, Pittsburgh, Detroit and more (see the network map)'.

</details>

<details><summary><b>LOW</b> — Subject-verb agreement error in an emphasized, load-bearing sentence.</summary>

**Issue:** Subject-verb agreement error in an emphasized, load-bearing sentence.

**Evidence:** `Speed and insulated packaging is a bet.`

**Fix:** Change to 'Speed and insulated packaging are a bet. A sensor on every load is a record — and the record is what wins the dispute.'

</details>

<details><summary><b>LOW</b> — Copy instructs the reader to 'watch' an animation that reduced-motion users and non-JS readers never see moving — the sentence dangles for t…</summary>

**Issue:** Copy instructs the reader to 'watch' an animation that reduced-motion users and non-JS readers never see moving — the sentence dangles for them.

**Evidence:** `watch the difference between a last mile you can't see and one that runs every mile cold.`

**Fix:** Make it motion-agnostic: 'One unmonitored mile is all it takes — below, the difference between a last mile you can't see and one that runs every mile cold.'

</details>

<details><summary><b>LOW</b> — The lead stat renders as a bare animated '0', which at a glance can read as a broken counter or placeholder before the label is parsed.</summary>

**Issue:** The lead stat renders as a bare animated '0', which at a glance can read as a broken counter or placeholder before the label is parsed.

**Evidence:** `Temperature incidents · 12 months`

**Fix:** Spell it as a word to make the brag unambiguous: 'Zero' with label 'temperature incidents in the last 12 months' (keep tnum styling; skip the count-up animation for this tile).

</details>

<details><summary><b>LOW</b> — The H1 sentence is repeated nearly verbatim three times on one page (H1, service card 01 kicker, second cine band), and 'held to temperature…</summary>

**Issue:** The H1 sentence is repeated nearly verbatim three times on one page (H1, service card 01 kicker, second cine band), and 'held to temperature' appears four more times — the motif tips into redundancy and eats space that could carry new information.

**Evidence:** `The product that leaves your dock is the product that arrives — and you can prove it.`

**Fix:** Keep the H1 and the closing cine band; change the card 01 kicker to advance the argument instead: 'Every drop closes with a temperature record your buyer can audit.'

</details>

<details><summary><b>LOW</b> — 'ACH set up' is an odd, unexplained detail in the market-entry pitch — payment rails are not a launch differentiator and the phrase reads as…</summary>

**Issue:** 'ACH set up' is an odd, unexplained detail in the market-entry pitch — payment rails are not a launch differentiator and the phrase reads as internal checklist language.

**Evidence:** `Asset-light entry into a new market — vetted operators, live monitoring, ACH set up — without standing up a depot or signing for trucks before you have the volume.`

**Fix:** Replace with a buyer-meaningful item: 'Asset-light entry into a new market — vetted operators, live monitoring, billing ready day one — without standing up a depot or signing for trucks before you have the volume.'

</details>

<details><summary><b>LOW</b> — Meta description is 271 characters — Google truncates around 155–160, so the CTA-relevant back half ('no fleet to buy... producers shipping …</summary>

**Issue:** Meta description is 271 characters — Google truncates around 155–160, so the CTA-relevant back half ('no fleet to buy... producers shipping to distributors, retail DCs, and stores') is cut in SERPs.

**Evidence:** `SupplyNow moves your product's last mile held to temperature — frozen and refrigerated delivery with a documented cold chain, a 12-month zero-temperature-incident record, and no fleet to buy. For food & beverage producers shipping to distributors, retail DCs, and stores.`

**Fix:** Trim to ~155 chars: 'Frozen & refrigerated last-mile delivery for food manufacturers — documented cold chain, 12 months with zero temperature incidents, no fleet to buy.'

</details>

<details><summary><b>LOW</b> — Service card 02's serif kicker restates the card body it sits directly under instead of adding anything.</summary>

**Issue:** Service card 02's serif kicker restates the card body it sits directly under instead of adding anything.

**Evidence:** `One hiccup downstream stops being a write-off.`

**Fix:** Replace the kicker with a concrete beat: 'Refused at 9am. Redelivered in-temp by 2pm.'

</details>

<details><summary><b>LOW</b> — Contact email domain (.org) doesn't match the site domain (.io) — a small trust snag for a first-time B2B visitor deciding whether an email …</summary>

**Issue:** Contact email domain (.org) doesn't match the site domain (.io) — a small trust snag for a first-time B2B visitor deciding whether an email is legitimate.

**Evidence:** `aaron@supplynow.org`

**Fix:** Publish aaron@supplynow.io on the site (keep .org as a receiving alias) so the visible email matches the domain in the address bar.

</details>

<details><summary><b>LOW</b> — 'Talk to Aaron' assumes the reader knows who Aaron is — he is never introduced on the page, so the personal CTA loses its founder-access pun…</summary>

**Issue:** 'Talk to Aaron' assumes the reader knows who Aaron is — he is never introduced on the page, so the personal CTA loses its founder-access punch for cold traffic.

**Evidence:** `Talk to Aaron →`

**Fix:** Add a one-line intro near the closing CTA: 'Aaron is SupplyNow's founder (Techstars, Forbes 30 Under 30) — he still quotes every manufacturer lane himself.'

</details>

### `/network` — 6/10

**Title tag:** The Network — SupplyNow Cold-Chain Last Mile  
**Meta description:** Nine Midwest metros, the outlier lanes the big distributors abandon, and a Q4 expansion into Atlanta, Orlando, Miami and Texas — run on a vetted non-CDL refrigerated network, with margin engineered as a science.  
**Funnel job:** Mid-funnel capability/coverage page. Its job is to convince a freight decision-maker (a distributor's ops lead or a food & beverage manufacturer's supply-chain manager, plus the Restaurant Depot-style anchor accounts) that SupplyNow's refrigerated network has the coverage, density economics, and cold-chain discipline to be trusted with a lane — and convert that belief into a "Quote a lane" submission. It is the proof-of-capability step between the homepage promise and the quote form.

**Strengths:**
- One clear conversion action repeated with consistent hierarchy — 'Quote a lane' appears as the primary CTA in nav, hero, and closing, never competing with itself.
- The closing CTA copy is excellent plain-language conversion writing: 'Tell us the lane. We'll come back with a number.' — zero jargon, zero friction, states exactly what happens next.
- Named anchor customer (Restaurant Depot) is concrete, verifiable proof most logistics pages lack.
- Genuinely differentiated wedge positioning — 'The lanes the big distributors hand back — past the metro edge, where coverage is hard and the margin hides' is a memorable, defensible story.
- Highly scannable structure: short sections, stat chips on the globe, a 4-card lever grid, a 3-card coverage grid — no walls of text; mobile CSS even scales the chips down.
- Specific operational detail (150-mile radius, day-level route telemetry, two-shift asset utilization) instead of generic 'reliable, flexible, on-time' platitudes.
- Moments of correct customer-POV economics translation: 'the delivered cost comes down for everyone on the route, and that saving is shared, not kept.'
- WhatsApp CTA ships with a pre-filled message ('I'd like a lane quote'), removing composition friction.

**Top 3 fixes:**
1. Flip the economics section from company-POV to customer-POV: retitle 'Margin as a science' → 'Your delivered cost' with H2 'Dense routes cost less to run. You keep the difference.', rewrite the ≈18-hours card and the 'Density is the moat' caption to state what the reader saves — the whole middle of the page currently pitches SupplyNow's P&L to the person paying it.
1. Stop routing the only conversion action off-page: give /network its own embedded quote form (or a dedicated /quote page) instead of sending every 'Quote a lane' click back to the homepage anchor, and pass lane context into the form.
1. Make every number survive a skeptical logistics buyer: 1,454 km → 904 miles; name all nine metros and reconcile 'Midwest' with Wilkes-Barre; replace 'Texas' with the actual metro so '+4' adds up; date 'Q4' as 'Q4 2026'; back 'Twelve months, zero excursions' with the sensor-logging mechanism; and delete the footer's 'unaudited' disclaimer that undercuts all of it.

**All issues:** 3 high · 13 medium · 6 low

<details><summary><b>HIGH</b> — The page's centerpiece section is framed around SupplyNow's own profitability, not the customer's outcome. 'Margin as a science' as a sectio…</summary>

**Issue:** The page's centerpiece section is framed around SupplyNow's own profitability, not the customer's outcome. 'Margin as a science' as a section header on a customer-facing page reads as 'we've engineered how much we make off you' — pitch-deck framing pointed at the wrong audience.

**Evidence:** `Margin as a science`

**Fix:** Reframe the section from company economics to customer delivered cost. Eyebrow: 'Your delivered cost'. H2: 'Dense routes cost less to run. You keep the difference.' Keep the lever cards but flip each payoff line to the reader (the lead paragraph's 'that saving is shared, not kept' already shows the right move — make it the section's headline idea, not a footnote).

</details>

<details><summary><b>HIGH</b> — A food-safety-grade claim ('zero excursions' over twelve months) is asserted with no substantiation — no monitoring method, no logger vendor…</summary>

**Issue:** A food-safety-grade claim ('zero excursions' over twelve months) is asserted with no substantiation — no monitoring method, no logger vendor, no audit trail — and is then directly undercut by the footer's own disclaimer that figures are unaudited. A QA manager at a manufacturer will probe exactly this claim.

**Evidence:** `Live temperature on every leg.Twelve months, zero excursions.`

**Fix:** Back the claim with its mechanism: 'Sensor-logged temperature on every leg — timestamped, exportable, shared on request. Twelve months without a single out-of-temp delivery.' Then remove or narrow the footer disclaimer so it doesn't contradict the page's strongest trust claim.

</details>

<details><summary><b>HIGH</b> — Every primary CTA ('Quote a lane') navigates away from this page to a homepage anchor. The conversion action requires a full page change bac…</summary>

**Issue:** Every primary CTA ('Quote a lane') navigates away from this page to a homepage anchor. The conversion action requires a full page change back to '/', losing the network-page context, adding load time, and creating back-button confusion — a classic leak on the page's only conversion path.

**Evidence:** `&lt;a href="/#quote" class="cta-primary" data-astro-cid-ef4fiqgb&gt;Quote a lane&lt;/a&gt;`

**Fix:** Embed the quote form at the bottom of /network (give this page its own #quote section) or route to a dedicated /quote page. At minimum, pass context so the form knows the visitor came from the network page (e.g. /#quote?src=network) and pre-select 'lane quote'.

</details>

<details><summary><b>MEDIUM</b> — 'Density is the moat' is investor vocabulary — moats are what founders promise VCs, not what shippers buy. On a customer page it frames dens…</summary>

**Issue:** 'Density is the moat' is investor vocabulary — moats are what founders promise VCs, not what shippers buy. On a customer page it frames density as SupplyNow's competitive defense rather than the customer's price advantage.

**Evidence:** `Density is the moat.`

**Fix:** Rewrite the video caption to the customer's benefit: 'Density is why it costs less. Every metro feeds the next.'

</details>

<details><summary><b>MEDIUM</b> — Geographic error inside the page's headline claim: Wilkes-Barre is in northeastern Pennsylvania, not the Midwest — and only six of the 'nine…</summary>

**Issue:** Geographic error inside the page's headline claim: Wilkes-Barre is in northeastern Pennsylvania, not the Midwest — and only six of the 'nine' metros are named, hiding the claim the H1 leads with. Logistics buyers know exactly where Wilkes-Barre is; this single word makes the flagship number look unchecked.

**Evidence:** `Daily cold-chain routes across Ohio and the states next door — Cleveland, Detroit, Akron,
            Columbus, Indianapolis, Wilkes-Barre and more — anchored by Restaurant Depot.`

**Fix:** Either drop 'Midwest' ('Nine metros' / heading 'Nine metros, Midwest to Mid-Atlantic') or drop Wilkes-Barre from the Midwest framing. And name all nine metros — 'and more' undercuts a page whose H1 is literally a count.

</details>

<details><summary><b>MEDIUM</b> — The '+4' expansion math counts a state as a metro. Atlanta, Orlando, and Miami are metros; 'Texas' is not — so the chip's '+4' and the card'…</summary>

**Issue:** The '+4' expansion math counts a state as a metro. Atlanta, Orlando, and Miami are metros; 'Texas' is not — so the chip's '+4' and the card's list use inconsistent units, and the reader can't tell if Texas means one city or five.

**Evidence:** `Atlanta · Orlando · Miami · Texas`

**Fix:** Name the actual Texas metro(s): 'Atlanta · Orlando · Miami · Dallas–Fort Worth' — or if multiple Texas cities are planned, change the chip from '+4 Q4 expansion' to '+4 markets · Q4' and the heading to 'Atlanta · Orlando · Miami · Texas Triangle'.

</details>

<details><summary><b>MEDIUM</b> — The proof stat is in kilometers for an American Midwest freight audience. US shippers, carriers, and rate sheets run on miles; 'km' reads as…</summary>

**Issue:** The proof stat is in kilometers for an American Midwest freight audience. US shippers, carriers, and rate sheets run on miles; 'km' reads as either a data-export artifact or copy written by someone who doesn't run these roads — and it sits in the page's only telemetry proof line.

**Evidence:** `1,454 km · 46 stops · 10 routes · every load in-temp.`

**Fix:** Convert to miles: '904 miles · 46 stops · 10 routes · every load in-temp.'

</details>

<details><summary><b>MEDIUM</b> — The expansion is dated only 'Q4' with no year — in title, meta, chip, and card. It's July 2026; readers can't tell if this means Q4 2026 or …</summary>

**Issue:** The expansion is dated only 'Q4' with no year — in title, meta, chip, and card. It's July 2026; readers can't tell if this means Q4 2026 or is stale copy from last year, and the page will silently rot after December.

**Evidence:** `Next · Q4`

**Fix:** Date it everywhere it appears: 'Next · Q4 2026', and in the meta description 'a Q4 2026 expansion into Atlanta, Orlando, Miami and Dallas–Fort Worth'.

</details>

<details><summary><b>MEDIUM</b> — The meta description — the page's ad in search results — is written in internal company language: 'non-CDL' is fleet-ops jargon (and can mis…</summary>

**Issue:** The meta description — the page's ad in search results — is written in internal company language: 'non-CDL' is fleet-ops jargon (and can misread as 'less-qualified drivers'), and 'margin engineered as a science' is about SupplyNow's P&L, not the searcher's problem.

**Evidence:** `run on a vetted non-CDL refrigerated network, with margin engineered as a science.`

**Fix:** Rewrite the meta customer-first: 'Refrigerated delivery across nine metros — including the outlier lanes big distributors hand back. Expanding to Atlanta, Orlando, Miami and Dallas–Fort Worth in Q4 2026. Tell us the lane; we'll come back with a number.'

</details>

<details><summary><b>MEDIUM</b> — The H1 is three insider fragments that assume the reader already knows what SupplyNow is and what 'outlier lanes' means (it's the company's …</summary>

**Issue:** The H1 is three insider fragments that assume the reader already knows what SupplyNow is and what 'outlier lanes' means (it's the company's own coinage). A first-time visitor arriving from search or a shared link gets no category, no service, no benefit above the fold until the subhead.

**Evidence:** `Nine metros. The outlier lanes. The expansion.`

**Fix:** Keep the rhythm, ground the meaning: 'Nine metros. The lanes big distributors hand back. Four more markets by Q4.' — or ground it via the eyebrow: change 'The network' to 'The refrigerated network'.

</details>

<details><summary><b>MEDIUM</b> — The hero's second CTA sends visitors backwards in the funnel. Prime hero real estate — the moment of highest attention — is spent on an exit…</summary>

**Issue:** The hero's second CTA sends visitors backwards in the funnel. Prime hero real estate — the moment of highest attention — is spent on an exit link instead of a deeper engagement step.

**Evidence:** `← Back to home`

**Fix:** Replace with a forward action: 'See where we run ↓' anchoring to the coverage globe, or 'Talk to Aaron' → /contact. The browser back button already handles 'back to home'.

</details>

<details><summary><b>MEDIUM</b> — One idea — the paid mile home — is repeated in near-identical words four times (hero, section lead, lever card, signature line), and 'densit…</summary>

**Issue:** One idea — the paid mile home — is repeated in near-identical words four times (hero, section lead, lever card, signature line), and 'density' appears in five separate blocks. The page spends its length restating one insight instead of adding proof.

**Evidence:** `turns the empty mile home into a paid load — margin you&#39;ve already paid for, collected.`

**Fix:** Keep the signature line ('The empty mile home is margin you've already paid for.') as the single statement of the idea. Rewrite the 'Density not deadhead' card to the customer outcome: 'Multi-drop plus backhaul means the truck is never running empty on your dime — the return leg is already carrying someone's load.'

</details>

<details><summary><b>MEDIUM</b> — A blanket footer disclaimer tells readers not to trust any number on the page — including '150-mile radius', 'zero excursions', and the tele…</summary>

**Issue:** A blanket footer disclaimer tells readers not to trust any number on the page — including '150-mile radius', 'zero excursions', and the telemetry line. It's investor-deck hedging pasted onto a sales page, and it plants doubt at the exact moment of decision.

**Evidence:** `Figures shown are unaudited and provided for informational purposes.`

**Fix:** Delete it, or narrow it to something that adds credibility instead of subtracting it: 'Operational figures self-reported from our telematics, June 2026.'

</details>

<details><summary><b>MEDIUM</b> — The page's only performance proof is a single cherry-picked day. One good Tuesday is anecdote, not evidence — and it hard-codes a date that …</summary>

**Issue:** The page's only performance proof is a single cherry-picked day. One good Tuesday is anecdote, not evidence — and it hard-codes a date that goes stale. There is also no other third-party proof anywhere on the page (no customer count, no testimonial, no Techstars/press credentials) beyond the Restaurant Depot mention.

**Evidence:** `One June Tuesday on the network —`

**Fix:** Replace with rolling telematics totals: 'Last 90 days on the network: [miles] · [stops] · 100% of loads in-temp.' Add one credibility strip (customer count, a one-line shipper quote, or press/Techstars marks) between the globe and the economics section.

</details>

<details><summary><b>MEDIUM</b> — 'Vetted' is the hero's lead adjective but the page never says what vetting means — no insurance standard, no temp-audit, no acceptance rate.…</summary>

**Issue:** 'Vetted' is the hero's lead adjective but the page never says what vetting means — no insurance standard, no temp-audit, no acceptance rate. An unsupported 'vetted' reads as filler to exactly the buyer this page targets.

**Evidence:** `One vetted, operator-led reefer network`

**Fix:** Add one proof sentence where the network is described: 'Every operator carries reefer-grade insurance, passes a cold-chain audit, and runs a logged temperature sensor on every leg.'

</details>

<details><summary><b>MEDIUM</b> — The '≈18 hours' lever card is written from the asset owner's ledger — 'the same asset keeps earning', 'fixed cost spread thin' — with no tra…</summary>

**Issue:** The '≈18 hours' lever card is written from the asset owner's ledger — 'the same asset keeps earning', 'fixed cost spread thin' — with no translation to what the reader gets. It's the clearest example of the section's company-POV problem at card level.

**Evidence:** `Two shifts, not nine-to-five. We rotate operators so the same asset keeps earning across the day — fixed cost spread thin.`

**Fix:** Rewrite the card body: 'Two operator shifts keep each truck working ~18 hours a day instead of eight — so your rate isn't paying for idle iron.'

</details>

<details><summary><b>LOW</b> — The stat line's own math undercuts the density story: 46 stops across 10 routes is 4.6 stops per route — thin for a page arguing multi-drop …</summary>

**Issue:** The stat line's own math undercuts the density story: 46 stops across 10 routes is 4.6 stops per route — thin for a page arguing multi-drop density is the moat. A sharp logistics reader will do this division.

**Evidence:** `46 stops · 10 routes`

**Fix:** Show the stat that flatters the thesis: drop the route count ('904 miles · 46 stops · every load in-temp') or cite a dense-day per-route figure instead.

</details>

<details><summary><b>LOW</b> — The title tag positions the service as 'Last Mile' while the hero claims a 150-mile operating radius — regional haul, not last mile. The two…</summary>

**Issue:** The title tag positions the service as 'Last Mile' while the hero claims a 150-mile operating radius — regional haul, not last mile. The two claims describe different businesses to a freight-literate reader.

**Evidence:** `The Network — SupplyNow Cold-Chain Last Mile`

**Fix:** Align the title with the actual scope: 'The Network — SupplyNow Refrigerated Coverage & Lanes' (or, if last-mile is genuinely the core, say 'last-mile and regional' in the hero).

</details>

<details><summary><b>LOW</b> — Contact email domain (.org) doesn't match the site domain (.io). Domain mismatch on the conversion contact is a small phishing-pattern trigg…</summary>

**Issue:** Contact email domain (.org) doesn't match the site domain (.io). Domain mismatch on the conversion contact is a small phishing-pattern trigger for procurement teams.

**Evidence:** `aaron@supplynow.org`

**Fix:** Use aaron@supplynow.io on the .io site (alias the .org mailbox), or add a note if .org is the canonical company domain.

</details>

<details><summary><b>LOW</b> — Nav labels contradict their URL slugs: 'For Distributors' links to /restaurants and 'For Manufacturers' links to /suppliers. The destination…</summary>

**Issue:** Nav labels contradict their URL slugs: 'For Distributors' links to /restaurants and 'For Manufacturers' links to /suppliers. The destination pages match the labels (confirmed), but the mismatched slugs show in the status bar, shared links, and analytics, and read like a mis-link.

**Evidence:** `&lt;a href="/restaurants" class="nav-link text-[0.92rem] text-ink/80 transition-colors hover:text-ink"&gt;For Distributors&lt;/a&gt;`

**Fix:** 301-redirect the legacy slugs to label-matching URLs: /restaurants → /distributors, /suppliers → /manufacturers.

</details>

<details><summary><b>LOW</b> — The eyebrow label 'The network' appears twice within two screens — over the hero and again as the video-band caption — spending a slot that …</summary>

**Issue:** The eyebrow label 'The network' appears twice within two screens — over the hero and again as the video-band caption — spending a slot that could carry new information.

**Evidence:** `&lt;p class="cine-eyebrow" data-astro-cid-ef4fiqgb&gt;The network&lt;/p&gt;`

**Fix:** Change the video-band eyebrow to something additive, e.g. 'On the road' or 'A Tuesday, 6 a.m.'

</details>

<details><summary><b>LOW</b> — 'Talk to Aaron' assumes the reader knows who Aaron is — nothing on this page introduces him, wasting real founder credibility (Forbes 30 Und…</summary>

**Issue:** 'Talk to Aaron' assumes the reader knows who Aaron is — nothing on this page introduces him, wasting real founder credibility (Forbes 30 Under 30, Techstars).

**Evidence:** `Talk to Aaron`

**Fix:** Add a title to the CTA or its surroundings: 'Talk to Aaron, our founder — he prices lanes himself.'

</details>

### `/press` — 6/10

**Title tag:** Recognition & Press — SupplyNow  
**Meta description:** Forbes 30 Under 30. Techstars. The awards, press, and talks that have followed SupplyNow and founder Aaron George since day one.  
**Funnel job:** Mid-funnel trust/validation page: give prospects doing vendor diligence (plus journalists, investors, and partners) click-verifiable third-party proof — awards, accelerators, press, talks — that this small startup is legitimate, then route the warmed reader to the quote request on the homepage (/#quote). Likely readers: a restaurant/manufacturer/distributor decision-maker vetting SupplyNow before trusting it with perishable supply, and secondarily media researching the company.

**Strengths:**
- Highly scannable ledger structure — three labeled sections (Awards & accelerators / In the press / Podcasts & talks), one-line rows with source, headline, and date; zero wall-of-text, works well on mobile (flex-col to flex-row).
- Every credibility claim is click-verifiable: all 13 rows link out to the actual third-party source (Forbes, Techstars, Crain's, YouTube, etc.) with target=_blank rel=noopener — rare honesty for a press page.
- Consistent conversion spine: hero and closing band both push the same single action (/#quote), so the page never scatters intent across competing offers.
- 'Talk to Aaron →' as the closing secondary CTA is a genuinely good founder-led-sales move — personal, low-friction, matches how a 200-customer company actually sells.
- Title tag and meta description are specific, name the two strongest badges (Forbes, Techstars), and are well-formed for a press-page SERP; canonical, OG, and Twitter tags all present.

**Top 3 fixes:**
1. Rewrite the conversion action in customer language: change 'Get a lane quote'/'Quote a lane' (and 'The lanes are open.') to 'Get a same-day quote' / 'The record is public. Put us to work.' — the page's only CTA currently speaks freight-broker jargon to restaurant, caterer, and manufacturer buyers, and also fix the nav label/URL mismatch ('For Distributors' → /restaurants) it funnels into.
1. Fix recency and curation in one pass: sort all three lists newest-first with consistent 'Mon YYYY' dates, cut the PR Newswire duplicate and the two visa stories (or move them to a founder sub-list), and add any 2025–26 coverage — if none exists, drop 'since day one' and anchor the subhead to current traction instead ('Forbes 30 Under 30. Techstars ’24. The public record behind the 200+ kitchens we supply today.').
1. Give the page substance beyond badges: add a proof strip under the hero ('200+ Northeast Ohio kitchens supplied · 30+ wholesalers shopped per order · Same-day refrigerated delivery') and a Media block with a matching-domain press contact, one-paragraph boilerplate, and downloadable logo/fact-sheet — serving both the diligencing buyer and the journalist this page currently half-ignores.

**All issues:** 3 high · 8 medium · 6 low

<details><summary><b>HIGH</b> — The page's one conversion action is written in freight-broker jargon ('lane') that the stated core buyers — restaurants, caterers, food manu…</summary>

**Issue:** The page's one conversion action is written in freight-broker jargon ('lane') that the stated core buyers — restaurants, caterers, food manufacturers who text an order list and get same-day refrigerated delivery — do not use. It appears in the nav, hero, closing H2, and even the WhatsApp prefill, so a chef-buyer who was just convinced by the press list hits a CTA she doesn't understand.

**Evidence:** `Get a lane quote`

**Fix:** Replace all three instances with customer language: hero and closing CTA → 'Get a same-day quote'; nav → 'Get a quote'; WhatsApp prefill → 'Hi SupplyNow, I'd like a same-day delivery quote.' If the site is deliberately repositioned to distributors/freight, keep 'lane' but then the hero subhead and closing line should say who it's for (e.g. 'Refrigerated lanes for distributors — quoted same day.').

</details>

<details><summary><b>HIGH</b> — Nav labels contradict their URLs and omit the core segment: 'For Distributors' links to /restaurants and 'For Manufacturers' links to /suppl…</summary>

**Issue:** Nav labels contradict their URLs and omit the core segment: 'For Distributors' links to /restaurants and 'For Manufacturers' links to /suppliers, and there is no nav item for restaurants or caterers at all. A restaurant owner (the flagship customer) has no visible path, and anyone noticing the URL/label mismatch reads it as a broken or untrustworthy site.

**Evidence:** `&lt;a href="/restaurants" class="nav-link text-[0.92rem] text-ink/80 transition-colors hover:text-ink"&gt;For Distributors&lt;/a&gt;`

**Fix:** Make label and destination agree and cover the real segments: 'For Restaurants & Caterers' → /restaurants, 'For Manufacturers & Distributors' → /suppliers (or rename the URLs). Ship whichever direction matches the actual pages' content, but do not leave 'For Distributors' pointing at /restaurants.

</details>

<details><summary><b>HIGH</b> — Staleness undercuts the page's central claim. Today is July 2026; the newest item anywhere on the page is the Techstars Fall 2024 cohort (~1…</summary>

**Issue:** Staleness undercuts the page's central claim. Today is July 2026; the newest item anywhere on the page is the Techstars Fall 2024 cohort (~19 months old) and 11 of 13 items are from 2022–2023 — yet the hero claims continuous coverage 'since day one.' To a diligencing buyer or journalist this reads as a company the press stopped following, the opposite of the intended message.

**Evidence:** `A founder and a company the press has followed since day one.`

**Fix:** Add any 2025–2026 coverage, award, or talk (even a podcast) to the top of each list. If none exists, rewrite the subhead so it doesn't promise recency: 'Forbes 30 Under 30. Techstars ’24. The public record behind the 200+ kitchens we supply today.' — anchoring credibility to current operations instead of a dated press trail.

</details>

<details><summary><b>MEDIUM</b> — A page titled 'Recognition & Press' offers nothing for press: no media contact, no boilerplate paragraph, no fact sheet, no logo/photo asset…</summary>

**Issue:** A page titled 'Recognition & Press' offers nothing for press: no media contact, no boilerplate paragraph, no fact sheet, no logo/photo assets. The closing band gives journalists only sales CTAs, so the page fails half its own audience and forfeits easy earned coverage.

**Evidence:** `The record is public. The lanes are open.`

**Fix:** Add a 'Media' block above the footer: 'Media inquiries: aaron@supplynow.org · Download press kit (logos, founder photos, fact sheet). Boilerplate: SupplyNow is a Cleveland-based same-day wholesale food procurement and refrigerated delivery service. Customers text their order list; SupplyNow shops 30+ wholesalers and delivers same-day, refrigerated, to 200+ restaurants, manufacturers, caterers, and distributors.'

</details>

<details><summary><b>MEDIUM</b> — The page contains zero customer-outcome proof — no customer count, no wholesaler count, no delivery stat, no customer quote. Every proof poi…</summary>

**Issue:** The page contains zero customer-outcome proof — no customer count, no wholesaler count, no delivery stat, no customer quote. Every proof point is company-POV ('we won things') rather than buyer-POV ('you'll get supplied reliably'), and the H1 is purely self-referential, wasting the trust the badges earn.

**Evidence:** `Backed, and recognized.`

**Fix:** Add a three-item proof strip directly under the hero CTAs: '200+ Northeast Ohio kitchens supplied · 30+ wholesalers shopped per order · Same-day refrigerated delivery.' Optionally sharpen the H1 to buyer-POV: 'Don’t take our word for it.'

</details>

<details><summary><b>MEDIUM</b> — All three lists are in scrambled, non-chronological order with inconsistent date formats, so the scanning reader hits the oldest/weakest ite…</summary>

**Issue:** All three lists are in scrambled, non-chronological order with inconsistent date formats, so the scanning reader hits the oldest/weakest items first and the strongest recent item (Techstars 2024) is buried mid-list. Awards runs Aug 2023 → Q4 2024 → Jan 2023; the press list runs Nov 2022, Nov 2022, Mar 2023, Jun 2022, then a bare '2023'; formats mix 'Aug 2023', 'Q4 2024', and bare years.

**Evidence:** `Q4 2024`

**Fix:** Sort every section reverse-chronologically (Techstars Anywhere Fall 2024 first in Awards) and normalize all dates to 'Mon YYYY' ('Q4 2024' → 'Oct 2024'; bare '2023' → the item's actual month).

</details>

<details><summary><b>MEDIUM</b> — Two of the five press items are about a Cleveland immigrant-visa program, not about SupplyNow's business. For a buyer evaluating a food-supp…</summary>

**Issue:** Two of the five press items are about a Cleveland immigrant-visa program, not about SupplyNow's business. For a buyer evaluating a food-supply vendor they are off-message filler, and they dilute the 'press has followed the company' claim.

**Evidence:** `Global Cleveland entrepreneurial visa`

**Fix:** Move 'Global Cleveland entrepreneurial visa' (Crain’s) and 'New path for international entrepreneurs' (The Land CLE) into a separate 'About the founder' sub-list, or cut them and let the business coverage stand alone.

</details>

<details><summary><b>MEDIUM</b> — The same news event — the GFS Food Foundry fifth cohort announcement — appears twice on the page (gfs.com post in Awards, PR Newswire releas…</summary>

**Issue:** The same news event — the GFS Food Foundry fifth cohort announcement — appears twice on the page (gfs.com post in Awards, PR Newswire release in the press list), which reads as padding once a reader clicks both.

**Evidence:** `Food Foundry accelerator cohort`

**Fix:** Delete the PR Newswire row and keep only the GFS Food Foundry entry in Awards & accelerators; replace the freed press slot with a genuine business story.

</details>

<details><summary><b>MEDIUM</b> — The hero's secondary CTA sends visitors backwards out of the page instead of deepening engagement — a wasted slot given the logo and nav alr…</summary>

**Issue:** The hero's secondary CTA sends visitors backwards out of the page instead of deepening engagement — a wasted slot given the logo and nav already provide the way home.

**Evidence:** `← Back to home`

**Fix:** Replace with 'Talk to Aaron →' (/contact) — already proven in the closing band — or 'See customer results →' (/#proof).

</details>

<details><summary><b>MEDIUM</b> — The footer company descriptor is investor-deck language, not customer language; 'asset-light' means nothing to a chef and can even read as '…</summary>

**Issue:** The footer company descriptor is investor-deck language, not customer language; 'asset-light' means nothing to a chef and can even read as 'they don't own the trucks keeping my food cold.'

**Evidence:** `Asset-light cold-chain logistics.`

**Fix:** Rewrite the footer descriptor: 'Same-day wholesale food sourcing & refrigerated delivery. Cleveland, OH.'

</details>

<details><summary><b>MEDIUM</b> — The contact email domain (.org) doesn't match the site domain (.io). Careful B2B buyers and journalists treat cross-domain email as a typo o…</summary>

**Issue:** The contact email domain (.org) doesn't match the site domain (.io). Careful B2B buyers and journalists treat cross-domain email as a typo or phishing signal, exactly the doubt a trust page must not create.

**Evidence:** `aaron@supplynow.org`

**Fix:** Publish aaron@supplynow.io (alias it to the .org inbox if needed) so the visible address matches supplynow.io everywhere on the site.

</details>

<details><summary><b>LOW</b> — The hero, title, and meta description cite 'Forbes 30 Under 30' unqualified, but the linked award is the Forbes local Cleveland list ('30-un…</summary>

**Issue:** The hero, title, and meta description cite 'Forbes 30 Under 30' unqualified, but the linked award is the Forbes local Cleveland list ('30-under-30-local-2023-cleveland'). The list row discloses 'Cleveland,' the hero doesn't — press-savvy readers who click will register the gap.

**Evidence:** `Forbes 30 Under 30. Techstars. The awards, press, and talks that have followed SupplyNow and founder Aaron George since day one.`

**Fix:** Qualify it once at first mention: hero subhead and meta → 'Forbes 30 Under 30 (Cleveland). Techstars.' Precision costs little and inoculates against the 'inflated claim' read.

</details>

<details><summary><b>LOW</b> — Row labels with no information scent force clicks to evaluate credibility: one talk's source is just 'Demo Day' (which one?) and one item's …</summary>

**Issue:** Row labels with no information scent force clicks to evaluate credibility: one talk's source is just 'Demo Day' (which one?) and one item's entire description is 'Interview.'

**Evidence:** `5-minute pitch`

**Fix:** Name the org and the topic in each row: 'GFS Food Foundry — Demo Day pitch (5 min)' and 'One America Works — Building SupplyNow in Cleveland (interview).'

</details>

<details><summary><b>LOW</b> — The same primary action carries two different labels ('Quote a lane' in nav vs 'Get a lane quote' in hero/closing), a small consistency leak…</summary>

**Issue:** The same primary action carries two different labels ('Quote a lane' in nav vs 'Get a lane quote' in hero/closing), a small consistency leak that makes the reader re-parse whether these are the same thing.

**Evidence:** `Quote a lane`

**Fix:** Standardize on one label everywhere (per the high-severity fix: 'Get a quote' in nav, 'Get a same-day quote' on-page).

</details>

<details><summary><b>LOW</b> — 'View ↗' is repeated identically 13 times as the row action — generic, adds noise, and misses a free scannability cue about content type.</summary>

**Issue:** 'View ↗' is repeated identically 13 times as the row action — generic, adds noise, and misses a free scannability cue about content type.

**Evidence:** `View ↗`

**Fix:** Vary by medium: 'Read ↗' for articles, 'Watch ↗' for the four YouTube items, 'Listen ↗' for the podcast.

</details>

<details><summary><b>LOW</b> — The footer disclaimer about unaudited figures appears on a page that shows no figures at all, planting doubt ('what figures? what's unaudite…</summary>

**Issue:** The footer disclaimer about unaudited figures appears on a page that shows no figures at all, planting doubt ('what figures? what's unaudited?') with zero offsetting benefit here.

**Evidence:** `Figures shown are unaudited and provided for informational purposes.`

**Fix:** Scope the disclaimer to pages that actually show metrics (e.g. /#proof / Results); remove it from the press page footer.

</details>

<details><summary><b>LOW</b> — H1 comma reads as a typo to most readers ('Backed, and recognized.') — a stray-comma stumble in the first three words of a page whose entire…</summary>

**Issue:** H1 comma reads as a typo to most readers ('Backed, and recognized.') — a stray-comma stumble in the first three words of a page whose entire job is polish and credibility.

**Evidence:** `Backed, and recognized.`

**Fix:** Drop the comma — 'Backed and recognized.' — or use punchier parallel fragments: 'Backed. Recognized. Verifiable.'

</details>

### `/contact` — 6.5/10

**Title tag:** Contact SupplyNow — Get a Cold-Chain Lane Quote  
**Meta description:** Tell us your lane — origin, stops, temperature, cadence — and we'll come back with capacity and a number. Cold-chain last-mile for food distributors and manufacturers.  
**Funnel job:** Bottom-of-funnel lead-capture page: convert a warm visitor — an ops/supply-chain decision-maker at a food distributor or F&B manufacturer in Northeast Ohio — into an inbound lead by getting them to submit a lane for a same-hour capacity-and-price quote, or to reach out directly via email, phone, or WhatsApp. It is the site's primary conversion endpoint alongside the homepage /#quote form.

**Strengths:**
- Concrete, differentiated response-time promise — "usually within one business hour" — restated at the form itself, which is where the anxiety lives.
- Strong risk-reversal in the hero: "No contract to start — one lane, then you decide." This is textbook bottom-funnel objection handling.
- Founder-level accessibility as a trust signal: direct founder email plus "We read every note ourselves" — human, non-corporate, credible for a startup.
- Plain-spoken, zero-buzzword microcopy: "give us the route and we come back with capacity and a number" — "a number" is confident, refreshingly unhedged pricing language.
- Highly scannable structure: short H1, one lead paragraph, labeled channel list (Email/Phone/Direct), compact 5-field form with optional fields explicitly marked "optional" — no wall of text anywhere.
- Low-friction channel redundancy, including a prefilled WhatsApp deep link ("Hi SupplyNow, I'd like a lane quote.") so the visitor never types a cold opener.
- Mobile-conscious form CSS in the copy structure (16px inputs, 44px min touch targets, single-column grid under 767px) — no iOS zoom traps.
- Title tag matches search/click intent exactly: "Get a Cold-Chain Lane Quote" tells the reader what the page will do before they arrive.
- Post-submit redirect target (/thanks) verified live — no dead-end after conversion.

**Top 3 fixes:**
1. Make the form collect what the H1 asks for: replace the generic message form with structured lane-quote fields (Origin, Stops, Temperature select, Cadence select) and a "Get my lane quote" button — the page promises a price from four inputs but never asks for them, which is the single biggest conversion leak.
1. Add credibility at the decision moment: a one-line proof strip under the form button — "Techstars alum · Forbes 30 Under 30 founder · 200+ Northeast Ohio kitchens, plants and distributors served" — the page currently asks a stranger to hand over a lead with zero third-party proof anywhere.
1. Close the trust-signal gaps around the channels: switch displayed email to the matching supplynow.io domain, add an SMS "Text us: (216) 548-7070" link for the text-native audience, and repoint the nav's "Quote a lane" CTA to this page's own form instead of routing converts back to the homepage.

**All issues:** 2 high · 6 medium · 6 low

<details><summary><b>HIGH</b> — Promise/mechanism mismatch: the H1, meta, and hero all promise a lane quote from four specific inputs (origin, stops, temperature, cadence),…</summary>

**Issue:** Promise/mechanism mismatch: the H1, meta, and hero all promise a lane quote from four specific inputs (origin, stops, temperature, cadence), but the form is a generic name/email/message form — the visitor must compose all four data points as freeform prose in one textarea. This adds cognitive friction at the exact conversion moment, produces incomplete submissions that force a follow-up email before a quote can be given, and quietly breaks the one-business-hour promise.

**Evidence:** `Tell us the lane — origin, stops, temperature, cadence — or whatever's on your mind.`

**Fix:** Replace the generic form with structured quote fields matching the promise: Origin (city or ZIP), Stops per run (number), Temperature (select: Frozen −10°F / Refrigerated 34–40°F / Ambient), Cadence (select: Daily / 3–5x per week / Weekly / One-time), plus an optional notes field. Change the button to "Get my lane quote" and keep a small "Just have a question? Email aaron@supplynow.org" escape hatch below.

</details>

<details><summary><b>HIGH</b> — The page addresses only distributors and manufacturers and speaks pure freight language — the company's stated core offer (text your order l…</summary>

**Issue:** The page addresses only distributors and manufacturers and speaks pure freight language — the company's stated core offer (text your order list, we shop 30+ wholesalers, same-day refrigerated delivery) and two named customer segments (restaurants, caterers) appear nowhere on the page, in the nav, or in the meta. A restaurant or caterer landing here has no path and no reason to believe this company serves them; that traffic bounces.

**Evidence:** `Cold-chain last-mile for food distributors and manufacturers.`

**Fix:** If restaurants/caterers are still served, add a routing line under the hero: "Restaurant or caterer? Text your order list to (216) 548-7070 — we shop 30+ wholesalers and deliver same-day, refrigerated." And extend the meta description: "Tell us your lane — origin, stops, temperature, cadence — and we'll come back with capacity and a number within one business hour. Same-day cold-chain delivery for Northeast Ohio restaurants, caterers, distributors and food manufacturers." If the reposition to pure logistics is deliberate, make it explicit somewhere so procurement-intent visitors self-select out instead of bouncing confused.

</details>

<details><summary><b>MEDIUM</b> — CTA conflict: the persistent nav's primary button sends visitors OFF the contact page to the homepage quote anchor (/#quote), directly compe…</summary>

**Issue:** CTA conflict: the persistent nav's primary button sends visitors OFF the contact page to the homepage quote anchor (/#quote), directly competing with this page's own form. Two primary CTAs for the same action on one screen splits clicks and the nav one costs a full page load.

**Evidence:** `Quote a lane`

**Fix:** On /contact only, point the nav CTA at the on-page form (href="#message" with an id on the quote-card) or swap its label to "Quote below ↓" — never route a visitor away from the page whose entire job is the same conversion.

</details>

<details><summary><b>MEDIUM</b> — Zero third-party proof at the decision moment: no Techstars, no Forbes 30 Under 30, no customer count, no testimonial, no press logo anywher…</summary>

**Issue:** Zero third-party proof at the decision moment: no Techstars, no Forbes 30 Under 30, no customer count, no testimonial, no press logo anywhere on the page. The only credibility element is a self-asserted service claim. A contact page is where skeptics do their final gut-check.

**Evidence:** `We read every note ourselves and reply within one business hour.`

**Fix:** Add a one-line proof strip directly beneath the form button: "Techstars alum · Forbes 30 Under 30 founder · 200+ Northeast Ohio kitchens, plants and distributors served." One line, no logos required, placed where the hesitation happens.

</details>

<details><summary><b>MEDIUM</b> — Freight jargon in the H1 and hero ("lane", "cadence", "capacity") reads fluently to a 3PL buyer but is opaque to owner-operators of restaura…</summary>

**Issue:** Freight jargon in the H1 and hero ("lane", "cadence", "capacity") reads fluently to a 3PL buyer but is opaque to owner-operators of restaurants, caterers, and smaller food manufacturers — a named segment of the business. "Tell us the lane." is meaningless to someone who thinks in routes and deliveries.

**Evidence:** `Tell us the lane.`

**Fix:** Keep the punchy H1 for the logistics audience but translate the lead into plain movement language: "Where it starts, where it stops, how cold it rides, how often it runs — give us the route and we come back with capacity and a price, usually within one business hour."

</details>

<details><summary><b>MEDIUM</b> — Email domain does not match the site domain (.org email on a .io website) — a classic phishing-pattern signal, surfaced three times on the o…</summary>

**Issue:** Email domain does not match the site domain (.org email on a .io website) — a classic phishing-pattern signal, surfaced three times on the one page whose job is to earn a stranger's outreach. Some B2B recipients' IT filters and plenty of humans will hesitate.

**Evidence:** `aaron@supplynow.org`

**Fix:** Register/alias aaron@supplynow.io (forwarding to the .org inbox) and use the .io address everywhere on supplynow.io, or at minimum add "(yes, .org — long story, same company)" style disarming microcopy. Matching domains is the cheaper fix.

</details>

<details><summary><b>MEDIUM</b> — The response-time promise is stated inconsistently — hedged in the hero ("usually") but absolute at the form — and "business hour" is undefi…</summary>

**Issue:** The response-time promise is stated inconsistently — hedged in the hero ("usually") but absolute at the form — and "business hour" is undefined because no operating hours appear anywhere on the page. A Friday 7pm submitter has no idea when the clock starts, and the absolute version sets up a broken promise.

**Evidence:** `usually within one business hour`

**Fix:** Unify both instances and anchor the term: "We read every note ourselves and reply within one business hour (Mon–Sat, 7am–6pm ET; after hours, first thing next morning)."

</details>

<details><summary><b>MEDIUM</b> — No SMS option despite texting being the product's native interaction model (customers text their order lists). WhatsApp is offered three tim…</summary>

**Issue:** No SMS option despite texting being the product's native interaction model (customers text their order lists). WhatsApp is offered three times, but WhatsApp has thin adoption among US independent food businesses; the frictionless channel the audience already uses is plain SMS.

**Evidence:** `Prefer to talk? WhatsApp ·`

**Fix:** Add "Text us: (216) 548-7070" as an sms:+12165487070 link ahead of WhatsApp in the "Direct" list and the form footer: "Prefer to talk? Text (216) 548-7070 · WhatsApp · aaron@supplynow.org".

</details>

<details><summary><b>LOW</b> — Nav label contradicts its URL slug: "For Distributors" resolves to /restaurants (legacy slug from the earlier positioning). The mismatch is …</summary>

**Issue:** Nav label contradicts its URL slug: "For Distributors" resolves to /restaurants (legacy slug from the earlier positioning). The mismatch is visible on hover, in the URL bar, and in shared links, and reads like a mis-link — a distributor prospect lands on a URL that says restaurants.

**Evidence:** `For Distributors`

**Fix:** Rename the route to /distributors with a 301 from /restaurants, and update all internal hrefs. (Same for /suppliers → /manufacturers to match its "For Manufacturers" label.)

</details>

<details><summary><b>LOW</b> — The Company field placeholder is the vendor's own company name, which reads as a prefilled error or a form built for internal use — momentar…</summary>

**Issue:** The Company field placeholder is the vendor's own company name, which reads as a prefilled error or a form built for internal use — momentary confusion in a field the prospect should breeze through.

**Evidence:** `placeholder="SupplyNow"`

**Fix:** Change to a neutral example: placeholder="Acme Provisions Co." — or drop the placeholder entirely since the label already says Company.

</details>

<details><summary><b>LOW</b> — The Phone field placeholder is SupplyNow's own real phone number — a visitor can mistake it for prefilled data, and any who type it verbatim…</summary>

**Issue:** The Phone field placeholder is SupplyNow's own real phone number — a visitor can mistake it for prefilled data, and any who type it verbatim pollute lead records with the company's own number.

**Evidence:** `placeholder="(216) 548-7070"`

**Fix:** Use a reserved fictional number as the example: placeholder="(216) 555-0142".

</details>

<details><summary><b>LOW</b> — Boilerplate footer disclaimer about figures appears on a page containing no figures, which reads as copy-paste template residue and plants d…</summary>

**Issue:** Boilerplate footer disclaimer about figures appears on a page containing no figures, which reads as copy-paste template residue and plants doubt ("what unaudited figures?") on a trust-critical page.

**Evidence:** `Figures shown are unaudited and provided for informational purposes.`

**Fix:** Render that legal line only on pages that actually display metrics (homepage /#proof, network page); suppress it in the footer component on /contact and /privacy.

</details>

<details><summary><b>LOW</b> — The form posts to a free third-party endpoint with captcha explicitly disabled — visible to anyone who views source, it reads hobby-grade fo…</summary>

**Issue:** The form posts to a free third-party endpoint with captcha explicitly disabled — visible to anyone who views source, it reads hobby-grade for a funded company, and honeypot-only spam protection on a public endpoint invites junk that will erode the one-hour-reply promise.

**Evidence:** `action="https://formsubmit.co/8d4ccb67255848d0e7f174ff64e13925"`

**Fix:** Move to a first-party endpoint (e.g. /api/contact via the existing Astro deployment) or a paid form backend on a custom domain, and enable a low-friction spam check; at minimum set _captcha to true.

</details>

<details><summary><b>LOW</b> — "Direct" is a mislabel for a channel group containing LinkedIn — a company-page link is the least direct channel on the page, and grouping i…</summary>

**Issue:** "Direct" is a mislabel for a channel group containing LinkedIn — a company-page link is the least direct channel on the page, and grouping it with WhatsApp dilutes the immediacy the label claims.

**Evidence:** `Direct`

**Fix:** Relabel the group "Message us" and keep WhatsApp (plus a new SMS link) in it; move LinkedIn to the footer only, or into a separate "Follow" item.

</details>

### `/privacy` — 3/10

**Title tag:** Privacy Policy — SupplyNow  
**Meta description:** SupplyNow, Inc. privacy policy.  
**Funnel job:** Trust/compliance utility page at the bottom of the funnel. Nobody converts here; its job is to survive due-diligence reads by ops/finance/legal stakeholders at food manufacturers, distributors and restaurant groups vetting SupplyNow as a vendor, plus privacy-conscious leads clicking the footer link before texting an order. Success = the reader finds a current, credible, accurate policy and leaves with trust intact. Failure = anything that reads as neglect or sloppiness on the one page whose only message is "we are careful with your data."

**Strengths:**
- The page exists, is indexed (robots index,follow), has a correct canonical, and the title tag follows the site's clean 'Page — SupplyNow' pattern — many seed-stage sites fail even this.
- Names its actual vendors — 'Mailgun' for email and 'Celero' for payments — with working links to their policies, which is more specific than most generator boilerplate.
- The Payments section carries a genuinely reassuring, concrete claim for B2B buyers: 'We will not store or collect Your payment card details' plus PCI-DSS handling by the processor.
- Section headings exist throughout (Definitions, Retention, Security, Children's Privacy, Contact Us), so the document is navigable rather than one unbroken wall of text.
- Site chrome around the policy is strong: footer gives a physical Cleveland address, a founder email, WhatsApp and LinkedIn — real, human contact channels that support trust.

**Top 3 fixes:**
1. Replace the 2022 generator boilerplate with a current, correctly-scoped policy: define the Service as the website + text/WhatsApp ordering (not just a downloadable app), describe the data SupplyNow actually collects (order lists, delivery addresses, order history), add Cookies and Your Privacy Rights sections, and refresh 'Last updated' — this fixes the four biggest diligence flags at once.
1. Run one proofread-and-repair pass on the text: fix all eight-plus corrupted apostrophes ( "s → 's, including the 'Children"s Privacy' heading), 'differ than' → 'differ from', and complete the truncated legal address so it matches the footer ('SupplyNow, Inc., 2800 Euclid Ave, Suite 310, Cleveland, OH 44115').
1. Make the Contact Us block actually work: add the missing mailto href so the page's only action is clickable, and move the privacy contact to a role address on the site's own domain (privacy@supplynow.io) instead of a bare founder email on a mismatched .org domain.

**All issues:** 4 high · 4 medium · 7 low

<details><summary><b>HIGH</b> — The page's only in-body action — the privacy contact email — is a dead anchor with no href. A reader who wants to exercise privacy rights or…</summary>

**Issue:** The page's only in-body action — the privacy contact email — is a dead anchor with no href. A reader who wants to exercise privacy rights or ask a diligence question cannot click it; on some renderers it doesn't even look like a link.

**Evidence:** `By email: &lt;a&gt;aaron@supplynow.org&lt;/a&gt;`

**Fix:** Add the href: By email: <a href="mailto:aaron@supplynow.org">aaron@supplynow.org</a>. Better: create a role address on the site's own domain and use it here and in the footer — 'By email: privacy@supplynow.io'.

</details>

<details><summary><b>HIGH</b> — Pervasive character corruption: every possessive apostrophe renders as a stray double-quote (8+ instances, including a section heading 'Chil…</summary>

**Issue:** Pervasive character corruption: every possessive apostrophe renders as a stray double-quote (8+ instances, including a section heading 'Children"s Privacy'). A legal document full of broken characters reads as neglect to exactly the diligence-minded reader this page serves.

**Evidence:** `Usage Data may include information such as Your Device"s Internet Protocol address (e.g. IP address)`

**Fix:** Global find-and-replace "s → 's across the document (Device's, Company's, Children's Privacy, parent's, third party's, application's, Service Provider's), then proofread the full text once.

</details>

<details><summary><b>HIGH</b> — The policy is nearly four years stale — 'August 06, 2022' — while the site footer says © 2026. It predates the current business (distributor…</summary>

**Issue:** The policy is nearly four years stale — 'August 06, 2022' — while the site footer says © 2026. It predates the current business (distributor network, WhatsApp ordering, ~200 customers), and any vendor-security questionnaire will flag a policy untouched since 2022.

**Evidence:** `Last updated: August 06, 2022`

**Fix:** Actually review the policy against current data practices, then update the line to 'Last updated: July 2026'. Do not just bump the date — the content must match today's operations or the mismatch becomes a legal problem instead of a cosmetic one.

</details>

<details><summary><b>HIGH</b> — Scope bug: the policy defines the Service as ONLY a downloadable mobile app — so on its face it covers neither the website it lives on nor t…</summary>

**Issue:** Scope bug: the policy defines the Service as ONLY a downloadable mobile app — so on its face it covers neither the website it lives on nor the text/WhatsApp ordering channel that is SupplyNow's actual product. A legal reviewer will notice the company's core data flow (order lists sent by SMS) is technically outside the policy.

**Evidence:** `Service refers to the Application.`

**Fix:** Rewrite the definitions: '"Website" refers to SupplyNow, accessible from https://www.supplynow.io. "Service" refers to the Website, our text and WhatsApp ordering service, and the Application, collectively.' Then add a data-practices paragraph: 'When you place an order by text or WhatsApp, we collect the contents of your messages (your order list), your delivery address, and your order history so we can purchase from wholesalers on your behalf and deliver your order.'

</details>

<details><summary><b>MEDIUM</b> — The legal entity's address is truncated mid-sentence (street only, no city/state/zip) and contradicts the footer address on the same page (4…</summary>

**Issue:** The legal entity's address is truncated mid-sentence (street only, no city/state/zip) and contradicts the footer address on the same page (4614 Prospect Ave. vs 2800 Euclid Ave). Inconsistent registered addresses on a legal page reads as either a move nobody updated or carelessness.

**Evidence:** `refers to SupplyNow Inc, 4614 Prospect Ave.`

**Fix:** Use one canonical legal address, in full: 'refers to SupplyNow, Inc., 2800 Euclid Ave, Suite 310, Cleveland, OH 44115.' (or whichever is current — and update the footer to match).

</details>

<details><summary><b>MEDIUM</b> — Unedited generator boilerplate discloses app-style data collection (camera, photo library, location) while saying nothing about the data Sup…</summary>

**Issue:** Unedited generator boilerplate discloses app-style data collection (camera, photo library, location) while saying nothing about the data SupplyNow actually handles — order lists, delivery addresses, purchase history, supplier pricing. The policy describes a product that isn't this business.

**Evidence:** `Pictures and other information from your Device"s camera and photo library`

**Fix:** Cut the camera/photo/location block unless an app truly collects it. Replace with the real inventory: 'Order information: the items you request, quantities, delivery address and window, order history, and messages you send us by text or WhatsApp.'

</details>

<details><summary><b>MEDIUM</b> — The policy claims browser-level data collection but contains no cookie/tracking-technology disclosure, and there is no user-rights section a…</summary>

**Issue:** The policy claims browser-level data collection but contains no cookie/tracking-technology disclosure, and there is no user-rights section anywhere (access, deletion, correction, state privacy rights). By 2026 norms, both omissions are diligence flags for a vendor selling to food manufacturers.

**Evidence:** `We may also collect information that Your browser sends whenever You
            visit our Service or when You access the Service by or through a
            mobile device.`

**Fix:** Add two sections: 'Cookies and Tracking Technologies' (list what the Astro site actually sets — likely just analytics, if any) and 'Your Privacy Rights': 'You may request access to, correction of, or deletion of your Personal Data at any time by emailing privacy@supplynow.io. We respond within 30 days.'

</details>

<details><summary><b>MEDIUM</b> — Boilerplate sharing clauses grant broad rights ('business partners', 'Affiliates', parent companies, promotional sharing) that a 200-custome…</summary>

**Issue:** Boilerplate sharing clauses grant broad rights ('business partners', 'Affiliates', parent companies, promotional sharing) that a 200-customer startup almost certainly doesn't use — and that spook B2B buyers whose order data reveals their menu costs and volumes.

**Evidence:** `With business partners: We may share Your
                information with Our business partners to offer You certain
                products, services or promotions.`

**Fix:** Delete the affiliates/business-partners clauses and replace with a narrower, stronger promise: 'We do not sell your personal information. We share it only with vendors who help us run the Service — payment processing (Celero), email delivery (Mailgun), and delivery logistics — under their own privacy obligations.'

</details>

<details><summary><b>LOW</b> — Seven H1 elements on one page (the title plus six section headings like 'Collecting and Using Your Personal Data' and 'Contact Us'), other s…</summary>

**Issue:** Seven H1 elements on one page (the title plus six section headings like 'Collecting and Using Your Personal Data' and 'Contact Us'), other section heads are styled <p> tags, and alignment flips between centered and left. Weak for accessibility, SEO hygiene, and scan-ability.

**Evidence:** `&lt;h1 class="text-2xl font-bold text-center my-8"&gt;Contact Us&lt;/h1&gt;`

**Fix:** Keep one H1 ('Privacy Policy'); demote all section headings to h2 and subsections to h3, all left-aligned, and convert the bold <p class="text-2xl font-bold text-left"> pseudo-headings to real h2s.

</details>

<details><summary><b>LOW</b> — Legal body copy is set at text-xl with leading-8 and mt-8 on every paragraph, padded with literal <br> spacer tags — the document is far lon…</summary>

**Issue:** Legal body copy is set at text-xl with leading-8 and mt-8 on every paragraph, padded with literal <br> spacer tags — the document is far longer and less scannable than it needs to be, especially on mobile.

**Evidence:** `&lt;/p&gt; &lt;br&gt; &lt;p class="text-2xl font-bold text-left"&gt;Interpretation&lt;/p&gt;`

**Fix:** Drop body copy to text-base, remove all <br> spacers in favor of heading margins, and tighten list-item spacing (mt-2, not mt-8) so the policy scans as a reference document.

</details>

<details><summary><b>LOW</b> — Grammar error inherited from the template: 'differ than' instead of 'differ from' in the data-transfer section.</summary>

**Issue:** Grammar error inherited from the template: 'differ than' instead of 'differ from' in the data-transfer section.

**Evidence:** `governmental jurisdiction where the data protection laws may differ
            than those from Your jurisdiction`

**Fix:** Change to '…where the data protection laws may differ from those of Your jurisdiction.'

</details>

<details><summary><b>LOW</b> — Vendor policy links use raw URLs as link text instead of descriptive anchors — minor polish and accessibility miss.</summary>

**Issue:** Vendor policy links use raw URLs as link text instead of descriptive anchors — minor polish and accessibility miss.

**Evidence:** `Their Privacy Policy can be viewed at  &lt;a href="https://www.mailgun.com/legal/privacy-policy/" rel="noreferrer" target="_blank"&gt;`

**Fix:** Rewrite as: 'See <a href="https://www.mailgun.com/legal/privacy-policy/">Mailgun's privacy policy</a>.' (same pattern for Celero). Also remove the doubled space after 'viewed at'.

</details>

<details><summary><b>LOW</b> — Privacy contact and footer email live on supplynow.org while the site is supplynow.io — a domain mismatch on the trust page pattern-matches …</summary>

**Issue:** Privacy contact and footer email live on supplynow.org while the site is supplynow.io — a domain mismatch on the trust page pattern-matches to phishing for wary readers, and a founder's personal address as the privacy contact doesn't scale.

**Evidence:** `By email: &lt;a&gt;aaron@supplynow.org&lt;/a&gt;`

**Fix:** Stand up privacy@supplynow.io (forwarding to Aaron), use it as the policy contact, and keep aaron@supplynow.org only if .org is genuinely the mail domain — in which case say so nowhere near the trust page; consistency wins.

</details>

<details><summary><b>LOW</b> — Nav label/URL mismatches in the site chrome on this page: 'For Distributors' links to /restaurants and 'For Manufacturers' links to /supplie…</summary>

**Issue:** Nav label/URL mismatches in the site chrome on this page: 'For Distributors' links to /restaurants and 'For Manufacturers' links to /suppliers — a repositioning that never re-slugged the URLs, which confuses link-hoverers and dilutes URL trust.

**Evidence:** `&lt;a href="/restaurants" class="nav-link text-[0.92rem] text-ink/80 transition-colors hover:text-ink"&gt;For Distributors&lt;/a&gt;`

**Fix:** Re-slug the pages to /distributors and /manufacturers with 301 redirects from the old paths, or relabel the nav to match the audiences the pages actually address.

</details>

<details><summary><b>LOW</b> — 'Quote a lane' — the primary nav CTA visible on this page — is freight-broker jargon. Restaurant owners and caterers don't quote lanes; they…</summary>

**Issue:** 'Quote a lane' — the primary nav CTA visible on this page — is freight-broker jargon. Restaurant owners and caterers don't quote lanes; they order food. It only speaks to the distributor segment.

**Evidence:** `&lt;a href="/#quote" class="cta-primary !px-5 !py-2.5 !text-[0.9rem]"&gt;Quote a lane&lt;/a&gt;`

**Fix:** If the site now targets distributors/manufacturers only, keep it; if restaurants and caterers still land here, change to 'Get a quote' or 'Get same-day pricing'.

</details>

---

*Generated by a 45-agent audit workflow: 7 page auditors → 3 cross-cutting auditors (consistency, funnel, SEO) → 34 adversarial verifiers → 1 synthesis. All evidence quotes verified against raw HTML.*