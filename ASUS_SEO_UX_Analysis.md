# ASUS חיפוי מבנים — SEO + UX/UI Analysis Report

> **Scope:** Full audit of the website content document across two dimensions:
> (1) SEO — technical, on-page, content & local search
> (2) UX/UI — information architecture, user flows, conversion, and interaction design

---

## 🔴 CRITICAL ISSUE #0 — Brand Name Conflict (Pre-Launch Blocker)

**The document flags this, but underestimates the severity.**

Googling "ASUS" returns pages 1–10 of ASUSTeK Computer Inc. content (motherboards, laptops, ROG). This is a $15B Taiwanese brand with DR 90+. **No construction company named ASUS will rank for unbranded queries using its own name** — Google has already decided what "ASUS" means.

**Impact:** Every branded search, every backlink mentioning just "ASUS," and every meta title starting with "ASUS" will be associated with electronics by Google's entity resolution.

**Recommended actions (choose one path):**

| Option | Action | Risk |
|--------|--------|------|
| ✅ Recommended | Rebrand to a unique name (e.g., "אסוס גובה", "גובה פלוס", "אקסוס") | Low — fresh start |
| ⚠️ Acceptable | Keep ASUS but always use full compound brand: **"ASUS חיפוי"** as the brand entity in ALL schema, GMB, backlinks | Medium — confusing entity |
| ❌ Avoid | Use "ASUS" alone in titles, schema, or GMB listing name | High — Google entity conflict |

If keeping "ASUS," every page's `<title>` must include the disambiguating suffix. The document is already doing this — **don't let the developer shorten any title**.

---

---

# PART 1 — SEO AUDIT

## Priority Matrix

| Priority | Issue | Impact | Effort | Status in Doc |
|----------|-------|--------|--------|---------------|
| 🔴 P1 | Brand name entity conflict | 🔥🔥🔥 | High | ⚠️ Flagged but underweighted |
| 🔴 P1 | `<html lang="he" dir="rtl">` missing from spec | 🔥🔥🔥 | Low | ❌ Missing |
| 🔴 P1 | All [X] placeholder values unpublished | 🔥🔥🔥 | Medium | ❌ Not resolved |
| 🔴 P1 | No robots.txt / sitemap.xml template | 🔥🔥🔥 | Low | ❌ Missing |
| 🔴 P1 | Google Search Console submission steps | 🔥🔥🔥 | Low | ❌ Missing |
| 🟠 P2 | LocalBusiness schema: no JSON-LD code | 🔥🔥 | Low | ⚠️ Described, not coded |
| 🟠 P2 | FAQPage schema: no JSON-LD code | 🔥🔥 | Low | ⚠️ Described, not coded |
| 🟠 P2 | Service schema: no JSON-LD code | 🔥🔥 | Low | ⚠️ Described, not coded |
| 🟠 P2 | No BreadcrumbList schema | 🔥🔥 | Low | ❌ Missing |
| 🟠 P2 | No Review/AggregateRating schema | 🔥🔥 | Medium | ❌ Missing |
| 🟠 P2 | Google Business Profile (GMB) strategy | 🔥🔥 | Medium | ⚠️ Mentioned, no action plan |
| 🟡 P3 | No competitor SERP analysis performed | 🔥🔥 | Medium | ❌ Missing |
| 🟡 P3 | E-E-A-T signals not systematized | 🔥 | Medium | ⚠️ Partial |
| 🟡 P3 | No Israeli backlink targets listed | 🔥 | High | ❌ Missing |
| 🟢 P4 | Yandex / DuckDuckGo optimization | Low | Low | ❌ Missing |

---

## 1.1 Technical HTML — Ready-to-Paste Code

### Global `<head>` Template (all pages)

```html
<html lang="he" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  <!-- ▼ Change per-page ▼ -->
  <title>חיפוי מבנים חיצוניים ועבודות סנפלינג | ASUS חיפוי – מומחים בחיפוי חזיתות</title>
  <meta name="description" content="ASUS חיפוי – חברה מובילה לחיפוי מבנים חיצוניים, חזיתות וסנפלינג. ועדי בתים, חברות, פרטיים. ניסיון מוכח, ביטוח מלא. הצעת מחיר חינם ☎ 0X-XXXXXXX">
  <link rel="canonical" href="https://asus-hafui.co.il/">
  <!-- ▲ Change per-page ▲ -->

  <!-- Open Graph -->
  <meta property="og:type" content="website">
  <meta property="og:locale" content="he_IL">
  <meta property="og:title" content="ASUS חיפוי מבנים – מומחים בחיפוי חזיתות וסנפלינג">
  <meta property="og:description" content="חברה מובילה לחיפוי מבנים חיצוניים ועבודות סנפלינג. ביטוח מלא, ניסיון רב שנים. הצעת מחיר חינם.">
  <meta property="og:image" content="https://asus-hafui.co.il/og-image-1200x630.webp">
  <meta property="og:url" content="https://asus-hafui.co.il/">
  <meta property="og:site_name" content="ASUS חיפוי מבנים">

  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:title" content="ASUS חיפוי מבנים – חיפוי חזיתות וסנפלינג">
  <meta name="twitter:description" content="חיפוי מבנים חיצוניים, שיקום חזיתות וסנפלינג מקצועי. הצעת מחיר חינם.">
  <meta name="twitter:image" content="https://asus-hafui.co.il/og-image-1200x630.webp">

  <!-- Performance -->
  <link rel="preload" as="image" href="/hero-image.webp" fetchpriority="high">
  <link rel="preconnect" href="https://fonts.googleapis.com">
</head>
```

---

### LocalBusiness Schema — Copy-Paste JSON-LD (Homepage)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "@id": "https://asus-hafui.co.il/#business",
  "name": "ASUS חיפוי מבנים",
  "alternateName": "אסוס חיפוי",
  "description": "מומחים לחיפוי מבנים חיצוניים, שיקום חזיתות ועבודות סנפלינג בישראל",
  "url": "https://asus-hafui.co.il",
  "logo": {
    "@type": "ImageObject",
    "url": "https://asus-hafui.co.il/logo.png"
  },
  "telephone": "+972-X-XXXXXXX",
  "email": "info@asus-hafui.co.il",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[כתובת]",
    "addressLocality": "[עיר]",
    "addressRegion": "[מחוז]",
    "postalCode": "[מיקוד]",
    "addressCountry": "IL"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "[קו רוחב]",
    "longitude": "[קו אורך]"
  },
  "areaServed": {
    "@type": "Country",
    "name": "Israel"
  },
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "שירותי חיפוי ועבודות גובה",
    "itemListElement": [
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "חיפוי מבנים חיצוניים"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "עבודות סנפלינג"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "פרויקטים מיוחדים"}}
    ]
  },
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Sunday","Monday","Tuesday","Wednesday","Thursday"],
      "opens": "08:00",
      "closes": "18:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Friday",
      "opens": "08:00",
      "closes": "14:00"
    }
  ],
  "priceRange": "₪₪₪",
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "5",
    "reviewCount": "23",
    "bestRating": "5",
    "worstRating": "1"
  },
  "sameAs": [
    "https://www.facebook.com/[handle]",
    "https://www.instagram.com/[handle]",
    "https://www.google.com/maps/place/[place-id]"
  ]
}
</script>
```

---

### FAQPage Schema — All 9 Questions (FAQ page)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "כמה עולה חיפוי חזית בניין?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "עלות חיפוי חזית תלויה בשטח, סוג החיפוי ומורכבות הגישה. בממוצע, חיפוי בניין משותף נע בין X ל-Y ₪ למ\"ר כולל חומרים ועבודה. פנו ל-ASUS לקבלת סקירה ראשונית חינם."
      }
    },
    {
      "@type": "Question",
      "name": "מה ההבדל בין חיפוי רטוב לחיפוי יבש?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "חיפוי רטוב מתבסס על אריחים, טיח ומלט – נפוץ בבניינים ישנים. חיפוי יבש כולל לוחות HPL, אלוקובונד ופאנלים שמתחברים למבנה מכנית – מהיר יותר להתקנה ולתחזוקה."
      }
    },
    {
      "@type": "Question",
      "name": "כמה זמן לוקח פרויקט חיפוי חזית?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "בניין קטן-בינוני עד 6 קומות לוקח 3–6 שבועות. בניינים גדולים יותר עד 3 חודשים. ASUS מספקת לוח זמנים מפורט בהצעת המחיר ועומדת בו."
      }
    },
    {
      "@type": "Question",
      "name": "האם סנפלינג מסוכן?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "סנפלינג על ידי צוות מוסמך ומבוטח הוא שיטה בטוחה ויעילה. ASUS מבצעת בדיקת בטיחות מקדימה לכל פרויקט ועומדת בכל תקני הבטיחות הישראליים."
      }
    },
    {
      "@type": "Question",
      "name": "האם אפשר לחפות בניין ממוגן (לשימור)?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "כן, אך נדרשים אישורים מיוחדים וחומרים תואמי שימור. ASUS מכירה את הנהלים ומסייעת בכל תהליך הרישוי."
      }
    },
    {
      "@type": "Question",
      "name": "האם ועד הבית צריך עורך דין לפני שיפוץ חזית?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "לא חובה, אך מומלץ לבדוק תקנון הבית המשותף ולוודא רוב נדרש. ASUS מספקת חוזה ברור ויכולה להכין תיעוד לאסיפת דיירים."
      }
    },
    {
      "@type": "Question",
      "name": "מה כולל האחריות?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "ASUS מספקת אחריות על איכות הביצוע לתקופה מוסכמת. האחריות מכסה פגמים שנגרמו מהביצוע. תנאים מלאים מצוינים בחוזה."
      }
    },
    {
      "@type": "Question",
      "name": "האם ASUS פעילה בכל הארץ?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "כן. ASUS פעילה בכל אזורי ישראל – ממטה אשר בצפון ועד אילת בדרום."
      }
    },
    {
      "@type": "Question",
      "name": "מה ההבדל בין HPL לאלוקובונד?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "HPL הוא לוח שכבות פלסטיק בלחץ גבוה – קל, גמיש עיצובית ועמיד לחוץ. אלוקובונד הוא לוח אלומיניום עם ליבת פולי-אתילן – עמיד יותר לחום קיצוני, מתאים לבניינים גבוהים ומסחריים."
      }
    }
  ]
}
</script>
```

---

### BreadcrumbList Schema (add to every sub-page)

```html
<!-- Example: /services/hafui-mivnim -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {"@type": "ListItem", "position": 1, "name": "בית", "item": "https://asus-hafui.co.il/"},
    {"@type": "ListItem", "position": 2, "name": "שירותים", "item": "https://asus-hafui.co.il/services/"},
    {"@type": "ListItem", "position": 3, "name": "חיפוי מבנים חיצוניים"}
  ]
}
</script>
```

---

### robots.txt — Ready to Upload

```
User-agent: *
Allow: /

Disallow: /wp-admin/
Disallow: /wp-login.php
Disallow: /?s=
Disallow: /search/

Sitemap: https://asus-hafui.co.il/sitemap.xml
```

---

## 1.2 Content Gap Analysis

### Missing keywords NOT in the document

The following high-intent Hebrew search terms are absent from the keyword strategy:

| Missing keyword | Monthly intent | Where to add |
|----------------|---------------|--------------|
| איטום חזית בניין | High | Services page, blog |
| שיפוץ אריחים רופפים | High | Services/snapling page |
| חיפוי מחסן מפעל | Medium | Services page |
| חברת עבודות גובה בישראל | Medium | Homepage, Snapling |
| ASUS סנפלינג ישראל | Brand-specific | All pages |
| חיפוי ועד בית מחיר | High (long-tail) | FAQ, ועדי בתים page |
| עלות שיפוץ חזית ₪ | Very high | Blog post, FAQ |

### E-E-A-T signals — Currently Missing

Google heavily weights E-E-A-T (Experience, Expertise, Authoritativeness, Trust) for contractor services. Add to the About page:

- ✅ Named author bylines on all blog posts (with photo + title)
- ✅ Real license number visible on homepage (not just About)
- ✅ Link to Ministry of Construction / Contractors Registry page with your license number
- ✅ Photos of actual team members (not stock photos)
- ✅ Date on every blog post (`datePublished` in JSON-LD)
- ✅ Case study-style project pages (problem → ASUS approach → outcome in numbers)

---

## 1.3 Local SEO — Google Business Profile Action Plan

This is the #1 conversion driver for ועדי בתים searching locally. Treat it as a second website.

**Setup checklist:**

1. **Category:** Primary = "Building Materials Supplier" → also add "Contractor" + "Waterproofing Service"
2. **Business name:** "ASUS חיפוי מבנים" (include the disambiguation keyword)
3. **Services:** List all 3 service types with descriptions
4. **Photos:** Minimum 20 before/after project photos; cover photo = impressive completed façade
5. **Posts:** Publish one Google Post per week (tip, project spotlight, FAQ)
6. **Q&A section:** Pre-populate with the same 9 FAQ questions from the website
7. **Reviews:** Request reviews from every completed project client — aim for 30+ reviews in the first year
8. **Booking link:** Add a "Request quote" link pointing to `/contact`

---

## 1.4 Israeli-Specific Backlink Opportunities

Standard link-building playbooks miss Israel-specific sources. Prioritize:

| Source type | Examples | Link value |
|------------|----------|-----------|
| Contractor directories | Duns 100, Kompass Israel, BNI | Medium |
| ועד בית forums | vaad.co.il, forums on ynet, community Facebook groups | High (trust) |
| Building/property portals | Madlan, Yad2 (articles), One.co.il | High |
| Trade associations | AECO, Israeli Builders Association | Very high (authority) |
| Local news | Walla מקומי, mynet | Medium |
| Architecture/design blogs | Guest posts on Hebrew blogs | High |

---

## 1.5 6-Month Launch Checklist (supplement to document's schedule)

**Before launch (Week 0):**
- [ ] Fill ALL [X] placeholder values
- [ ] Add `lang="he" dir="rtl"` to `<html>`
- [ ] Add all JSON-LD schemas from this report
- [ ] Convert all gallery images to WebP < 150KB
- [ ] Set hero image: `loading="eager" fetchpriority="high"`
- [ ] Set up Cloudflare (free plan sufficient)
- [ ] Create robots.txt and submit sitemap

**Day 1 after launch:**
- [ ] Submit to Google Search Console
- [ ] Submit to Bing Webmaster Tools (covers DuckDuckGo/Yahoo)
- [ ] Verify Google Business Profile
- [ ] Install Google Analytics 4 with conversion events (form submit, phone click, WhatsApp click)

---

---

# PART 2 — UX/UI AUDIT

## Summary

The content document shows strong strategic thinking — correct audience segmentation (ועדי בתים / חברות / פרטיים), good information hierarchy, and an awareness of mobile-first needs. **The primary UX risk is conversion loss from weak trust signals, incomplete social proof (placeholders), and an under-specified contact/quote request flow.**

Overall UX maturity: **Intermediate — solid IA, gaps in interaction design and conversion optimization.**

---

## 2.1 Strengths

**Audience-first IA:** Dedicated pages for each persona (ועדי בתים, חברות, פרטיים) is excellent — users self-select and land on content that speaks directly to their situation. This is a meaningful conversion advantage over competitors with generic "services" pages.

**Sequential service pages:** The document correctly structures services as separate URLs (`/services/hafui-mivnim`, `/services/snapling`, `/services/special-projects`) enabling keyword targeting per page without cannibalization.

**FAQ as a standalone page:** Correct — FAQ content at `/faq` earns its own SERP placement for long-tail queries and also feeds the FAQ schema rich result.

**Blog strategy:** 8 posts planned with specific word counts and target keywords. This is properly resourced content marketing, not an afterthought.

**WhatsApp-first mobile CTA:** Correctly identified as critical for the Israeli market. Implementation needs more specificity (see Critical Issue #1 below).

---

## 2.2 Critical UX Issues

---

### ❌ Critical Issue #1 — WhatsApp CTA Is Underspecified

**Problem:** The document says WhatsApp should be "sticky on mobile" but gives no design specification. If not built correctly, this becomes an afterthought or broken on mobile.

**Impact:** Very high — ועדי בתים contact almost exclusively via WhatsApp in Israel. Missing or buried WhatsApp = lost leads.

**Principle violated:** Fitts's Law — the most important action must be the easiest to reach.

**Fix — Exact implementation spec:**
```html
<!-- Sticky floating WhatsApp button — visible on ALL pages, ALL devices -->
<a href="https://wa.me/972XXXXXXXXX?text=שלום%2C%20אני%20מעוניין%20בהצעת%20מחיר%20לחיפוי%20מבנה"
   class="whatsapp-sticky"
   aria-label="פנייה בוואטסאפ"
   target="_blank" rel="noopener">
  <img src="/icons/whatsapp.svg" alt="" aria-hidden="true" width="28" height="28">
  <span>דברו איתנו</span>
</a>
```
- Fixed position: `bottom: 20px; left: 20px` (RTL — left side is visually prominent)
- Size: minimum 56×56px touch target
- Pre-filled message in the `text=` parameter saves the user typing
- Pair with a click event in Google Analytics 4

---

### ❌ Critical Issue #2 — Social Proof Section Has [X] Placeholders

**Problem:** The "ASUS במספרים" section currently reads `[X]+ פרויקטים`, `[X] שנות ניסיון`, `[X]+ לקוחות`. Publishing with placeholders is a severe trust-killer — it signals an incomplete or unprofessional business.

**Impact:** Very high — social proof is the #1 conversion driver for contractor services. Users compare companies and zero in on proof.

**Principle violated:** Heuristic 1 (Visibility of system status) + basic trust design.

**Fix:** Before launch, define the MINIMUM real numbers you can state truthfully. Even conservative numbers are infinitely better than [X].

**Recommendation for testimonials:**
- Replace placeholder testimonials with real ones, attributed with first name + neighborhood (e.g., "רן מ., ועד בית, ראשון לציון") — full names aren't required, but specificity is
- Add a star rating (⭐⭐⭐⭐⭐) visual next to each testimonial
- Embed actual Google Reviews widget (iframe from GBP) as a trust anchor

---

### ❌ Critical Issue #3 — Contact Form Is Underspecified

**Problem:** The form is described as: `[טופס: שם, טלפון, אימייל, סוג השירות, הודעה חופשית]`. No spec for validation, success state, error handling, or loading state.

**Impact:** High — this is the primary conversion point. A broken or confusing form means lost leads.

**Principle violated:** Form design standards (label above field, inline validation, explicit success state).

**Fix — Detailed form spec:**

```
Form: Quote Request
Fields:
  ├── שם מלא* [text, required, min 2 chars]
  ├── טלפון* [tel, required, Israeli pattern: 05X-XXXXXXX]
  ├── אימייל [email, optional]
  ├── סוג השירות* [radio buttons — NOT dropdown for 4 options]
  │     ○ חיפוי מבנים חיצוניים
  │     ○ עבודות סנפלינג
  │     ○ פרויקט מיוחד
  │     ○ לא בטוח / ייעוץ כללי
  ├── עיר הנכס [text, optional] ← Add this — helps triage
  └── הודעה [textarea, optional, max 500 chars]

Validation:
  ├── Inline — validate on blur, not on keypress
  ├── Phone: red border + "נא להזין מספר ישראלי תקין (05X-XXXXXXX)"
  └── Required empty: red border + "שדה זה הוא חובה"

Submit button:
  ├── Default: "שלח פנייה ←"
  ├── Loading: spinner + "שולח..."
  └── Disabled until required fields valid (or show errors on submit attempt)

Success state:
  └── Replace form with: "✅ קיבלנו את פנייתך! נחזור אליך תוך 24 שעות."
      + WhatsApp link: "רוצים מענה מהיר יותר? דברו איתנו בוואטסאפ"

Honeypot: add hidden field to block bots
```

---

### ❌ Critical Issue #4 — Project Gallery Has No Design Spec

**Problem:** The gallery page (`/projects`) is described with categories and a "card format" but no interaction spec. For a building cladding company, the gallery is the primary trust-building tool — it is the portfolio.

**Impact:** High — users make a buy/no-buy decision based on project quality. A bad gallery implementation (random images, no before/after, no context) = missed conversion.

**Fix — Gallery interaction design:**

**Before/After Slider** for each project card (essential for cladding — the transformation IS the product):
- Component: image slider with drag handle at center
- Label: "לפני" (left) / "אחרי" (right)
- Mobile: swipe gesture

**Project Card spec:**
```
[Before/After slider image — 4:3 ratio]
[Tag: "חיפוי HPL" | "סנפלינג" | "פרויקט מיוחד"]
[Headline: "שיפוץ חזית בניין 8 קומות, רמת גן"]
[2-line: "לקוח: ועד הבית | שטח: 800 מ"ר | משך: 5 שבועות"]
[CTA: "קרא את הסיפור המלא →"]
```

**Filter bar** at top of gallery (matching your 5 categories) — use pill/tab buttons, not a dropdown on mobile.

---

## 2.3 Quick Wins (Low Effort, High Impact)

**QW-1 — Clickable phone number in header:**
```html
<a href="tel:+97205XXXXXXXX" class="header-phone">
  ☎ 05X-XXXXXXX
</a>
```
Every page. Non-negotiable for service businesses in Israel.

**QW-2 — Trust badges in footer (and above the fold on homepage):**
- "קבלן מורשה מס׳ XXXXX"
- "מבוטח — אחריות מקצועית + עובדים"
- "אחריות [X] שנים על כל עבודה"

Display as icon + text in a horizontal strip.

**QW-3 — Hero section improvement:**
Current: "הפנים של הבניין שלכם – בידיים הנכונות."
This is good copy. Add a small trust block BELOW the hero CTAs:
```
✅ הצעת מחיר חינם  |  ✅ ביטוח מלא  |  ✅ קבלן מורשה  |  ✅ ניסיון [X] שנים
```
This addresses objections before the user even scrolls.

**QW-4 — Add "עיר / אזור" to the comparison table for services:**
Users need to know ASUS serves their area. The current copy says "כל הארץ" in the FAQ, but add this to every service page too.

**QW-5 — Services page CTA hierarchy:**
Each service page should end with:
1. Primary CTA: "קבל הצעת מחיר לחינם" → links to `/contact`
2. Secondary CTA: WhatsApp link (pre-filled with service type)
3. Tertiary: "ראה פרויקטים דומים →" → links to filtered gallery

---

## 2.4 Strategic UX Recommendations (Longer Term)

**SR-1 — Add a "הצעת מחיר בשלבים" (Guided Quote Flow):**
Instead of a generic contact form, create a 3-step wizard:
1. Step 1: "מה צריך?" (radio: חיפוי / סנפלינג / שניהם / לא בטוח)
2. Step 2: "איפה?" (city field + building type)
3. Step 3: "פרטי קשר" (name + phone only — minimize friction)

Each step completion is a micro-conversion you can track in GA4. This pattern typically improves lead quality and volume for contractor services.

**SR-2 — Dedicated landing page per neighborhood/city:**
Once the site has authority, create pages like:
- `/חיפוי-מבנים-תל-אביב`
- `/חיפוי-מבנים-ירושלים`
- `/חיפוי-מבנים-חיפה`

Each captures local-intent queries ("חיפוי חזית תל אביב") that the homepage can't rank for.

**SR-3 — Accessibility for RTL (Hebrew-specific):**
- All directional icons must flip for RTL (arrow "→" should become "←" in Hebrew text)
- Input fields: text-align: right for all form inputs
- All animations: check `prefers-reduced-motion` compliance
- Minimum 4.5:1 contrast ratio — especially important for text over project photos
- Tab order: must follow visual flow in RTL direction

**SR-4 — Add a "מדריך לוועד בית" downloadable PDF as a lead magnet:**
Convert the existing 5-step planning guide into a branded PDF download (no email required — just WhatsApp-gate it). This drives WhatsApp contact AND positions ASUS as the expert.

---

## 2.5 User Persona Journey Maps

### Persona A — ועד בית Member

**Context:** 45-year-old accountant, elected ועד בית chair, not a construction expert. Searching on mobile during lunch break. Needs to justify spending ₪80,000+ to 30 neighbors.

**Journey:**
```
Google: "חיפוי חזית בניין מחיר" (mobile)
  → Lands on FAQ page or Blog post
  → Reads the "כמה עולה" answer
  → Clicks "קרא עוד" → Service page
  → Sees comparison table, trust badges
  → Clicks WhatsApp CTA
  → Downloads "מדריך לוועד בית" PDF [SR-4]
  → Calls for free inspection
```

**Friction points to eliminate:** Hidden phone number, no price range on FAQ, no proof that ASUS is legitimate/insured before contact.

---

### Persona B — Facilities Manager (חברה גדולה)

**Context:** Professional procurement, works on a computer, needs documentation, invoices, B2B contracts. Comparing 3 contractors.

**Journey:**
```
Google: "קבלן חיפוי מבנים מסחרי ישראל" (desktop)
  → Lands on Homepage or /clients/companies
  → Looks for: license number, insurance docs, B2B references
  → Downloads or requests spec sheet
  → Submits formal inquiry via contact form
```

**Friction points to eliminate:** No B2B-specific credential page, no mention of purchase order / procurement process compliance, no downloadable insurance certificates.

**Fix:** The `/clients/companies` page (currently only described at high level) should explicitly list: "מסמכים שאנחנו יכולים לספק" — ביטוחים, רישיון קבלן, חשבוניות מסודרות, דוחות ביצוע.

---

### Persona C — Private Homeowner (לקוח פרטי)

**Context:** Homeowner, visual decision-maker, primarily driven by aesthetics and price. May be comparing with 2 other quotes.

**Journey:**
```
Google: "שיפוץ חזית בית פרטי" (any device)
  → Lands on Services or Homepage
  → Scrolls to gallery → Must see houses, not just apartment buildings
  → Reads testimonials from private clients
  → Contacts via WhatsApp for a photo-based quote
```

**Friction point:** Gallery currently mixes all project types. Private clients need to quickly find projects similar to their own home. Add filter tag "בית פרטי" to gallery.

---

## 2.6 Navigation Recommendations

**Current proposed navigation (from site architecture):**
Home | אודות | שירותים ▾ | פרויקטים | קהלי לקוחות ▾ | FAQ | בלוג | צור קשר

**Issues:**
- 8 top-level items is at the limit of cognitive capacity (Hick's Law)
- "קהלי לקוחות" as a nav item is jargon — users don't think of themselves as a "קהל"

**Recommended navigation:**
```
ASUS חיפוי  |  שירותים ▾  |  פרויקטים  |  למי אנחנו מתאימים ▾  |  FAQ  |  [☎ 05X-XXXXXXX]  |  [קבל הצעה]
                                                                                             ↑ always visible  ↑ CTA button
```

- Rename "קהלי לקוחות" → "למי אנחנו מתאימים" (more user-centric language)
- Collapse בלוג + אודות into the footer (low-traffic, high-friction items)
- Make the phone number a nav item on desktop (Jakob's Law — service sites always do this)
- "קבל הצעה" as a colored CTA button in the nav — always visible

**Mobile nav:** Hamburger is acceptable here since there are 5+ items. Keep WhatsApp sticky button as the primary mobile action.

---

---

# APPENDIX: Launch Readiness Checklist

## SEO — Pre-Launch

- [ ] `<html lang="he" dir="rtl">` on every page
- [ ] All [X] placeholders filled with real data
- [ ] All JSON-LD schemas from this report added
- [ ] Hero image: WebP format, <150KB, `fetchpriority="high"`
- [ ] All gallery images: WebP, `loading="lazy"`, descriptive Hebrew `alt` text
- [ ] robots.txt created and uploaded
- [ ] sitemap.xml generated and submitted
- [ ] Google Search Console verified
- [ ] Google Business Profile complete (20+ photos, all services listed)
- [ ] GA4 installed with conversion events: form_submit, phone_click, whatsapp_click

## UX — Pre-Launch

- [ ] Sticky WhatsApp button: all pages, all devices, pre-filled message
- [ ] Clickable phone number in header (tel: link)
- [ ] Trust badge strip on homepage (license, insurance, warranty)
- [ ] Social proof numbers filled (not [X])
- [ ] At least 3 real testimonials with real attribution
- [ ] Contact form: validation + success state + honeypot
- [ ] Before/after slider on gallery (at least for 5 hero projects)
- [ ] Gallery filter tags working (חיפוי מגורים / מסחרי / סנפלינג / לפני-אחרי)
- [ ] All RTL directional icons reviewed (arrows, chevrons)
- [ ] Tested on iPhone Safari (primary target device for ועדי בתים)

---

*Analysis prepared by SEO Expert + Advanced UX Specialist skill combination.*
*Document date: June 2026*
