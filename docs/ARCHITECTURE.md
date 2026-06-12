# Architecture — gmoplus-online-blog-web

## Stack
- Framework: Next.js (App Router)
- Language: TypeScript
- i18n: next-intl ([locale] prefix routing)
- Styling: Tailwind CSS + tailwind-merge + clsx
- Content safety: isomorphic-dompurify
- No auth, no state management library

## Folder Structure
```
src/
  app/
    [locale]/
      page.tsx              — Blog index
      [slug]/page.tsx       — Post detail
      category/[slug]/      — Category filtered posts
      author/[slug]/        — Author profile + posts
      tag/[slug]/           — Tag filtered posts
      search/page.tsx       — Search results
      kategoriler/          — Category list
  components/
    blog/                   — PostCard, FeaturedPost, PostContent,
                              PostHeader, RelatedPosts, TagList,
                              ShareButtons, SidebarSearch,
                              NewsletterCTA, ReadingProgress
    layout/                 — BlogHeader, BlogFooter, BlogSidebar,
                              LanguageSwitcher
  lib/
    api.ts                  — CMS fetch helpers
    seo.ts                  — OG/Twitter metadata helpers
    translations.ts         — i18n message loader
    vertical-config.ts      — Blog identity (online-specific branding)
  i18n/                     — next-intl config
  middleware.ts             — Locale detection
  types/blog.ts             — Post, Category, Author, Tag types
```

## Data Flow
Server component → lib/api.ts → CMS endpoint → sanitize HTML → render

All pages use generateMetadata() for per-post SEO. No client-side data fetching.

## Notes
- Redundancy risk: online-web embeds inline blog at /blog. This standalone blog app and the inline blog may serve the same domain. Canonical URLs must be consistent.
- Identical component structure to store-blog-web and booking-blog-web (shared pattern across all verticals).