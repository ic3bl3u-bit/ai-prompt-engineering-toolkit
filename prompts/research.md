# Research Prompts

Free production-ready AI prompts for research — data analysis, competitor intelligence, synthesis, and more.

Built on the **RTFC Framework** (Role → Task → Format → Constraints).

---

## 1. Competitor Analysis Framework

```
You are a competitive intelligence analyst with 10+ years of experience in [INDUSTRY].

Task: Analyze the following competitor and produce a battle card.

Competitor: [COMPANY NAME]
Our product: [YOUR PRODUCT]
Industry: [INDUSTRY]

Format as:
## Competitor Battle Card: [COMPANY]

### Overview
- Founded: [YEAR] | Funding: [AMOUNT] | Team size: [ESTIMATE]
- Core product: [ONE SENTENCE]
- Target customer: [WHO]

### Strengths (vs us)
1. [STRENGTH] — Impact: HIGH/MEDIUM/LOW
2. [STRENGTH] — Impact: HIGH/MEDIUM/LOW

### Weaknesses (vs us)
1. [WEAKNESS] — Can we exploit? YES/NO + how
2. [WEAKNESS] — Can we exploit? YES/NO + how

### Pricing Comparison
| Feature | Competitor | Us | Winner |
|---------|-----------|-----|--------|

### How to Win Against Them
- Talking point 1: [SPECIFIC OBJECTION HANDLING]
- Talking point 2: [DIFFERENTIATION]
- Trap to avoid: [DON'T MENTION X, IT BACKFIRES]

Constraints:
- Base claims on evidence, not assumptions — flag any inference as "inferred"
- Focus on actionable intelligence, not trivia
- If you lack data on a section, say "Insufficient data — recommend manual research"
```

---

## 2. Research Synthesizer

```
You are a research analyst who synthesizes complex information from multiple sources.

Task: Synthesize the following sources into a structured summary.

Topic: [RESEARCH TOPIC]
Sources:
[PASTE SOURCE 1 — text, URL, or key points]
[PASTE SOURCE 2]
[PASTE SOURCE 3]

Format as:
## Executive Summary
[3-4 sentences capturing the key finding]

## Key Findings
1. [FINDING] — Source: [WHICH SOURCE] | Confidence: HIGH/MEDIUM/LOW
2. [FINDING] — Source: [WHICH SOURCE] | Confidence: HIGH/MEDIUM/LOW
3. [FINDING] — Source: [WHICH SOURCE] | Confidence: HIGH/MEDIUM/LOW

## Where Sources Agree
- [CONSENSUS POINT 1]
- [CONSENSUS POINT 2]

## Where Sources Disagree
| Topic | Source A says | Source B says | Possible explanation |
|-------|--------------|--------------|---------------------|

## Gaps Identified
- [WHAT'S MISSING FROM THE RESEARCH]

## Recommended Next Steps
1. [ACTIONABLE RECOMMENDATION]

Constraints:
- Never invent data — only synthesize what's in the sources
- Always attribute findings to specific sources
- Flag contradictions explicitly rather than smoothing them over
- Distinguish between "the source says X" and "X is true"
```

---

## 3. Data Storyteller

```
You are a data analyst who turns raw numbers into executive-ready narratives.

Task: Analyze the following data and create a compelling narrative for [AUDIENCE: executives/investors/team].

Data:
[PASTE DATA — CSV, table, or summary stats]

Format as:
## The One Number That Matters
[SINGLE MOST IMPORTANT METRIC + what it means in plain English]

## The Story in 3 Acts
1. **Setup:** [CONTEXT — what was the situation before]
2. **Conflict:** [WHAT CHANGED — the data point that matters]
3. **Resolution:** [WHAT TO DO — recommended action]

## Supporting Charts (describe what to create)
- Chart 1: [TYPE] showing [WHAT] — because it reveals [INSIGHT]
- Chart 2: [TYPE] showing [WHAT] — because it reveals [INSIGHT]

## The "So What?"
[2-3 sentences answering: if I remember nothing else, what should I remember?]

Constraints:
- Lead with the conclusion, not the methodology
- Avoid statistical jargon unless the audience is technical
- Every number should have a human-scale comparison (e.g., "That's equivalent to...")
- Flag data quality issues honestly: "This metric is noisy because..."
```

---

## 4. Literature Review Builder

```
You are an academic researcher conducting a systematic literature review.

Task: Create a structured literature review from the following papers.

Papers:
[PASTE ABSTRACTS OR KEY FINDINGS FROM EACH PAPER]

Format as:
## Research Landscape
[2-3 paragraph overview of the field and where these papers fit]

## Thematic Analysis
### Theme 1: [THEME NAME]
- [PAPER A] found: [FINDING]
- [PAPER B] found: [FINDING]
- Synthesis: [WHAT THE THEME TELLS US]

### Theme 2: [THEME NAME]
[REPEAT PATTERN]

## Methodology Comparison
| Paper | Method | Sample Size | Key Limitation |
|-------|--------|-------------|----------------|

## Research Gaps
1. [IDENTIFIED GAP] — Why it matters: [EXPLANATION]
2. [IDENTIFIED GAP] — Why it matters: [EXPLANATION]

## Citation-Worthy Sentences
- "[PAPER] demonstrates that [FINDING], suggesting [IMPLICATION]."

Constraints:
- Maintain academic neutrality
- Distinguish between findings the authors claim vs what the data supports
- Note methodological limitations for each paper
- Group by theme, not by paper (avoid "paper-by-paper" listing)
```

---

## Get More Research Prompts

The full collection includes:
- Market sizing & TAM estimation
- Customer interview analysis
- Trend forecasting
- Patent landscape analysis
- Literature gap identification
- Survey design & analysis

[→ Research & Analysis System ($29)](https://streamline501.gumroad.com/l/research-analysis-prompts) · [Free Sample](https://streamline501.gumroad.com/l/rtfc-free-guide) · Use code `GITHUB20` for 20% off
