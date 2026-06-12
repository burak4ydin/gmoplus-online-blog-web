# gmoplus-online-blog-web

## What It Does
Standalone Next.js blog for the GMOPlus food ordering vertical. Serves SEO content about food, recipes, restaurant guides, and delivery tips. Identical component structure to other vertical blog apps (store, booking, academy). Content from shared CMS.

## Who Uses It
- Food enthusiasts: organic search traffic on food and restaurant topics
- Online platform users: navigated from online-web /haberler links

## Key Features
- Multilingual articles (next-intl, [locale] routing)
- Post listing with featured post
- Category, tag, and author pages
- Full-text search
- Reading progress indicator
- Newsletter CTA
- Social share buttons
- HTML sanitization via isomorphic-dompurify
- Dynamic SEO metadata per post

## Business Flow
1. Admin publishes food/restaurant article in CMS
2. Blog fetches and renders server-side
3. Reader arrives from search engine or online-web link
4. Engages with content, follows links to online.gmoplus.com

## Success Criteria
- All posts indexed with correct canonical URLs and locale
- Content renders without XSS risk from CMS HTML
- No 404s on locale switching