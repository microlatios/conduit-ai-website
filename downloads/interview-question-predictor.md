---
name: interview-question-predictor
description: >
  Predict the most likely interview questions from a job description. Use this skill whenever
  a job description is pasted and the goal is interview preparation, question prediction,
  or anticipating what an interviewer will ask. Trigger on phrases like "what will they ask me",
  "predict interview questions", "prep me for this interview", "likely questions",
  "what should I prepare for", or any JD shared with an interview-prep intent.
---

# Interview Question Predictor

Predicts the 8 highest-probability interview questions from a JD, mapped to source language.

## Input

**Job Description** — pasted text or uploaded file.

## Workflow

### Step 1: Parse the JD

Extract question-generating components: core responsibilities, required skills, soft skill signals, level indicators, team context, company stage. **Anything mentioned twice is an anxiety signal — expect the hardest questions there.**

### Step 2: Preparation Summary

Before listing questions, distill the three things the candidate absolutely must prepare. Each bullet is one sharp sentence: what the story is, what it must include, and why it matters. Written to be skimmable in 10 seconds. These map directly to the hot seat questions below.

Format:
```
### Prepare These Three Things
- **{Label}.** {What to prepare + what it must include, in one sentence.}
- **{Label}.** {What to prepare + what it must include, in one sentence.}
- **{Label}.** {What to prepare + what it must include, in one sentence.}
```

### Step 3: Generate 8 Questions

**3 Hot Seat 🔥** — The questions most likely to determine the outcome. Must map to repeated themes or core responsibilities. Add one line on what separates a strong answer from a weak one.

**1 Behavioral** — Best past-experience question mapped to the JD's primary responsibility. Must be role-specific, not generic.

**1 Technical / Competency** — Tests whether you can do the job. For senior roles, systems-level ("how would you design...") over task-level ("how do you use tool X").

**1 Situational** — Tests judgment on the role's implicit tension (speed vs quality, autonomy vs alignment, etc.).

**1 Culture-Fit** — Mapped to company values or stage signals.

**1 Trap / Differentiator** — The question most people don't prepare for.

### Step 4: Format Each Question

Each question gets:
- The question text
- **Source + why** — one line combining the JD phrase that triggers it and what the interviewer assesses

For Hot Seat questions only, add one line on strong vs weak answer signals.

### Step 5: Interviewer Map

Predict which question types come from which interviewer round (1-2 lines per round).

---

## Output Format

```
## Interview Questions — {Company}, {Role Title}

### Prepare These Three Things
- **{Label}.** {One sentence.}
- **{Label}.** {One sentence.}
- **{Label}.** {One sentence.}

### 🔥 Hot Seat (3)
{Question + source/why + strong vs weak signal}

### Behavioral
{Question + source/why}

### Technical
{Question + source/why}

### Situational
{Question + source/why}

### Culture-Fit
{Question + source/why}

### Trap / Differentiator
{Question + source/why}

### Interviewer Map
{1-2 lines per round}
```

---

## Principles

- **Specific beats generic.** Every question specific enough that the user knows which experience to reach for.
- **The JD is the answer key.** Every question traces to JD language. No source = cut the question.
- **Repeated themes are anxiety signals.** Cluster the hardest questions there.
- **Don't write answers.** Predict questions and explain why. The user's real experience is the only thing that works.
