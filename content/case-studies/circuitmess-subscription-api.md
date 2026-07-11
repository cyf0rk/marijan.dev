---
title: "CircuitMess Subscription API: Killing Duplicate Shipments with a Centralized Order Brain"
date: 2026-07-06
summary: Greenfield Node.js + GCP + MySQL subscription API that ended 100+ duplicate shipments for a Forbes-featured STEM toy company.
---
## The Situation

CircuitMess makes DIY electronics kits and STEM toys for kids and makers. Featured in Forbes, BBC, TechCrunch, Mashable, Wired, and The Verge, CircuitMess had built real public profile before the backend caught up. When the API was first built, the catalog was their own products. By the time the engagement ended, they had added officially licensed products from NASA, LEGO, Rimac, and Adult Swim (Rick and Morty) — brand partnerships that raised the stakes on every order that shipped wrong.

The infrastructure behind those shipments wasn't keeping up even before the brand deals. Recharge handled subscriptions, order tags signaled what to ship, and a Mechanic app ran Shopify scripts to interpret it all. No single source of truth. No database of record. Just a fragile chain of tags and scripts where a misfire meant real boxes shipped twice. That cost money, burned logistics hours, and eroded team trust. As the business grew and changed, the backend had to grow with it. The duplicate problem wasn't a bug. It was structural, and it had to hold together through significant business change.

## What We Built

A centralized subscription management API that sits between Shopify, Recharge, and the fulfillment workflow — owning all subscription state in one place.

**Stack:**
- **Node.js REST API**, the core service handling all subscription business logic
- **GCP Cloud Functions + Pub/Sub** to ingest Shopify webhooks and decouple event processing from API load
- **PostgreSQL** as the single database of record for subscription state, order history, and what shipped to whom
- **Python processor**, a post-Pub/Sub script that queries the Recharge API to validate subscription data before any fulfillment decision
- **Shopify Admin API** for reading and writing order/subscription state as the source of commerce truth

Every fulfillment decision now runs through the database. If it isn't in Postgres, it doesn't ship.

## How We Did It

Solo architecture and build over ~3 months. No existing codebase to extend — this was greenfield: database schema design, API layer, GCP infrastructure, webhook pipeline, and Recharge integration all from scratch. It was also the first production-grade API I built independently, which meant learning cloud architecture, database design, application security, and the full Shopify API surface while shipping real code to a real client.

That learning curve showed up in the work. GCP Pub/Sub was chosen specifically to buffer Shopify webhook volume and prevent race conditions in order processing — an architecture decision that required understanding both the problem and the tooling simultaneously. The Python layer was kept separate from the Node API to isolate Recharge API concerns and make both easier to debug independently.

The hardest part wasn't the tech stack. It was the subscription spaghetti. CircuitMess had accumulated multiple subscription iterations without a unified model, which meant the API had to handle edge cases that weren't planned for upfront. That required ongoing schema adjustments and logic rewrites mid-build — real-world complexity that's invisible in a spec doc and can't be shortcut.

## Results

Before the API, duplicate shipments were a recurring cost — over 100 products sent out incorrectly, each worth $10–50 to make. That's real money lost before you factor in logistics, customer support, and team time spent figuring out what went wrong.

After: occasional edge cases — a Python script logic bug, a manual Recharge edit, an edge case from a subscription iteration change — but contained and traceable. The logistics team went from firefighting invisible errors to having a queryable database. "What did this subscription actually receive?" became a five-second query instead of a Slack thread. When something goes wrong now, you find it before the box ships.

CircuitMess has since stopped selling new subscriptions, but the existing subscriber commitments still had to be honored — 2-year pre-paid obligations that couldn't just disappear. The system was designed to handle that backlog without the original developer in the loop. That was the real constraint: build something reliable enough to outlast the engagement.

## Why It Matters for E-Commerce Subscription Brands

Recharge plus workarounds plus scripts plus tags is a common setup for a growing subscription brand, and it works right up until someone new joins the team and has to learn the invisible rules by trial and error. Every edge case becomes a potential duplicate, and a new plan or region layered on top of that stack is a coin flip.

What fixed it here wasn't cleverness, it was ownership: one database that every fulfillment decision has to pass through, with auditable state, predictable behavior, and room to change the logic without breaking everything downstream. Any brand that has outgrown its subscription tooling but hasn't yet taken ownership of its own order data is looking at the same fix.
