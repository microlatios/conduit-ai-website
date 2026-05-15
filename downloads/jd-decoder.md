---
name: jd-decoder
description: >
  Decode a job description into plain language — what the role actually is, what the company
  really wants, and what the JD isn't telling you. Use this skill whenever a job description
  is pasted and the goal is understanding or evaluating the role rather than optimising a
  resume or preparing for an interview. Trigger on phrases like "what does this role actually do",
  "decode this JD", "break this down", "what are they really looking for",
  "is this JD legit", "red flags in this JD", or any JD shared with an evaluative intent.
---

# JD Decoder

Translates a job description from corporate language into a plain-language breakdown.

## Input

**Job Description** — pasted text or uploaded file.

## Workflow

### Step 1: Translate the Role Into Plain Language

Rewrite what this person will actually do day-to-day in 2-3 sentences. No jargon. Write it as if explaining to a friend.

Decode euphemisms, respect straightforward language:
- "Drive revenue growth across strategic accounts" → "You're selling to big companies and own a number"
- "Partner cross-functionally" → "You'll spend time getting other teams to prioritise your requests"
- "Thrive in ambiguity" → "No playbook — figure it out"

### Step 2: Estimated Salary Range

Research and estimate the salary range for this role using:
- Company, title, seniority level, and location
- Public data from Glassdoor, Levels.fyi, LinkedIn Salary, or comparable sources
- Adjust for regional market (e.g., Singapore vs. SF vs. London)
- Note whether the role likely includes variable/commission and estimate total OTE if applicable

Present as a range (e.g., SGD 150K–190K base + 20–30% variable) with a one-line confidence note explaining the basis (e.g., "Based on Glassdoor data for similar titles at this company" or "Estimated from comparable roles at peer companies — no public data for this specific role").

### Step 3: Company Snapshot

In 3-4 sentences, cover:
- **What they do** — one-line plain-language description of the product/business
- **Key competitors** — 2-3 direct competitors by name
- **Market perception** — how the company is regarded in its space (market leader, challenger, niche, declining, etc.) and any notable brand strengths or weaknesses relevant to a candidate's decision

Use web search to verify current positioning. Don't pad — if the company is well-known, keep it brief.

### Step 4: Infer the Real Seniority Level

Use reporting line, decision authority, scope, budget language, team language, and years required to infer actual level. Flag any title/level mismatch in one sentence.

### Step 5: Separate Real Requirements from Wish List

Classify the **top 4 most decisive requirements only** into tiers:

| Tier | Signal |
|---|---|
| **1 — Dealbreaker** | Appears in both requirements AND responsibilities; specific credential; role can't function without it; mentioned 2+ times |
| **2 — Preference** | Only in requirements section; softener language ("ideally", "preferred"); transferable skills apply |
| **3 — Wish list** | Vague/unmeasurable; contradictory; generic professional skills |

Present as a 4-row table max: `| Requirement | Tier | Why (one phrase) |`

### Step 6: Red Flags and Green Flags

2-3 of each max. Every flag must cite specific JD language.

**Red flag categories:** unicorn hunting, ghost posting, scope without authority, revolving door, compensation opacity, contradictory culture signals, jargon density with no substance.

**Green flag categories:** specific success metrics, realistic scope, clear reporting line, investment signals, honest challenge language.

### Step 7: Questions to Ask Them

3-4 ready-to-use interview questions based on identified gaps and omissions.

---

## Output Format

```
## JD Decoder — {Company}, {Role Title}

### What This Role Actually Is
{2-3 sentences}

### Estimated Salary Range
{Range + one-line confidence note}

### Company Snapshot
{3-4 sentences: what they do, competitors, market perception}

### Real Seniority Level
{1-2 sentences with reasoning. Flag title mismatch if present.}

### Requirements: What Actually Matters
| Requirement | Tier | Why |
|---|---|---|
{Max 4 rows}

### 🚩 Red Flags
{2-3 bullets, each citing JD language}

### 🟢 Green Flags
{2-3 bullets, each citing JD language}

### Questions to Ask Them
{3-4 ready-to-use questions}
```

---

## Principles

- **Decode, don't judge.** Flag signals, let the user decide.
- **Honesty without cynicism.** Not every JD is hiding something.
- **Every flag needs evidence.** Cite the JD language that triggered it.
- **The omissions are the insight.** What a JD doesn't say is often more informative than what it does.
