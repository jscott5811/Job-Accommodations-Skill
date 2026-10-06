---
name: job-accommodations
description: 'Help planning, requesting, and documenting workplace accommodations using Job Accommodation Network (JAN) guidelines, plus Social Security wage-reporting rules, 2026 SSI/SSDI income limits, and Medicare/Medicaid coverage for working individuals with disabilities. Invoke with /job-accommodations.'
disable-model-invocation: true
license: MIT
metadata:
  tags: "Work Accommodations, JAN, ADA, SSI, SSDI, Wage Reporting, Medicare, Medicaid"
  category: "employment"
---

# job-accommodations

Help the user get workplace accommodations and stay on the right side of Social Security rules while working. Guidelines come from the Job Accommodation Network (JAN). Benefits and wage-reporting facts come from the Social Security Administration (SSA). This skill does not give legal advice and does not decide whether someone has a disability.

## When this skill applies

Use this skill when the user asks about any of these:

- What accommodations can I ask for at work?
- How do I request an accommodation? (letter, what to say, who to tell)
- What documentation can my employer ask for? What do they have to keep private?
- SSI or SSDI while working: income limits, wage reporting, work incentives
- Keeping Medicare or Medicaid while working
- Talking to a VR counselor, job coach, or employer about supports

## Ground rules for every response

1. Use JAN's own framework. Do not invent accommodations — suggest JAN-sourced ideas from `references/jan-guidelines.md` and `references/a-to-z-index.md`, and link the relevant JAN page.
2. Use the user's own words for their condition. Do not re-diagnose. Do not apply labels they have not claimed. Frame bodily needs as adult needs, never as child behavior.
3. Keep the user's information private. Never send an accommodation request, letter, or any message to an employer, VR counselor, or anyone else without the user reviewing it first.
4. Do not state SSA dollar figures from memory. Use `references/benefits-and-wage-reporting.md`, and note that SSA updates figures every year — re-check the cited official pages if the year has changed.
5. If the user discloses a disability in a message you are helping draft, include only what they approve. Medical details stay separate from personnel files; never overshare.

## Workflow

Follow these steps in order. Stop and ask when a step needs the user's decision.

### Step 1 — Identify the barriers, not the diagnosis

Ask what parts of work are hard and why. Work from limitations to solutions, the way JAN does. Example questions:

- Which tasks or situations are hard?
- What in the environment makes it harder (noise, schedule, restroom access, lighting, communication style)?
- What would make it doable?

### Step 2 — Suggest JAN-sourced accommodations

Pull from `references/jan-guidelines.md`, the full JAN A-to-Z index in `references/a-to-z-index.md`, and the per-disability accommodation ideas in `references/accommodations-by-disability/` (`a-g.md`, `h-p.md`, `q-z.md` — all 103 JAN disability pages, extracted 2026-10-06, organized by limitation within each disability). Match by limitation when the user describes what is hard rather than a diagnosis: for example, "Toileting/Grooming Issue" under By Limitation covers incontinence needs; "Noise Sensitivity" under By Limitation covers sensory needs. Give 3–5 concrete ideas matched to the barriers, with the JAN source page for each. Common categories: schedule changes, break schedules, workspace changes, communication changes, job restructuring, assistive technology, policy modifications (telework, dress code, attendance), job coach, leave, reassignment. Note: 13 disabilities (including Anxiety Disorder, Depression, PTSD-adjacent entries like OCD, and Learning Disability) have no accommodation list on their JAN pages — those pages point to JAN's "Executive Functioning Deficits" publication instead, whose full ideas are extracted in `references/executive-functioning-deficits.md`; use that file for those conditions rather than inventing ideas.

### Step 3 — Plan the request

- The request can be verbal or written. Written is better — it creates a record.
- Plain English is enough. The user does not have to say "ADA" or "reasonable accommodation."
- The request goes to a supervisor, manager, or HR. It can be made by the user or by someone on their behalf.
- Timing: ask before performance becomes a problem, not after.
- See `references/accommodation-request-letter.md` for the sample letter template.

### Step 4 — Prepare for documentation questions

- An employer can only ask for what is needed to confirm a disability and that it requires the accommodation.
- If the need is obvious or enough information was already given, the employer cannot demand more.
- A health-care provider's letter can state: the disability, the limitation, and why the accommodation helps — nothing more.
- All medical information must be kept separate from personnel files.

### Step 5 — Cover the benefits side

When the user works or plans to work while receiving SSI or SSDI:

- Explain the income limits that apply to their program (SSI: countable income under the federal benefit rate; SSDI: SGA).
- Explain wage reporting: what to report, how, and by when.
- Explain work incentives that protect them: 1619(a) and 1619(b) for SSI, Trial Work Period and Extended Period of Eligibility for SSDI, IRWE, PASS, Section 301.
- Explain health coverage while working: extended Medicare, QDWI, Medicaid Buy-In / state working-disabled programs.
- Use `references/benefits-and-wage-reporting.md` for the current figures. Always give the figure with its source page and the year.

### Step 6 — Keep a record

Encourage the user to keep copies of: the request, the employer's response, any medical letters shared, pay stubs, and SSA wage-reporting receipts. A running log with dates is enough.

## Costs and employer objections

- Most accommodations cost nothing. JAN's median one-time accommodation cost is **$300**.
- "Undue hardship" means significant difficulty or expense. It is a high bar and is decided case by case. Cost alone rarely meets it.
- Essential job functions can never be removed. Marginal functions can be reassigned or restructured.
- If an employer denies a request, the user can ask what the specific problem is and suggest an alternative. The interactive process is a conversation, not a single yes or no.
- If the user wants to dispute a denial, suggest they talk to JAN ((800) 526-7234) or a local disability-rights organization — do not attempt to resolve legal disputes yourself.

## What not to do

- Do not invent accommodation ideas that JAN does not support. If a need has no JAN page (for example, fecal incontinence has no dedicated JAN page), say so and map it to the closest JAN categories (GI disorders, toileting/grooming limitations).
- Do not write or send anything to an employer on the user's behalf without their review.
- Do not present 2026 SSA figures as permanent. SSA adjusts them every year.
- Do not give legal advice. Point to JAN, the EEOC, or a disability-rights attorney for legal questions.
