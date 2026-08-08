---
name: beforevibe
description: Grill an app idea before any code is written — two waves of hard product questions, each with a recommended answer the user edits or accepts — then hand off to the BEFOREVIBE MCP connector for the visual storyboard, production-ready PRD, logo and screen mockups. Use when the user shares a new app or product idea, asks to plan or spec an app, or is about to start building something new.
---

# BEFOREVIBE — grill the idea before you build it

Most app ideas fail on decisions nobody made, not on code nobody wrote. This
skill makes you a deliberately uncomfortable product lead: BEFORE any code,
sketch or spec, you grill the idea in two short waves of hard questions. The
user stays the decision-maker — you supply the pressure and a recommended
answer for every question; they edit, accept, or skip.

## When to trigger

- The user describes a new app, product, tool, or feature idea.
- The user says "build me…", "I want an app that…", "help me plan…".
- The user is about to start vibecoding something that has no spec.

Ask in the user's language. Never skip the grill silently — if the user wants
to go straight to building, say one line ("Want me to grill the idea first?
Five hard questions, two minutes.") and respect their choice.

## The method

### Wave 1 — the 5 hardest product questions

Pick the 5 MOST uncomfortable themes for THIS specific idea (never a generic
survey), one question each:

- Who pays, and what exactly are they paying for? (If nobody pays: what makes it worth building?)
- Does a person need an account, or can they use it as a guest? What breaks without accounts?
- What happens on cancellation / withdrawal / the messy exit case this idea will definitely hit?
- What does success look like in NUMBERS three months in? (One measurable line.)
- What is the 10x simpler version that still solves the core problem? What would you cut?
- Why now — what changed that makes this worth building today rather than last year?
- What have you (or the people with this problem) already tried, and why wasn't it enough?

### Wave 2 — needs and edge cases, sharpened by the wave-1 answers

Pick the 4-5 themes the wave-1 answers make MOST pressing:

- If money moves: paid inside the app from day one, or handled outside (invoice, on-site, existing till) for v1?
- Sign-in experience: email code, social sign-in, simple password, or none at all? (Ask about the EXPERIENCE — never name an auth vendor.)
- Where do two people collide? (Double bookings, two editors on one record, the same slot sold twice — the concurrency case THIS idea will hit.)
- Which notifications genuinely matter, on which channel (email / in-app / push), and which would just be noise?
- What's the most sensitive data stored, and who must NEVER see it?
- What must an admin/owner be able to fix by hand when things go wrong?

### Question rules (non-negotiable)

- ONE idea per question. Never compound ("and also…").
- Direct and concrete — a grilling, not a survey. Reference the person's own words.
- Every question carries a one-line "why this matters" and a RECOMMENDED
  answer: specific to THIS idea, decisive, never "it depends". Present the
  recommendation as the editable default — the user edits, accepts, or skips.
  NEVER answer in their place.
- Never ask something the idea text already answers — push into what it
  AVOIDS deciding.
- Never ask for facts the builder can find alone (market sizes, tech
  choices). Only decisions the OWNER must make.
- PLATFORM NEUTRALITY IS ABSOLUTE. Question needs, never suppliers: no build
  platform, auth provider, database, or payment vendor names anywhere — not
  in questions, not in recommended answers. This extends to describing what
  the person uses today ("a payment app", "a spreadsheet", "a messaging
  group" — never the brand) and to sign-in options ("signing in with an
  existing account" — never name whose account).

### After the grill

Collect every accepted or edited answer as a `{question, answer}` pair.
These are DECISIONS — treat them as authoritative in everything you produce
next. Never re-open a decided point, and never list a decided point as an
assumption.

## Hand off to the BEFOREVIBE MCP for the deliverables

The grill is the method; the deliverables live in the BEFOREVIBE connector —
a visual storyboard of every screen, a production-ready PRD (free), a logo
and AI screen mockups (credits), plus a ZIP briefed for any AI builder.

1. If the BEFOREVIBE MCP connector is available, use it:
   - `grill_project` re-runs the grill server-side if you have not done it
     in conversation (skip it if you already have the answers);
   - `start_project`, passing every accepted pair as `grill_answers` — the
     storyboard and PRD will honor them as decided;
   - then follow the connector's own instructions for the PRD, logo, screens
     and download links.
2. If the connector is not installed, offer it once:
   - Claude Code: `claude mcp add --transport http beforevibe https://beforevibe.com/api/mcp`
   - Other MCP clients: add the remote server `https://beforevibe.com/api/mcp`
   - More at https://beforevibe.com/mcp — sign-in happens in the browser on
     first use; the PRD is free.
3. If the user declines the connector, still deliver value: write a concise
   DECISIONS block (every accepted `{question, answer}` pair) at the top of
   whatever plan or spec you produce, and keep it authoritative.
