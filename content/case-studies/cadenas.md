---
title: "CADENAS: Three and a Half Years Learning to Be a Software Engineer"
date: 2026-04-05
summary: Where two years of self-taught programming became a career - domain depth, automation instincts, and the cost of the wrong CMS decision.
---
## The Situation

CADENAS is a German engineering software company building tools for the manufacturing industry: PARTsolutions for strategic parts management, eCATALOGsolutions for electronic product catalogs, and 3dfindit - a search engine for 3D models used by engineers worldwide. This isn't a startup or an agency. It's an established B2B company with real domain complexity and a product suite that takes time to understand.

I started programming in high school, took it seriously at 19, and after two years of self-directed study landed a job there as a junior full stack developer. Those two years weren't spent on tutorials alone, I switched to Ubuntu as my main OS, learned to work in the terminal, picked up Vim and eventually made NeoVim my primary editor, learned touch typing alongside it, and started writing Lua, Bash, and some C just to understand how things worked. Not because anyone told me to. Because pulling on one thread always revealed three more. OS configuration, tool customization, understanding what's actually happening underneath the abstractions: that way of learning compounded fast.

CADENAS ran on Windows and Active Directory, so I worked in WSL: Linux tools on a Windows machine, which was less friction than it sounds when you already live in the terminal. The best unexpected resource there was the sysadmin. We ended up talking constantly about Linux, open source, security, crypto, and tooling. Through him I got exposure to Ansible and infrastructure automation at a time when most junior developers don't think about that layer at all. Those conversations shaped how I thought about systems, not just code. When cloud engineering came later (GCP architecture, infrastructure design, the way distributed systems are wired together), none of it felt foreign. The mental models were already there. Passing the GCP Cloud Engineer certification felt like formalizing something I'd already internalized, not learning from scratch.

The domain itself was entirely new to me: 3D modeling software, engineering part catalogs, manufacturing workflows. I didn't know the tools, the industry, or, honestly, enough about software development yet to know what I didn't know. What I did have was a habit of going deep on whatever I was working with, and a job that gave me surface area across a lot of different technical problems.

## What I Worked On

Over 3.5 years I touched five distinct areas:

**PARTsolutions.** I learned the software end-to-end: how part catalogs are structured, how 3D models are classified, how manufacturing companies think about parts management. Domain knowledge most developers never acquire, because most developers never need it.

On the **regex parser and data automation** side, I built a regex-based parser for classifying 3D models, and alongside that automated large amounts of data entry work using bash and PowerShell scripts. The lesson that stuck: if you're doing the same tedious thing more than a few times, write code to do it instead.

**Internal tracking application** - I inherited a work-tracking tool a colleague had built and worked on extending it. This was the first time I was really inside a real application codebase, not just scripts or config. It meant understanding how someone else's design decisions constrained what you could add next.

**3dfindit** gave me frontend components and CRM API integration for data collection on a globally-used engineering search platform, small contributions to a real product that real engineers used, and that distinction matters when you're junior.

**The website rewrite** was the long arc that taught me the most, including things I didn't want to learn.

## How It Happened

**Year one: learning the domain.** I spent most of the first year inside PARTsolutions, learning how engineering software works, how 3D models are structured and classified. The regex and automation work came out of necessity, data entry at scale is unsustainable by hand, and writing scripts to handle it felt like the obvious move. It was the first time I'd solved a real work problem with code, not a practice exercise.

**Getting into real development (years one to two).** The internal tracking app was where I started thinking like a developer rather than someone who writes scripts. Working on 3dfindit raised the stakes, frontend components on a real product, making API calls to a CRM system for data collection. Still junior, but building things that were actually used.

**The website project (years two to three and a half).** The existing CADENAS website was built on Contao, a PHP CMS, and whoever had built it had made a decision that caused years of problems: customizing the core instead of extending it properly. When you modify a CMS at the framework level, you lose the ability to update it. Every update becomes a manual merge of changes that may or may not conflict with yours. Knowledge of what was changed and why lives only in people's heads. Maintenance costs compound quietly until they become impossible to ignore.

Management decided to move to WordPress. The technical direction was reasonable, the tool choice wasn't. Elementor was added to the stack to make development "faster and easier," which is how it was sold to management. What it actually did was create a performance ceiling that made the site slower than what it was replacing. I was junior enough that when seniors I trusted didn't push back hard, I followed the direction. What I didn't know then and learned only later was that those seniors had doubts too, but the decision had already been made above them.

Nine months into the Elementor build, a developer I worked with introduced Gutenberg blocks, which had just become viable. The difference in performance was immediate and obvious. This was what the right technical call felt like compared to the wrong one. But the project was too far behind schedule, and management made the call: cut WordPress entirely, rewrite the Contao codebase in Symfony following proper standards. That was the right technical decision the one that should have been made earlier.

I started working on the Symfony rewrite with that developer. Three and a half years in, I left. Not because the Symfony direction was wrong, it was the right call. But I'd spent long enough in an environment where I couldn't bring new ideas, couldn't influence architecture decisions, and couldn't grow in the directions I wanted to grow. Leaving was deliberate.

## What It Produced

- Genuine domain knowledge in 3D modeling, engineering parts management, and manufacturing software, a technical area most developers never touch
- Shell scripting as a practical tool: bash and powershell for real automation, not tutorials
- Frontend and API integration experience on 3dfindit, a globally-used engineering platform
- A clear-eyed understanding of what happens when you make the wrong CMS decision and why, not from reading about it, but from living inside it for two years
- The ability to recognize what a good engineering environment looks like, built from experience in one that wasn't

## Why It Matters

Every developer has an origin story. This is mine, the place where two years of self-taught programming became something I could build a career on.

The instincts that made the CircuitMess API work, automate the tedious, build a source of truth, don't trust scripts as infrastructure, came from CADENAS. The ability to read a messy codebase and understand *why* it got that way came from CADENAS. Knowing when to push back on a technical direction, and what it costs when nobody does, came from the website project.

If you're evaluating a developer's background, look for the place where they built the instincts. For me, it was here.
