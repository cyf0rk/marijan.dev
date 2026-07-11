---
title: "Clipster: From MVP on a Single Server to 100 Billion Views"
date: 2026-07-06
summary: "Backend rewrite from a single-server Svelte MVP to Go + GCP + PostgreSQL - creator payouts, OAuth RFCs, and scale."
---
## The Situation

Clipster (clipster.gg) is a platform for clippers — creators who cut short-form highlights and distribute them across social media. The community existed before the product did, built around Discord, which meant there was a real market waiting when the platform launched. When I joined, the MVP had been built by two junior developers and a founder: a Svelte frontend, app and database both running on a single Hetzner server, and a codebase that had grown fast without much structure. Performance was slow, security was thin, and the architecture wasn't built to scale. The platform was also processing real creator payouts — normal payments and crypto — which meant backend reliability wasn't optional.

## What We Built

The end state was a full backend rewrite: Go, GCP, PostgreSQL. That replaced the original Svelte MVP running on Hetzner hardware.

**Team delivery:**
- Go REST API replacing the original backend
- GCP infrastructure — Cloud Run, Cloud SQL, and supporting services
- PostgreSQL as the primary database, replacing the original single-server setup
- Creator payout infrastructure handling both standard payments and crypto

**My specific contributions:**
- Performance debugging and fixes on the old Svelte/Hetzner MVP during the maintenance phase — buying the team time before the rewrite
- OAuth integration RFC and implementation: Google, Discord, and Apple sign-in, added alongside the existing auth system
- System design RFCs — responsible for authoring design documents for backend features before implementation

## How We Did It

**Phase 1: Maintenance (months 1–2).** I joined to work on backend and spent the first stretch on the existing MVP. Fixed performance bottlenecks that made the app noticeably faster, patched security issues, and stabilized enough to give the rewrite time to happen properly. No heroics — just getting a fragile system to a point where it wasn't actively breaking.

**Phase 2 was the architecture decision.** An AWS setup had been built out by a DevOps team before I got involved. It was overengineered for where the product actually was — it made sense at a different scale, but burned money earlier than it should have. A technical consultant from Mobalytics came in with deep GCP and cloud architecture experience. In a few weeks he helped us get organized, evaluate the options, and align on GCP — a decision that made sense given team knowledge and cost profile. He handled most of the cloud architecture work.

**Phase 3, the Go rewrite:** An engineering manager joined and became the backbone of the rewrite. We did a lot of pair programming. Watching someone approach a problem differently, again and again, changed how I think about writing code. The new Go backend was built out over several months: clean architecture, proper separation of concerns, a codebase that could actually be reviewed and extended.

**Phase 4 brought the team to scale.** Two more engineers joined as the rewrite progressed. The team introduced a real code review culture and a system design process. I was responsible for writing RFCs — design documents that defined how features should work before anyone wrote code. The OAuth system (Google, Discord, Apple) was one of those: I authored the RFC, got it reviewed, and implemented it.

## Results

- **100 billion+ views** generated across social media platforms by Clipster creators
- **$2M+ paid out** to creators through standard payments and crypto
- Architecture moved from a single Hetzner server running Svelte to Go + GCP + PostgreSQL — a stack that could support the scale the platform reached

## Why It Matters for Creator Economy Founders

Most creator platforms start the same way Clipster did: a community that already exists, a founder who builds fast to capture it, and junior developers who ship an MVP under pressure. That's not a failure. It's how you validate a market. The failure is staying in that mode after the market is validated.

What Clipster got right was knowing when to rebuild and bringing in the right people to do it. A technical consultant from Mobalytics helped correct an infrastructure direction that would've cost more to maintain than to change. An experienced engineering manager raised the quality bar on the backend through direct collaboration, not just code review. The result was a platform that could handle the load of a creator economy at real scale.

That's the shape of the Clipster engagement: not fixing a mistake, but recognizing the moment an MVP has done its job and needs to become infrastructure.
