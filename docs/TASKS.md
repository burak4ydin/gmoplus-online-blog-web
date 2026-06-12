# Task Backlog — gmoplus-online-blog-web

## P0 — Critical
- (none)

## P1 — High
- [ ] Wrong domain in .env.example — copy-pasted from another vertical, references incorrect domain. Fix: set to https://online.gmoplus.com and correct CMS API URL
- [ ] Redundancy with inline blog in online-web — same domain, two repos serving blog content. Decide canonical source and disable or redirect the other

## P2 — Medium
- [ ] Newsletter CTA has no backend endpoint
- [ ] No sitemap.xml for food/restaurant blog posts
- [ ] No robots.txt
- [ ] Search fires on every keystroke without debounce

## P3 — Low
- [ ] vertical-config.ts identity hardcoded — should be env-driven
- [ ] No JSON-LD Article schema on post pages
- [ ] No canonical tags to resolve duplicate content between locales
- [ ] Missing pagination on category/tag archive pages