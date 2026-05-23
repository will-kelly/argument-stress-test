# Argument stress-test agent

A Claude Project that stress-tests essays, Substack posts, and thought leadership pieces before publication. Paste a draft. Get back a structured report identifying every place the argument fails — before a real reader does.

This is not an editing tool. It does not improve prose or offer balanced feedback. It finds what breaks.

---

## What it does

The agent plays a skeptical expert reader and runs four passes on every submitted draft:

| Pass | What it finds |
|------|--------------|
| **1 — Unsupported assertions** | Factual claims stated without evidence, rated Minor / Moderate / Critical |
| **2 — Pattern-without-proof** | Trend or pattern claims with no named example, data, or documented case |
| **3 — Logical stress points** | Non sequiturs, false binaries, scope creep, causation/correlation slippage, implicit assumptions |
| **4 — Counterarguments** | The three strongest opposing cases, with threat level and minimum preemption move for each |

Every analysis returns the same structured report with a publish-ready verdict: **Yes**, **No**, or **Conditional**.

---

## Repository contents

```
├── PROJECT-INSTRUCTIONS.md       # Paste into Claude Project instructions — this is the agent
├── QUICK-START.md                # Upload as project knowledge — user-facing reference
└── PREEMPTION-LANGUAGE-GUIDE.md  # Upload as project knowledge — repair patterns for each finding type
```

---

## Setup

**Requirements:** A Claude.ai account with Projects (Pro, Team, or Enterprise plan).

1. Create a new Claude Project
2. Open **Project instructions** and paste the full contents of `PROJECT-INSTRUCTIONS.md`
3. Under **Project knowledge**, upload `QUICK-START.md` and `PREEMPTION-LANGUAGE-GUIDE.md`
4. Start a conversation, paste a draft, and the agent runs immediately

No API key, no code, no dependencies.

---

## Usage

**Basic stress-test**

Paste the draft directly into the conversation. No framing required. The agent goes straight to analysis and returns the report.

**With audience context**

Add one line before the draft to calibrate the skeptic persona:

```
Audience: senior HR leaders at mid-market companies.

[draft follows]
```

**After receiving the report**

Three follow-on options are offered at the end of every report:

1. **Revise and resubmit** — address the findings, paste the revised draft for a second pass
2. **Preempt the counterarguments** — agent drafts inline language to neutralize each of the three
3. **Done** — argument is sound, take it to an editor for prose polish

---

## Report structure

```
Argument stress-test report

Draft assessed: [first 10 words...]
Central claim (as read): [one sentence]

Pass 1: Unsupported assertions
Pass 2: Pattern-without-proof
Pass 3: Logical stress points
Pass 4: Three strongest counterarguments
  - Counterargument label
  - Skeptic's case
  - Threat level: Manageable / Significant / Structural
  - Minimum preempt

Verdict: Yes / No / Conditional
```

If the verdict is **Conditional** or **No**, the report ends with one to three specific structural fixes — not editorial notes, not style feedback.

---

## Severity ratings and threat levels

**Pass 1 severity**

- **Minor** — low stakes, commonly accepted; reader unlikely to challenge
- **Moderate** — contested or niche; a motivated reader may push back
- **Critical** — the argument depends on this claim; if it falls, the piece falls

**Pass 4 threat levels**

- **Manageable** — one sentence or a brief qualifier neutralizes it
- **Significant** — requires a paragraph or structural revision
- **Structural** — if this holds, the central argument may not

---

## What the agent will not do

- Rewrite your draft
- Suggest word choices or sentence-level edits
- Tell you what's working
- Soften its findings
- Ask clarifying questions mid-analysis

---

## Recommended workflow

```
Draft exists
    ↓
Argument stress-test   ← here
    ↓
Argument is sound
    ↓
Editorial polish
    ↓
Publish
```

Run the stress-test before polishing prose. Polishing first wastes effort — you may restructure or cut sections after the argument review.

---

## Adapting the persona

The default persona is a domain-calibrated skeptical expert reader. You can narrow it by specifying the audience in your submission. Examples:

- `Audience: CTOs at enterprise software companies`
- `Audience: policy researchers familiar with EU AI regulation`
- `Audience: general readers with no technical background`

The agent adjusts its frame of reference — the failure modes it prioritizes, the in-group assumptions it tests — based on what a reader in that audience would actually challenge.

---

## License

MIT
