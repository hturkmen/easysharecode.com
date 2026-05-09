# Website SEO & Content Optimization — Prompt for Dev Team

## Context

EasyShareCode.com is a Hugo-based multilingual website promoting an iOS app that helps UK eVisa holders store, manage, and access their Home Office share codes via Apple Wallet. The site currently supports 9 languages (en, de, es, fr, it, pl, pt, ro, tr).

We are launching Google Ads campaigns targeting UK eVisa holders. The website needs SEO optimization and new content to:
1. Improve Quality Score for Google Ads (landing page relevance)
2. Rank organically for share code & eVisa related searches
3. Convert visitors into app downloads

---

## Task 1: Landing Page Optimization for Google Ads

### Requirements

Create dedicated landing pages that align with our ad groups. These pages should be lightweight, fast-loading, and focused on a single conversion action (App Store download).

**Pages to create:**

1. **`/share-code-wallet/`** — Primary landing page for Ad Groups A & B
   - H1: "Store Your UK Share Code in Apple Wallet"
   - Focus: eVisa holders who want instant access to their share code
   - Content: Problem (codes expire, hard to find when needed) → Solution (store in Wallet) → Features → CTA
   - Include: App screenshot showing Wallet integration, trust signals

2. **`/right-to-rent/`** — Landing page for Ad Group C (rental)
   - H1: "Share Code Ready for Your Landlord?"
   - Focus: People about to rent who need to prove right to rent
   - Content: Scenario (viewing tomorrow, landlord asks for code) → Solution → CTA
   - Include: Step-by-step how it works

3. **`/right-to-work/`** — Landing page for Ad Group C (employment)
   - H1: "Prove Your Right to Work — Instantly"
   - Focus: Job seekers who need share code for employer verification
   - Content: Scenario (job offer, employer needs code) → Solution → CTA

4. **`/travel/`** — Landing page for Ad Group E
   - H1: "Your eVisa Share Code — Ready at the Border"
   - Focus: Travellers entering/re-entering UK
   - Content: Scenario (no WiFi at airport, need to show status) → Offline access → Wallet → CTA

5. **`/expiry-reminder/`** — Landing page for Ad Group D
   - H1: "Share Code Expiring? Get Reminded Before It's Too Late"
   - Focus: People whose codes have expired or are about to
   - Content: 30/60/90 day validity explanation → Reminder feature → CTA

### Technical Requirements for Landing Pages
- Use Hugo content pages under `content/{lang}/` with appropriate front matter
- Minimal navigation (logo + CTA only) — reduce bounce paths
- Fast loading: no unnecessary JS, optimized images
- Mobile-first design (most traffic will be mobile)
- Include structured data (FAQ schema where applicable)
- Each page needs `<meta name="robots" content="index, follow">`
- Canonical URLs set correctly
- hreflang tags for all language versions

---

## Task 2: SEO Meta Tags & Structured Data

### Homepage Meta Optimization

Update `content/en/_index.md` front matter:

```yaml
---
title: "Easy Share Code UK — Store Your Share Code in Apple Wallet"
description: "Store and manage your UK Home Office share codes securely. Add to Apple Wallet, get expiry reminders, access offline. Free iOS app for eVisa holders."
keywords: "uk share code, evisa share code, share code wallet, share code app, right to rent share code, right to work share code, home office share code"
---
```

### Structured Data to Add

Add JSON-LD to the base template (`layouts/_default/baseof.html` or equivalent):

```json
{
  "@context": "https://schema.org",
  "@type": "MobileApplication",
  "name": "Easy Share Code",
  "operatingSystem": "iOS",
  "applicationCategory": "UtilitiesApplication",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "GBP"
  },
  "description": "Store and manage your UK Home Office share codes. Apple Wallet integration, expiry reminders, offline access.",
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.8",
    "ratingCount": "UPDATE_WITH_REAL_NUMBER"
  }
}
```

Add FAQ schema to relevant pages:

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What is a UK share code?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "A share code is a 9-character code generated on GOV.UK that allows employers, landlords, and others to verify your immigration status online. It's linked to your eVisa digital immigration record."
      }
    },
    {
      "@type": "Question",
      "name": "How long is a share code valid?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Share codes have different validity periods: 30 days for right to work checks, 60 days for right to rent, and 90 days for other status checks. After expiry, you need to generate a new one."
      }
    },
    {
      "@type": "Question",
      "name": "Can I store my share code in Apple Wallet?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes, with the Easy Share Code app you can add your share code to Apple Wallet for instant access anytime, even without internet connection."
      }
    }
  ]
}
```

---

## Task 3: Blog Content for Organic SEO

### New Blog Posts to Create

Priority order based on search volume and ad relevance:

1. **"What is a UK Share Code and How to Use It (2025 Guide)"**
   - Target keywords: `uk share code`, `what is share code uk`, `how to use share code`
   - Content: Comprehensive guide explaining share codes, how to generate them, validity periods, who needs them
   - Word count: 1500-2000 words
   - Include: Step-by-step screenshots, FAQ section, internal link to app

2. **"eVisa UK: Everything You Need to Know About Digital Immigration Status"**
   - Target keywords: `uk evisa`, `evisa uk 2025`, `digital immigration status`
   - Content: What eVisa is, who has one, how to access UKVI account, connection to share codes
   - Word count: 1500-2000 words

3. **"How to Prove Right to Rent with a Share Code"**
   - Target keywords: `right to rent share code`, `prove right to rent uk`, `landlord share code`
   - Content: Step-by-step for tenants, what landlords check, how to be prepared
   - Word count: 1000-1500 words

4. **"Share Code Expired? Here's What to Do"**
   - Target keywords: `share code expired`, `share code not working`, `how long share code valid`
   - Content: Validity periods explained, what happens when expired, how to prevent issues
   - Word count: 800-1200 words

5. **"Travelling to the UK with an eVisa: What You Need at the Border"**
   - Target keywords: `travel with evisa uk`, `uk border evisa`, `immigration check uk airport`
   - Content: What to prepare, offline access importance, share code at border
   - Word count: 1000-1500 words

6. **"How to Prove Right to Work with a Share Code (Employer Guide)"**
   - Target keywords: `right to work share code`, `prove right to work uk`, `employer share code`
   - Content: Both employee and employer perspective, step-by-step
   - Word count: 1000-1500 words

### Blog Post Template (Front Matter)

```yaml
---
title: "POST TITLE"
date: 2025-XX-XX
description: "META DESCRIPTION (max 155 chars)"
keywords: ["keyword1", "keyword2", "keyword3"]
categories: ["UK Share Code Guide"]
image: "/images/blog/POST-SLUG.svg"
draft: false
---
```

### Internal Linking Strategy
- Every blog post should link to the app download at least twice (intro + conclusion)
- Cross-link between related posts
- Link from blog posts to relevant landing pages (/share-code-wallet/, /right-to-rent/, etc.)

---

## Task 4: Technical SEO Improvements

### Site Speed
- Ensure all images are optimized SVGs or WebP
- Minimize CSS/JS bundles
- Add preconnect for external resources
- Implement lazy loading for below-fold images

### Sitemap & Indexing
- Verify `sitemap.xml` includes all language versions
- Submit sitemap to Google Search Console
- Ensure `robots.txt` allows crawling of all public pages

### hreflang Implementation
- Verify all pages have correct hreflang tags for all 9 languages
- Add x-default pointing to English version

### Mobile Optimization
- Test all pages with Google PageSpeed Insights (target >90)
- Ensure tap targets are properly sized
- Verify no horizontal scroll on mobile

### Core Web Vitals
- LCP < 2.5s
- FID < 100ms
- CLS < 0.1

---

## Task 5: Conversion Optimization

### App Store Badge Placement
- Above the fold on every landing page
- Sticky CTA on mobile (bottom bar)
- After every major content section in blog posts

### Trust Signals to Add
- App Store rating badge
- Number of downloads (when available)
- "As seen on" or press mentions (when available)
- User testimonials/reviews

### A/B Testing Suggestions
- Test different hero headlines
- Test "Free" vs "Free Download" vs "Get Started Free" CTA text
- Test with/without pricing on landing pages
- Test video demo vs static screenshot

---

## Implementation Priority

| Priority | Task | Impact | Effort |
|----------|------|--------|--------|
| 1 | Landing page `/share-code-wallet/` | High (main ad landing) | Medium |
| 2 | SEO meta tags & structured data | High (Quality Score) | Low |
| 3 | Blog post #1 (What is share code) | High (organic traffic) | Medium |
| 4 | Landing pages for rent/work/travel | Medium (ad relevance) | Medium |
| 5 | Blog posts #2-6 | Medium (long-term SEO) | High |
| 6 | Technical SEO improvements | Medium (site health) | Medium |
| 7 | Conversion optimization | Medium (conversion rate) | Low-Medium |

---

## Notes for Dev Team
- All content must be created in English first, then translated to other 8 languages
- Use Hugo's i18n system for translatable strings
- Landing pages should use a minimal layout (different from blog/homepage)
- Track each landing page separately in Google Analytics (UTM parameters from ads)
- Set up Google Search Console and connect to Analytics
- Consider adding Google Tag Manager for easier conversion tracking
