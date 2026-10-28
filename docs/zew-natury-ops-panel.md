# Zew Natury - Ops Panel

Application details for Allegro administrators.

**User-Agent:** `Zew Natury - Ops Panel/1.0.0 (+https://github.com/stosola/zew-natury-ops-panel/blob/main/docs/zew-natury-ops-panel.md)`

**Owner:** Zew Natury, an online shop selling dog and cat food. Allegro account: zew-natury.

**Contact:** stodulskimikolaj@gmail.com

## What it is

An internal dashboard run on a single company computer. It is separate from our other Allegro app, "Zew Natury Dashboard", which is used by another internal tool. Each tool has its own app registration and its own tokens.

## Scopes and what we use them for

All scopes are read-only.

| Scope | Used for |
|---|---|
| `allegro:api:sale:offers:read` | offer list with views, watchers, price, stock; product ratings per offer |
| `allegro:api:sale:settings:read` | sales quality score and seller settings |
| `allegro:api:orders:read` | order status, to spot orders that are late or stuck |
| `allegro:api:ratings` | reading seller ratings and buyer comments (no replies or changes) |
| `allegro:api:billing:read` | Allegro fees: commission, delivery, ads, subscription |
| `allegro:api:payments:read` | payment and refund history, to match payments with orders |
| `allegro:api:profile:read` | basic account details, to confirm the connected account |
| `allegro:api:fulfillment:read` | stock and advance notices in One Fulfillment |
| `allegro:api:shipments:read` | shipment and tracking status |
| `allegro:api:affiliate:read` | results of affiliate programs |

## How it works

- Authorization through OAuth 2.0 Device Flow, so no Allegro logins or passwords are stored.
- Only GET requests (without a request body) plus the token refresh. Nothing is created or modified on the account.
- Data is fetched at most once an hour; ratings once a day. Requests are sent one at a time; on 429 or 5xx the app waits and retries.
- History is kept locally, so each run only asks for recent data.
- The User-Agent above is sent with every request, including the token refresh.

## Data and security

- Client secret and tokens are kept only on the company computer, outside of any repository.
- The dashboard runs locally (localhost), is password protected and is not reachable from the internet.
- Data from the API is used only inside our company. We do not share or sell it.
