---
title: "Own Your Corner of the Internet: A Developer's Guide to Permanent Online Presence"
date: 2026-07-06
summary: "I spent a decade scattering my work across platforms and usernames. Here's the setup that fixed it - one domain, one blog, everything else is distribution."
tags: ["career", "guide", "personal-brand"]
---

I recently audited my entire online footprint. A decade of being a developer on the internet, and here's what a search for my work actually turned up:

- A dead portfolio site on a GitHub Pages URL that stopped existing when I renamed my account
- Three different usernames across the years, each one orphaning the last
- Posts trapped inside social platforms, unsearchable, unexportable in any useful form
- One Docker forum reply and one GitHub issue as the sum of my indexed writing

Ten years of building things, and the internet had almost no evidence of it. Not because I did nothing - because everything lived on rented land.

If your work is scattered across platforms you don't control, this is the guide I wish I'd read at year one. Total cost: about $12 a year. Total setup time: a weekend, generously.

## The principle: own the home, rent the distribution

Platforms die, pivot, or quietly bury you. Google+ died. Twitter became X and locked its content behind a login wall. Medium put readers behind a paywall you don't control. Every platform bet I made expired - the only things that survived were git repositories and things behind a domain I owned.

So the architecture is simple:

**Your domain is the permanent home. Everything else is a distribution channel.**

Content gets published on your site first, then syndicated outward - LinkedIn, Instagram, wherever your audience is. The platforms get a copy. You keep the original. When a platform fades, you lose reach, not work.

## Step 1: Buy one domain, make it your name

Buy your real name if you can get it. I use `marijan.dev` - first name plus a TLD that says what I do. Short, spellable over the phone, and it doesn't need to change when my interests do.

Rules that held up:

- **Your name, not a project name.** Projects end. Brands pivot. You are the constant. My company exists for invoicing - the work is published under me.
- **Don't overthink the TLD.** `.dev`, `.com`, `.io` - any of them beats not owning anything.
- **One domain.** The second domain is where consistency goes to die.

## Step 2: Put a boring static blog on it

Mine is Hugo with the PaperMod theme. It's deliberately boring: markdown files in a git repository, built to static HTML, served through Cloudflare. No database, no CMS to update, no monthly platform fee, nothing to hack.

The boring stack is the point. A static site from 2015 still builds today. Every "modern publishing platform" from 2015 is dead or unrecognizable. For a permanent home you want technology that changes slowly: plain text, git, HTML.

Structure that works and takes an afternoon:

- `/` - who you are, latest writing
- `/work` - case studies of real projects, the proof
- `/now` - one paragraph on what you're doing this month
- `/about` and `/contact`

That's it. Resist the redesign spiral - I say this as someone who once spent nine months on the wrong website rebuild professionally. Ship the boring version, write instead.

## Step 3: Wire up the domain properly

Two things people skip that cost nothing:

**DNS you control.** I use Cloudflare - free tier, fast, and the domain settings live in one place regardless of where the site is hosted. Host on Pages, a VPS, wherever - if you own the DNS, you can move hosts in an afternoon without breaking a single link.

**Email on your domain.** Cloudflare Email Routing forwards `hello@yourdomain` to whatever inbox you already use, free, in five minutes. A contact address on your own domain outlives every inbox migration you'll ever do - and you can hand out per-service aliases and see exactly who leaked your address.

## Step 4: Solve the username problem once

Here's a mistake that cost me my early footprint: I treated usernames as disposable. Renamed my GitHub account, and every old link - including the one on my own deployed portfolio - died. Search engines shrug and move on.

What I settled on is a two-layer identity, and I'd recommend it to any developer, especially anyone security-adjacent:

- **Real name + domain for business.** The thing clients, employers, and conference organizers can find, spell, and trust.
- **One handle for community.** Mine is `cyf0rk` - it's on GitHub and wherever hackers know each other by handle rather than passport. Pick one, keep it forever.

The two layers link to each other: the handle sits on the site, the site is in every profile bio. Either thread leads to everything.

And if you must rename an account: GitHub redirects old profile and repo URLs to the new name. Most platforms don't. Check before you jump, then update every reference you control the same day.

## Step 5: Publish home-first, syndicate everywhere

The workflow that makes all of this compound:

1. Write on your own site. Case study, writeup, opinion - the canonical version lives at your domain.
2. Repost the idea natively where your audience is. A LinkedIn version of the post. A short video of the same case study. Link home.
3. Let RSS do its quiet work. Your static site generates a feed for free - the readers who matter most subscribe directly, no algorithm in between.

The platforms are good at one thing: putting your work in front of people who've never heard of you. Use them for exactly that. Just never let them hold the only copy.

I learned this one the hard way too: posts I'd marked "published" in my own content tracker existed only inside a social platform. The captions weren't archived anywhere I controlled. The reach was rented and so was the content. Home-first means that can't happen again.

## The whole stack, priced

| Piece | Tool | Cost |
|-------|------|------|
| Domain | your registrar | ~$12/year |
| DNS + CDN | Cloudflare free tier | $0 |
| Site | Hugo + a maintained theme | $0 |
| Hosting | static hosting (Pages et al.) | $0 |
| Email | Cloudflare Email Routing | $0 |
| Archive | git repository | $0 |

Twelve dollars a year for a professional presence that nothing can delete, rename, or paywall out from under you.

## Start this weekend

The audit is the motivating part - search your own name plus your usernames and look at what a stranger would actually find. If the answer is "scattered fragments on platforms I don't control," you know the fix now:

One domain. One boring blog. Email on the domain. One handle, kept forever. Publish at home, syndicate everywhere.

Your future self - the one who's changed jobs, niches, and platforms three more times - will find everything exactly where it was left.
