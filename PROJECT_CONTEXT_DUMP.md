# RSS Feature Superset (Nonredundant, All-Inclusive)

Date: 2026-02-14  
Purpose: Canonical superset feature list across major RSS/reader platforms, deduplicated for planning.

## Coverage assessment

This file provides an implementation-grade canonical checklist by combining:
- nonredundant taxonomy,
- explicit lifecycle status (`available now` / `plan-gated` / `historical`),
- per-feature source attribution.

Status key:
- **Available now**: capability is available in at least one mainstream product today.
- **Plan-gated**: capability generally appears as paid-tier, enterprise, or limited rollout.
- **Historical**: capability existed in products/APIs historically and may be discontinued or legacy.

## Canonical nonredundant superset (with lifecycle + source attribution)

| # | Capability area | Canonical feature | Lifecycle status | Source attribution |
|---|---|---|---|---|
| 1 | Intake formats and discovery | RSS/Atom/JSON Feed, add by URL, autodiscovery, OPML import, programmatic subscription endpoints | Available now | FreshRSS docs (OPML), Feedly/Inoreader/NewsBlur/Miniflux docs and product pages |
| 2 | Non-RSS intake | Web-page extraction (XPath/CSS/JSON), web change tracking, newsletter inbox aliases, saved pages | Plan-gated | FreshRSS OPML/XPath/JSON docs, Inoreader newsletter & web monitoring pages, Readwise Reader docs |
| 3 | Social and media intake | YouTube/podcast and platform-dependent social feeds, protected/auth feeds (Basic/Digest/custom) | Available now | Product pages and API docs (Inoreader, NewsBlur, BazQux, FreshRSS) |
| 4 | Fetch/update engine | Refresh cadence, priority polling, WebSub/push, retries/backoff, per-host concurrency controls | Available now | FreshRSS WebSub + feed update docs, other product feature docs |
| 5 | Update intelligence | Changed-article detection, diffs, infrequent-site views, archive-depth controls | Plan-gated | Feedly docs, NewsBlur blog updates, product changelogs |
| 6 | Parsing and normalization | Full-text extraction, readability fallback, per-site scraper rules, enclosure/media parsing, canonical URL cleanup | Available now | FreshRSS and competitor docs (Inoreader, TT-RSS, Readwise) |
| 7 | Noise reduction | Duplicate suppression (URL/content/semantic variants), mute/exclude filters, regex/rule classifiers | Available now | Feedly dedup docs, NewsBlur intelligence controls, TT-RSS/FreshRSS filtering docs |
| 8 | Organization model | Folders/subfolders, labels/tags, smart streams, saved searches, stars/read-later queues | Available now | FreshRSS, Inoreader, Feedly, NewsBlur, Miniflux docs |
| 9 | Knowledge artifacts | Highlights, notes/annotations, searchable saved items, key-term surfacing | Plan-gated | Readwise docs, Feedly AI docs, premium product pages |
| 10 | Reading UX | List/magazine/grid/split layouts, reader-vs-original mode, per-feed preferences, next-unread traversal, hide-read | Available now | FreshRSS + mobile client docs (NetNewsWire, Reeder, RSS Guard) |
| 11 | Personalization/accessibility | Themes, typography, custom CSS/JS hooks, keyboard workflows, RTL/localization, responsive behavior | Available now | FreshRSS, Nextcloud News customization/theme docs |
| 12 | Media experience | In-reader playback, resume, background audio, TTS | Plan-gated | Product pages for Inoreader/Feedly/mobile apps |
| 13 | Search and query layer | Full-text search, operators/query syntax, saved queries, date filters, global search | Available now | Feedly search API docs, FreshRSS/NewsBlur docs |
| 14 | Rules and automation | If/then rules, auto-tag/read/notify/webhook actions, rule simulation, automation logs/match counters | Plan-gated | Inoreader automation docs, enterprise plan pages, product docs |
| 15 | AI layer | Summaries, key-sentence extraction, ask-AI item/collection, entity tracking, auto-briefings, extraction pipelines | Plan-gated | Feedly/NewsBlur AI announcements, commercial plan docs |
| 16 | Collaboration and publishing | Shared folders/boards, role-based collaboration, comments/mentions, scheduled digests, public/private sharing | Plan-gated | Feedly boards docs, The Old Reader and Inoreader collaboration pages |
| 17 | External delivery | Slack/Teams/webhook pushes, Zapier/IFTTT rails, private/public RSS outputs | Available now | Inoreader integrations/dev pages, Nextcloud integrations docs |
| 18 | API and ecosystem | REST APIs, OAuth/token auth, rate limits, Google Reader-compatible APIs, Fever-compatible APIs | Available now | FreshRSS Google Reader/Fever docs, Nextcloud News API, NewsBlur API |
| 19 | Sync and portability | Multi-device sync, read/unread and stars/tags sync, OPML export, migration helpers | Available now | FreshRSS + major product import/export pages |
| 20 | Ownership/privacy/security/ops | Self-hosting, multi-user tenancy, tracker stripping/de-tracking, media proxy/referrer hardening, Docker/cron/CLI ops, extension architectures | Available now | FreshRSS admin docs, self-hosted reader docs (TT-RSS, Nextcloud News, CommaFeed) |

## FreshRSS-specific must-retain capabilities

1. WebSub push support.
2. Extended OPML plus XPath/JSON-based non-RSS ingestion options.
3. Google Reader plus Fever API compatibility.
4. Extension architecture (user/system extensions).
5. OIDC support path and strong self-host operations model.


## Where we are now (FreshRSS against the superset)

**Solidly covered in FreshRSS today**
- Core intake and discovery (RSS/Atom, OPML import, feed autodiscovery patterns through standard URL onboarding).
- Push and compatibility surfaces (WebSub, Google Reader API, Fever API).
- Self-host operations posture (extensions, multi-user model, Docker/CLI-oriented administration).

**Partially covered or ecosystem-dependent**
- Non-RSS extraction depth and rule sophistication vary by extension/workflow.
- Collaboration and outbound automation are possible but less productized than SaaS readers.
- Advanced media workflows (resume/background playback/TTS) are mostly client-dependent.

**Common competitive gaps vs top commercial suites**
- Native AI workflows (summaries, ask-on-collection, entity tracking, automated briefings).
- Rich rule observability (simulation, per-rule counters/log timeline, auditability UX).
- First-class team collaboration (roles, comments/mentions, digest workflows).

## What is next (recommended execution order)

1. **Convert this superset into a scored capability matrix for FreshRSS** (Now / Partial / Missing, with links to code/docs per row).
2. **Create a prioritized roadmap shortlist** using impact × complexity (top 5 gaps only, each with acceptance criteria).
3. **Define ownership boundaries**: core platform vs extension ecosystem vs external clients.
4. **Add evidence granularity** by attaching one verifiable source per row (local doc path or external URL + date checked).
5. **Track delivery** in milestones (e.g., `M1: ingestion+automation`, `M2: collaboration`, `M3: AI-assist`) and review quarterly.

## Sources checked

### Local references
- `PROJECT_CONTEXT_DUMP.md` (this canonical superset)
- `docs/en/users/WebSub.md` (WebSub)
- `docs/en/developers/OPML.md` (OPML and extended import)
- `docs/en/developers/06_GoogleReader_API.md` (Google Reader-compatible API)
- `docs/en/developers/06_Fever_API.md` (Fever API)
- `docs/en/admins/15_extensions.md` (extensions)
- `docs/en/admins/16_OpenID-Connect.md` (OIDC)
- `docs/en/admins/08_FeedUpdates.md` (feed updates/operations)

### External references
- https://freshrss.github.io/FreshRSS/en/
- https://freshrss.github.io/FreshRSS/en/users/WebSub.html
- https://freshrss.github.io/FreshRSS/en/developers/OPML.html
- https://freshrss.github.io/FreshRSS/en/developers/06_GoogleReader_API.html
- https://freshrss.github.io/FreshRSS/en/developers/06_Fever_API.html
- https://freshrss.github.io/FreshRSS/en/admins/15_extensions.html
- https://freshrss.github.io/FreshRSS/en/admins/16_OpenID-Connect.html
- https://freshrss.github.io/FreshRSS/en/admins/08_FeedUpdates.html
- https://www.inoreader.com/
- https://www.inoreader.com/pricing/feature/newsletters
- https://www.inoreader.com/developers
- https://www.newsblur.com/
- https://www.newsblur.com/api
- https://blog.newsblur.com/2026/01/22/intelligence-trainer-overhaul/
- https://feedbin.com/
- https://beta.bazqux.com/
- https://bazqux.com/faq
- https://www.theoldreader.com/en/tour/
- https://www.theoldreader.com/en/apps/
- https://theoldreader.com/users/sign_up
- https://miniflux.app/features.html
- https://tt-rss.org/docs/Features.html
- https://github.com/Athou/commafeed
- https://github.com/nextcloud/news
- https://nextcloud.github.io/news/api/api-v2/
- https://nextcloud.github.io/news/features/integration/
- https://nextcloud.github.io/news/features/plugins/
- https://nextcloud.github.io/news/features/customCSS/
- https://nextcloud.github.io/news/features/themes/
- https://netnewswire.com/help/ios/6.1/en/
- https://reederapp.com/
- https://docs.readwise.io/reader/docs
- https://github.com/martinrotter/rssguard
- https://docs.feedly.com/article/218-how-does-deduplication-work
- https://docs.feedly.com/article/61-how-can-i-share-a-board
- https://developers.feedly.com/docs/using-the-search-api
