# CareStride — SEO deployment checklist

This document covers the operational steps that turn the prepared site into a search-indexed property. None of these can be done before the domain `carestride.health` is live and serving the HTML; they're the first 14 days of post-deployment work.

---

## Phase 1: Same day as go-live

### 1.1 Google Search Console

1. Go to https://search.google.com/search-console
2. Click "Add property"
3. Choose "URL prefix" property type and enter `https://carestride.health`
4. Verify ownership using one of:
   - **DNS TXT record** (recommended — most permanent): add the TXT record Google provides to the carestride.health DNS configuration via your domain registrar's DNS panel. Wait 5–10 minutes for propagation, then verify.
   - **HTML file upload**: download the verification file from Google, upload to the site's root, and verify. (This requires hosting access; the file must be at `https://carestride.health/google[hash].html`.)
   - **HTML meta tag**: add a `<meta name="google-site-verification" content="[token]" />` tag to the homepage `<head>`. Reasonably permanent if the homepage HTML is stable.

5. Once verified, submit the sitemap:
   - In Search Console → "Sitemaps" → enter `sitemap.xml`
   - Google will start crawling within 24-72 hours

6. Check the "URL Inspection" tool for the homepage and the 3 live city pages (`chennai`, `bangalore`, `coimbatore`). Click "Request indexing" for each.

### 1.2 Bing Webmaster Tools

1. Go to https://www.bing.com/webmasters
2. Sign in with a Microsoft account
3. Click "Add a site" and enter `https://carestride.health`
4. Verify ownership (XML file, meta tag, or DNS record — same options as Google)
5. Submit the sitemap: `https://carestride.health/sitemap.xml`
6. Bing also offers IndexNow — submit URLs directly via API for faster indexing (worth setting up if traffic justifies)

### 1.3 Quick verification tests

- Visit `https://carestride.health/sitemap.xml` in a browser — should display the XML, all 40 URLs visible
- Visit `https://carestride.health/robots.txt` — should display the crawl rules
- Visit `https://carestride.health/llms.txt` — should display the AI-readable site map
- Test sharing the homepage URL on WhatsApp — the OG image should preview correctly. If it doesn't, run https://www.linkedin.com/post-inspector/ on the URL to diagnose.
- Test sharing on Twitter/X — Twitter card validator: https://cards-dev.twitter.com/validator (requires a Twitter account)
- Validate structured data — https://search.google.com/test/rich-results — paste a URL, expect to see all 12 schemas parsed for city pages, 10 for homepage.

---

## Phase 2: First week post-launch

### 2.1 Google My Business — for each live city

CareStride should have a separate GMB listing for each operating city. This is what gets the brand into Google Maps and the local "3-pack" (the map + 3 listings shown for local queries).

For **Chennai** (founding city, do this first):

1. Go to https://www.google.com/business/
2. Sign in with a business Google account (`info@carestride.health` recommended; create the account if needed)
3. Search for "CareStride" — if no listing exists, click "Add your business to Google"
4. Enter business name: **CareStride Chennai**
5. Choose business category: **"Home health care service"** (primary), **"Nursing agency"** (secondary)
6. Service area business — select "I deliver goods and services to my customers" → enter Chennai metropolitan area as service area (don't list a public storefront address; CareStride is a marketplace, not a clinic)
7. Contact details: enter `sree@carestride.health` and direct to the website. Phone: leave blank or enter the masked Exotel number (do not list a personal number)
8. Verify the listing — Google will offer phone, postcard, or video verification. Postcard takes 5-14 days; video verification is fastest.

Repeat for **Bangalore** and **Coimbatore** as separate listings (each with the local city as service area).

**Important** — do NOT create GMB listings for Tiruchirappalli, Puducherry, or Mangalore yet. Those cities are pre-launch on the website; creating GMB listings before supply is operational creates a misleading impression. Wait until those cities are actually serving families.

### 2.2 Per-city GMB profile contents

For each GMB listing, the profile should include:

**Business description (750 char max)** — for Chennai:

> CareStride Chennai is part of India's home healthcare marketplace for verified independent nurses and physiotherapists. NurseShield-verified professionals (Aadhaar, PAN, face match, council registration cross-verification, criminal background check). Home nursing from ₹600/hr; home physiotherapy from ₹700/hr. Specialisations: elderly care, post-surgery recovery, chronic condition management, IV/injection administration, paediatric, mother and newborn, orthopaedic rehab, neurological rehab, geriatric mobility. Tamil, English, Telugu, Hindi, Malayalam supported. NRI Family Dashboard for adult children abroad. Founded by Sree, registered with Micro Pixel Private Limited.

**Posts** (publish 1-2 per week to keep the listing active):
- Article 1 launch: "We've published our first home healthcare guide..." with link to /insights/how-to-choose-home-nurse-for-elderly-parents-india
- Service highlight: "Home nursing for post-discharge in Chennai..." with link to /services/home-nursing
- City-specific: "Now serving 22 neighbourhoods across Chennai..." with link to /cities/chennai

**Photos** (upload at minimum):
- Logo (use the caduceus-in-C logo at high resolution)
- Cover image (use og-chennai.png or a city-specific image)
- 5-10 product/service photos (illustrative — but not images of patients/professionals without explicit consent)

**Q&A section** — pre-populate with anticipated questions and authoritative answers:
- "Is CareStride live in Chennai?" → "Yes, CareStride home nursing and home physiotherapy are live at pilot in Chennai. Email sree@carestride.health to enquire."
- "Which Chennai areas does CareStride serve?" → "Chennai metropolitan area including Adyar, T. Nagar, Anna Nagar, Velachery, OMR, ECR, Mylapore, Nungambakkam, and 14+ other neighbourhoods. Full list at carestride.health/cities/chennai."
- "How are nurses verified?" → "NurseShield runs five government-grade checks before listing: Aadhaar, PAN, face match, nursing council registration cross-verification, criminal background check. Verification status visible on every profile."

### 2.3 First-week monitoring

Check Search Console daily for the first 7 days:

- **Coverage** report: how many pages Google has crawled and indexed. Expect 0 the first day, 5-10 by day 3, 20-40 by day 7. If Google reports errors, debug immediately.
- **Performance** report: impression and click data — likely 0 the first week (rankings haven't established), but valuable to monitor early
- **URL Inspection**: spot-check 3-4 URLs per day to confirm they're being indexed correctly

---

## Phase 3: First month post-launch

### 3.1 Backlink building (the highest-leverage SEO investment)

Domain authority is the single largest factor in ranking that's not under direct on-page control. Building it requires real backlinks from authoritative sources. In the first month, focus on:

- **Press release / launch announcement**: write a 600-800 word press release covering CareStride's launch, the verification approach, and the founder's background. Pitch to: YourStory, Inc42, ET Health (Economic Times Healthcare), Mint, MoneyControl, Mediagiraffe, Tech in Asia. A handful of these will likely cover the story; each gives a high-authority backlink.
- **Founder profile**: Sree on LinkedIn with the CareStride link in the profile; founder profiles on AngelList / Crunchbase / similar (each contributes a backlink).
- **Industry directories**: list CareStride on Indian healthcare directories (Practo health/business profile if applicable, Lybrate business listing, Healthify business profile). Avoid spammy / low-authority directories.
- **Founder bylined article**: pitch a 1500-word op-ed to a healthcare or tech publication on a topic CareStride is positioned to talk about ("Why India's home healthcare verification problem is structural"). This is harder but produces a much stronger backlink + brand association.

### 3.2 Referring traffic monitoring

Set up Google Analytics (GA4) on the site. Add the GA4 measurement ID to every page — typically a single script tag that loads gtag.js and configures the property. (Note: this is a separate step from Search Console; both are needed.)

In GA4, create a baseline report after week 1:
- Total sessions, by source/medium
- Top-performing pages
- Top organic search queries (visible in Search Console after Google has accumulated data)
- Conversion events (email clicks to sree@carestride.health, NRI page enquiries, register-interest clicks)

### 3.3 Content cadence

The launch article portfolio is 4 guides. To maintain SEO momentum and signal active site to Google, publish at least 1 new guide per month. Suggested second-month topics:

- "Home dialysis nursing in India: cost, logistics, and what to plan for"
- "Choosing between agency-based and marketplace home nursing in India"
- "Dementia care at home in India: a guide for adult children"
- "Insurance coverage for home healthcare in India: what's covered, what's not"

Each guide should:
- Target a specific high-intent query
- Be founder-reviewed before publication
- Internal-link to relevant service, city, and related-guide pages
- Adhere to the documented editorial principles

---

## Phase 4: Months 2-3 post-launch

By weeks 8-12, indexing should have stabilised and initial rankings should be visible in Search Console. Realistic expectations:

- Long-tail queries (e.g., "home nursing Velachery Chennai", "post-knee-replacement physio guide India") — should be ranking on pages 1-3 for some
- Mid-tail queries (e.g., "home nursing Chennai", "NRI parent care India") — should be ranking on pages 3-5
- Head queries (e.g., "home nursing India", "home healthcare app") — likely still on page 5+, requires more time and authority

Domain authority is the gating factor. Without quality backlinks, the strongest on-page SEO won't break into top results for competitive head queries. With 5-10 quality backlinks (from press coverage and authoritative directories), CareStride should be competitive on long and mid-tail queries by month 3 and beginning to break through on head queries by month 6-12.

---

## Phase 5: Quarterly reviews

Every quarter, review:
- Search Console performance — which queries are driving traffic, which pages are converting
- New cities to add (when supply density permits — the framework is in place; just add the config entry and re-run `build_cities.py`)
- Article performance — which guides are ranking, which queries they're winning, which adjacent topics to write next
- Brand position drift — is anything on the site claiming outcome guarantees, listing nurses where verification can't run, or compromising the five locked principles?

---

This is the operational playbook. The HTML, schemas, and content are ready; the work above turns them into search-indexed traffic.
