# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Next.js 15 (App Router) + TypeScript in `web/`, with GSAP (ScrollTrigger, @gsap/react) for scroll-driven film beats and Three.js for the golden-thread network. Every page is a .tsx component; both routes prerender as static pages. The user moved off hand-written HTML on 2026-11-07 and the earlier Vite build was deleted.

## Users

Primary: business partners. Brands looking for third-party or white-label Ayurveda manufacturing, and resorts, hotels and independent spas looking for Gloveda wellness partnerships. They arrive to judge whether AVVVS is a credible, established manufacturer and partner, then enquire. (Confirmed by the user, 2026-11-07.)
Secondary: consumers of AVVVS medicines and Gloveda skincare, routed to the Gloveda Herbals store.

## Product Purpose

The AVVVS corporate site. Its homepage carries the brand film "The Golden Thread" as a scroll experience: nature becomes knowledge, knowledge becomes formulation, formulation becomes medicine, and that medicine becomes a modern manufacturer. It ends at four business destinations. Success is a qualified partner enquiry.

## Positioning

A documented Ayurveda institution founded in Kozhikode in 1921, with a GMP-certified factory and more than 300 classical and proprietary formulations. Not a newly invented Ayurveda brand.

## Capabilities and Constraints

- Four destinations: AVVVS Manufacturing (classical and proprietary medicines, GMP manufacturing, third-party and white-label manufacturing), Gloveda Herbals (D2C skincare and haircare), Gloveda Experience (hospitality and resort spa partnerships), Gloveda Revive (standalone spas run by AVVVS, and independent spa partnerships; user, 2026-11-08).
- Film clips arrive one at a time from the user; every beat must work before its clip exists.
- Typography and logos are set on the page, never generated inside footage.
- Website photographs from avvvs.com are reference only and must not appear in the film.
- Palette: ivory #F4EFE5 and parchment #E8D9B9 grounds, ink #1E140E. Interface accents come from AVVVS's own "Since 1921" lockup, as the user asked on 2026-11-07: deep blue #06619B (links, buttons, focus, labels) and sky blue #51BBD3 (decoration and dark grounds only). Antique gold #C3A46A is kept for the golden thread and the film. No green outside the logos themselves.
- Logos: `web/public/brand/` holds the client's brand sheet (supplied 2026-11-07) and two marks cut from it: `avvvs-mark.svg` (header, destinations) and `avvvs-since-1921.svg` (footer). Shown in their true colours, never redrawn.
- The site is light themed only, with no dark mode and no toggle (user, 2026-11-07). The film scenes stay as their footage.
- Routes: `/` (film), `/manufacturing`, `/our-history` (family history; the film keeps only a short 1921 moment, user 2026-11-07), `/journal` and `/journal/[slug]` (the old avvvs.com blog rewritten without efficacy claims, user 2026-11-08; formulation pieces need AVVVS sign-off), `/admin` (Journal admin: named accounts, block editor with live preview and a medical-claim checker; Neon Postgres + Vercel Blob; user 2026-11-08), `/community` (CSR page, renamed from Social service by the user 2026-11-08; /social-service redirects), `/privacy` and `/terms` (drafts for legal review), plus a custom 404. Shop link in the navbar goes to https://shop.avvvs.com/ (user, 2026-11-07). A first-load loader (the gold Weaving thinking orb) covers the page until fonts and the page load; the film does not follow the pointer (user, 2026-11-08).
- SEO/GEO/AEO: canonical domain from NEXT_PUBLIC_SITE_URL (default https://avvvs.com), per-page metadata and generated social cards, sitemap, robots (AI crawlers allowed, /api blocked), schema.org Organization, WebSite, Service, AboutPage, BreadcrumbList and FAQPage, visible FAQs (src/lib/faq.ts, facts only), public/llms.txt.
- Analytics: GA4 (NEXT_PUBLIC_GA_ID) and Meta Pixel (NEXT_PUBLIC_META_PIXEL_ID) load only after consent (CookieConsent: analytics and marketing categories; Analytics.tsx). Events: page_view on every route, generate_lead / Lead on a sent enquiry, a shop click. Search Console and Meta domain verification tags come from NEXT_PUBLIC_GSC_VERIFICATION and NEXT_PUBLIC_META_DOMAIN_VERIFICATION.
- Enquiries: one site-wide panel (EnquiryPanel in the layout) opened by any #enquire link; pages end with an EnquiryInvite section. Submissions go to /api/enquiry, which sends by SMTP (nodemailer) to MAIL_TO (default mail@avvvs.com) with Reply-To set to the enquirer. SMTP settings live in web/.env.local (template: web/.env.example). The site therefore needs a Node host, not a static export.

## Brand Commitments

- Name: Arya Vaidya Vilasini Vaidya Sala (AVVVS). Malayalam: ആര്യവൈദ്യ വിലാസിനി വൈദ്യശാല.
- Copy must stay historically grounded. No invented events, people, photographs or medical claims.

## Evidence on Hand

- History, people and dates: `research/01-about-us-notes.md`, `research/source-inventory.csv`.
- Founder Kaloor Neelakandan Vaidyar (1895–1967), with the blessings of Sree Narayana Guru; successor K. N. Ramadas Vaidyar (1934–1998), his son; today Managing Director Dr Manoj Kaloor, son of K. N. Ramadas Vaidyar (confirmed by the user, 2026-11-07); four generations in all, with a fourth now in the work (user, 2026-11-08; names not yet given); Navathi (90 years) 2011; centenary.
- Film footage: `animatic/`, `lookdev/`, `blender/renders/`.
- Absent and not to be fabricated: client logos, testimonials, certifications beyond GMP, capacity figures, prices.

## Product Principles

1. Credibility before persuasion: every claim on the page is one AVVVS already makes publicly.
2. The film is the proof; copy stays short and lets it work.
3. Every path ends somewhere a partner can act.
