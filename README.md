# Bicep Heart

One photo in, one short video out. [bicepheart.site](https://bicepheart.site) recreates the "Bicep Heart" short-form clip with the person from your photo as the performer - same pose, same timing, same camera framing, no filming needed.

## What it does

- Upload one JPEG / PNG / WEBP photo of a person (up to 10 MB)
- Get a vertical 9:16 MP4, about 7 seconds, ready to post
- Credits are one-time purchases and never expire; failed renders are refunded automatically
- Google sign-in, English and Chinese UI

## Stack

| Layer | Choice |
| --- | --- |
| Runtime | Cloudflare Workers, TanStack Start SSR |
| Data | D1 (orders, users, credits), R2 (uploads, generated videos) |
| Async | Queues with a dead-letter queue, 5-minute cron |
| Video | Kling via APIMart (~$0.40 per render) |
| Payments | Dodo Payments as merchant of record, Standard Webhooks signatures |
| Analytics | Plausible + first-party AI-source attribution |

## Discovery work

Per-locale canonical and hreflang tags, a 34-URL sitemap, llms.txt, Organization / WebSite / SoftwareApplication + AggregateOffer / FAQPage structured data, explicit robots.txt allow-rules for 10 AI crawlers, and IndexNow submission to Bing and Yandex.

## Numbers after week one

Google Search Console (through 2026-11-10): 414 impressions, 8 clicks, average position 8.2, 34 pages indexed. Most impressions come from "what is the bicep heart trend" style queries - useful for discovery, weak for conversion. Distribution and backlinks are the remaining work.

## Notes

- Only people photos work: the motion-control model rejects animal photos.
- Generated videos carry an AI provenance marker verifiable at /verify.
- This repository is a project log; the application source is private.

Links: [Live site](https://bicepheart.site) · [Pricing](https://bicepheart.site/pricing) · [Guides](https://bicepheart.site/guides)
