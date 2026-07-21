# CleverTap Webhooks Gallery, Field Guide No.15

The outbound channel. CleverTap talking to the client's own stack, server to server, the moment something happens. Ninety integration recipes across fifteen verticals, real payload shapes, receiver snippets, the reliability and security model, an External Trigger section, and an honest build-vs-buy guide.

Live at: https://shijunneo-bot.github.io/ct-webhooks-gallery/

## Deploy to GitHub Pages

1. Create a repo named `ct-webhooks-gallery` under the `shijunneo-bot` account.
2. Put every file from this bundle in the repository root (not in a subfolder).
3. In Settings, Pages, set the source to the `main` branch, root folder.
4. Wait for the build, then open https://shijunneo-bot.github.io/ct-webhooks-gallery/

The favicon rides inline inside `index.html`, so it needs no separate file.

## Bundle contents

| File | What it is |
| --- | --- |
| `index.html` | The full gallery and guide. Self-contained: all CSS and JS inline, no CDN except Google Fonts. |
| `og-image.png` | The 1200x630 social share card. |
| `robots.txt` | Allows all crawlers and explicitly welcomes AI answer engines. Points to the sitemap. |
| `llms.txt` | The machine-readable summary answer engines read and cite: definition, facts, patterns, all 90 recipes, caveats. |
| `sitemap.xml` | Single-URL sitemap for search engines. |
| `README.md` | This file. |

## Grounded vs illustrative

Product mechanics (the four flavors, the payload shape, the reliability model, stats, External Trigger, DND behavior) are grounded in CleverTap documentation and the CleverTap developer docs. Everything customer-facing in the recipe gallery is invented: every brand, every endpoint, and every metric. Endpoints use `api.<brand>.example` hosts. Metrics are labeled illustrative.

## Verify with PM

A few facts move between docs, plans, and SDK or API versions. Confirm the current state before you commit a client:

- Retry and timeout figures. The published FAQ says a 5-second timeout with a retry limit of 2. Internal CS guidance has cited 3 retries at about 3-second intervals. Design for the pessimistic case.
- The exact set of webhook flavors and the signing or HMAC scheme for verification.
- External Trigger availability. It is Public Beta and needs CSM enablement.
- Macro namespaces (Profile, Event, System, ExternalTrigger) for your account and region.

## Notes

- Non-native regional messengers (KakaoTalk, Zalo, Viber, WeChat) have no native CleverTap channel. They are reachable with a generic webhook or a provider, so scope them as custom builds.
- DND (Do Not Disturb) for webhooks works in Campaigns, not in Journeys.

Built by SJ Neo, Enterprise CSM. No affiliation implied.
