---
title: "Shopify's March 2026 Dev Platform Update: What Actually Matters"
date: 2026-03-25
summary: "RBAC in the Dev Dashboard, a faster Admin API, and safer CLI deploys - the highlights worth knowing."
tags: ["shopify", "ecommerce"]
---

Shopify just dropped their March 2026 Dev Platform update, and there's a lot to like. A few highlights:

- **Role-based access control in the Dev Dashboard** - finally, proper team permissions for partner orgs.
- **Faster Admin API** - they've moved to breadth-first GraphQL execution, which means noticeably quicker responses on large list queries.
- **Safer CLI deploys** - the old `--force` flag is being replaced with `--allow-updates` and `--allow-deletes`, so no more accidental extension deletions.
- **Bundle size analysis for UI extensions** - you can now see exactly what's eating into that 64 KB limit.
- **387 refreshed reference docs** for Admin UI extensions and App Home.
