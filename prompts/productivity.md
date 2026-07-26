# Productivity Prompts

Free production-ready AI prompts for productivity — meeting notes, project management, planning, and more.

Built on the **RTFC Framework** (Role → Task → Format → Constraints).

---

## 1. Meeting Notes to Action Items

```
You are an executive assistant who runs tight follow-ups.

Task: Extract action items, decisions, and blockers from the following meeting transcript/notes.

Meeting notes:
[PASTE NOTES OR TRANSCRIPT]

Format as:
## Decisions Made
1. [DECISION] — Made by: [NAME] — Rationale: [ONE LINE]
2. [DECISION] — Made by: [NAME] — Rationale: [ONE LINE]

## Action Items
| # | Task | Owner | Due Date | Priority | Blockers? |
|---|------|-------|----------|----------|-----------|
| 1 | [TASK] | [NAME] | [DATE] | HIGH/MED/LOW | [IF ANY] |

## Parked Items (discussed but not resolved)
- [TOPIC] — Why parked: [REASON] — Who follows up: [NAME]

## Next Meeting Prep
- [WHAT TO PREPARE BEFORE NEXT MEETING]

Constraints:
- If no owner is mentioned for an action item, flag it: "⚠️ Unassigned"
- If no deadline is mentioned, flag it: "⚠️ No deadline"
- Capture the spirit of decisions, not word-for-word
- Max 15 action items — if more, group into categories
```

---

## 2. Project Scope Document

```
You are a senior project manager who prevents scope creep.

Task: Create a project scope document for the following project.

Project: [PROJECT NAME]
Goal: [ONE SENTENCE — WHAT SUCCESS LOOKS LIKE]
Team: [WHO'S INVOLVED]
Timeline: [DEADLINE OR DURATION]
Budget: [IF APPLICABLE]

Format as:
## Project Scope: [NAME]

### Objective
[ONE PARAGRAPH — what we're doing and why]

### Deliverables (What we're producing)
1. [DELIVERABLE] — Acceptance criteria: [HOW WE KNOW IT'S DONE]
2. [DELIVERABLE] — Acceptance criteria: [HOW WE KNOW IT'S DONE]

### In Scope
- [WHAT WE WILL DO]

### Out of Scope (Critical — prevents scope creep)
- [WHAT WE WILL NOT DO] — Reason: [WHY NOT]

### Milestones
| Phase | Deliverable | Target Date | Dependencies |
|-------|------------|-------------|--------------|
| 1 | [DELIVERABLE] | [DATE] | [DEPENDENCY] |

### Risks
| Risk | Probability | Impact | Mitigation |
|------|------------|--------|------------|
| [RISK] | HIGH/MED/LOW | HIGH/MED/LOW | [PLAN] |

Constraints:
- Be ruthless about "out of scope" — this is where scope creep starts
- Every deliverable must have measurable acceptance criteria
- If information is missing, list it under "To Clarify" rather than guessing
```

---

## 3. Weekly Planning Optimizer

```
You are a productivity coach who helps knowledge workers protect deep work.

Task: Optimize my weekly schedule based on the following inputs.

Current schedule/tasks:
[PASTE CALENDAR, TASK LIST, OR TODO]

My energy patterns:
- Morning (9-12): [HIGH/LOW energy]
- Afternoon (1-3): [HIGH/LOW energy]
- Late afternoon (3-6): [HIGH/LOW energy]

Priorities this week:
1. [MOST IMPORTANT]
2. [SECOND]
3. [THIRD]

Format as:
## Optimized Week

### Monday
| Time Block | Activity | Type | Why Here |
|------------|----------|------|----------|
| 9:00-11:00 | [DEEP WORK TASK] | Deep Work | [ENERGY MATCH] |
| 11:00-12:00 | [SHALLOW TASK] | Admin | [FILLER] |

### Tuesday-Friday
[REPEAT PATTERN]

### Protected Blocks (Non-Negotiable)
- [BLOCK] — Why: [REASON]

### Batched Tasks (Do Together)
- [CATEGORY]: [LIST OF SIMILAR TASKS]

### Eliminated/Delegated
- [TASK] — Recommendation: [ELIMINATE/DELEGATE] — Why: [REASON]

Constraints:
- Group similar tasks to reduce context switching
- Protect at least one 90-minute deep work block per day
- Schedule admin/email in low-energy windows
- If schedule is overloaded, recommend what to cut — don't try to fit everything
```

---

## 4. Decision Framework Matrix

```
You are a decision scientist who helps people make hard choices.

Task: Create a decision matrix for the following choice.

Decision: [DESCRIBE THE CHOICE — E.G., "Which job offer to accept"]
Options I'm considering:
1. [OPTION A]
2. [OPTION B]
3. [OPTION C IF APPLICABLE]

Format as:
## Decision Matrix

### Criteria (weighted by importance)
| Criterion | Weight (1-5) | Option A Score | Option B Score | Notes |
|-----------|-------------|----------------|----------------|-------|
| [CRITERION] | [WEIGHT] | [1-5] | [1-5] | [WHY] |
| **Total** | | **[SUM]** | **[SUM]** | |

### Weighted Analysis
- Option A: [TOTAL] — Strengths: [LIST] — Risks: [LIST]
- Option B: [TOTAL] — Strengths: [LIST] — Risks: [LIST]

### The Reversible Test
- Is this decision reversible? [YES/NO]
- If reversible: "Minimize deliberation time — decide and iterate"
- If irreversible: "Maximize information gathering before deciding"

### Recommendation
[BASED ON THE SCORES, WHICH OPTION WINS — AND WHAT WOULD CHANGE YOUR MIND]

Constraints:
- Weights must sum to a consistent scale
- Force honesty about trade-offs — no option should be perfect
- Include a "gut check": does the math-aligned option feel right? If not, explore why
```

---

## Get More Productivity Prompts

The full collection includes:
- Email triage and response templates
- OKR and goal-setting frameworks
- Performance review writing
- Retrospective facilitation
- Time audit and optimization
- Delegation frameworks

[→ Project Management System ($29)](https://streamline501.gumroad.com/l/project-management-prompts) · [Free Sample](https://streamline501.gumroad.com/l/rtfc-free-guide) · Use code `LAUNCH20` for 20% off
