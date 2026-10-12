GLAMOUR BEAUTY PRO — Production Edition (NANOESTETIC + Professional Products)
Local Development & Running
In this directory: `python3 -m http.server 8080`
Open `http://localhost:8080` in your browser.
Deployment (Cloudflare Pages)
Upload `index.html`, the `assets/` folder, and the `_headers` file without altering the structure.
The `_headers` file adds security headers (CSP, nosniff, X-Frame-Options, Referrer-Policy, Permissions-Policy) and caching for `/assets`. It works exclusively on Cloudflare Pages / Netlify; on other hosting providers, configure these headers manually at the server level.
Contacts & Links
Instagram: https://www.instagram.com/glammour_beauty
Telegram Bot (AI Consultant, Pricing & Product Selection): https://t.me/glamour_m_beauty_bot
web : https://glamourbeauty.com.ua 
The "Book", "Price & Selection", and "Check Price" buttons link directly to the bot.
Product Catalog
Section `#catalog` (located after "Products"). 34 NANOESTETIC items featuring photos, descriptions, active ingredients, and volumes. NO PRICES — pricing is available exclusively via the bot.
Category filters (Cleansing, Peeling, Serums, Masks, Creams, SPF/Tone, Pro Systems, Body/Massage).
Catalog data is generated as static HTML — cards are embedded in the DOM immediately (important for SEO, reduced-motion, and proper pin animations below).
Photos: `assets/catalog/<slug>.webp` (one per item, lazy-loaded).
Professional Catalog
Section `#professional-catalog`: 31 verified items from client materials plus a dedicated botulinum toxin block. Prices are not published.
Categories: Mesotherapy, Biorevitalization, Lipolytics, Fillers, Collagen Boosters, Periorbital Zone, and Professional Care.
Filters are keyboard-accessible; horizontally scrollable on mobile devices.
31 photos optimized in WebP format and stored in `assets/pro-catalog/`.
Medical claims, injection protocols, and dosages are intentionally omitted: final product selection is performed by a qualified specialist.
How to Add New Items or a New Brand Catalog
Add the photo to `assets/catalog/` and a new `<article class="cat-card" data-cat="...">` following the pattern of existing cards in the `#catalog` section.
For a new brand, you can duplicate the entire `#catalog` section with a different title and its own set of `data-cat` attributes.
For professional items, use `pro-card` and `data-pro-cat` within the `#professional-catalog` section; the button should link to the Telegram bot.
Hero & Animations
Hero — adaptive WebP sequence (120 desktop / 72 mobile frames), Canvas synchronized with scroll; a static poster acts as a fallback for slow connections and reduced motion.
All images, SVG logos, fonts, and animation libraries are local (no external CDNs).
Changes in This Edition
See `CHANGELOG.txt`
Multi-page Architecture
Homepage: `index.html` — without long catalogs.
Catalog Hub: `catalog/index.html`.
NANOESTETIC: `catalog/nanoesthetic.html`.
Professional Products: `catalog/professional.html` and 8 separate category pages.