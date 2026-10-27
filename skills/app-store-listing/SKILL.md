---
name: app-store-listing
description: Use when preparing or updating a Google Play or Apple App Store listing - app name or title, subtitle, short and long description, screenshot script, keywords per language and release notes. Keeps the listing consistent with the product context and with what the app declares in the Play data safety section and Apple privacy labels.
---

# App store listing

A store listing is a landing page with strict limits and a reviewer who checks it against the app. Write it from the product context, fit each field to the store's limits, and make sure every promise matches what the app does and declares about data.

## Inputs

- `.agents/product-context.md` and `.agents/voice.md` if they exist.
- The app itself or its spec: the features that are live today, not the roadmap.
- The data the app collects and shares (SDKs, analytics, accounts, permissions), from the code, the privacy policy and the current data safety or privacy label answers.
- Target languages and countries.

## Fields

Check current limits in the store's official documentation before writing; they change. At the time of writing:

| Store | Field | Notes |
|---|---|---|
| Google Play | App name (30), short description (80), full description (4000) | Play indexes the description text; no keyword field |
| App Store | Name (30), subtitle (30), keywords (100, comma-separated, not shown), promotional text (170), description (4000) | The description is not indexed; keywords and name are |
| Both | Screenshots, feature graphic or preview video, release notes | The first two or three screenshots carry most of the weight |

## How to write it

1. **Name and subtitle/short description:** brand plus the main job or result in the customer's words. No "best", "#1", "free" (unless always free) or emoji stuffing.
2. **Keywords per language:** list the queries the audience uses in each language, from customer language and search suggestions in the store. Do not translate keywords word for word; research each language. Do not repeat words already in the name (App Store). Never use competitor brand names.
3. **Description:** first lines answer what the app does and for whom; then main features as outcomes; then proof that is approved in product-context; then pricing model and requirements, stated honestly (subscriptions, in-app purchases, account needed).
4. **Screenshot script:** for each screenshot, the screen to capture, the one-line caption and the message it carries, in order. Use real screens of the current build; mockup frames are fine, invented features are not.
5. **Release notes:** what changed for the user, in plain words.

## Data safety and privacy consistency

Compare the listing and the app against the data declarations:

- Every data type the app collects or shares (including through SDKs like analytics, crash reporting, ads, login) appears in the Play data safety form and the App Store privacy label.
- The listing does not claim "no data collected", "private" or "secure" beyond what the declarations and the privacy policy support.
- Account deletion, if the app has accounts, is described where the stores require it.
- The privacy policy URL works and matches the declarations. For a deeper review, use `legal-pages-check`.

List every mismatch; the owner fixes the declarations or the copy, never the reviewer's perception.

## Rules

- Describe only live features. "Coming soon" stays out of the store fields.
- No invented ratings, download counts, awards, press quotes or testimonials.
- Do not submit, publish or change anything in Play Console or App Store Connect. Deliver the texts and the checklist.

## Output

Per store and language: each field with its character count against the limit, the keyword list, the screenshot script, and the data safety mismatches to resolve.

## Known failures

_Record real mistakes here with a date and the rule that prevents them._
