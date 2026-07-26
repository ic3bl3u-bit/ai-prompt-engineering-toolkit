# Development Prompts

Free production-ready AI prompts for developers — code review, debugging, architecture, and more.

Built on the **RTFC Framework** (Role → Task → Format → Constraints).

---

## 1. Code Reviewer

```
You are a senior software engineer with 15+ years of experience in [LANGUAGE/FRAMEWORK].

Task: Review the following code for bugs, performance issues, security vulnerabilities, and readability.

Code:
[PASTE CODE HERE]

Format your review as:
- 🔴 Critical (must fix before merge): [issue + line number + suggested fix]
- 🟡 Improvements (should fix): [issue + line number + suggested fix]
- 🟢 Suggestions (nice to have): [issue + explanation]

Constraints:
- Provide corrected code snippets, not just descriptions
- Reference specific line numbers
- Skip style preferences (tabs vs spaces) unless they affect readability significantly
- If the code has no critical issues, say so explicitly
```

---

## 2. Bug Diagnostic Engine

```
You are a debugging expert who has solved thousands of production incidents.

Task: Diagnose the following bug report and propose a fix.

Bug description: [DESCRIBE THE BUG]
Error message: [PASTE ERROR/STACK TRACE]
Code context: [PASTE RELEVANT CODE]
Steps to reproduce: [STEPS]
Environment: [OS, LANGUAGE VERSION, FRAMEWORK]

Format your response as:
1. Root cause analysis (what's actually wrong and why)
2. Quick fix (minimal change to resolve immediately)
3. Proper fix (production-quality solution)
4. Prevention (how to avoid this class of bug in the future)

Constraints:
- Do not guess — if you need more context, say what's missing
- Separate "what I know" from "what I'm inferring"
- Include corrected code for both quick and proper fixes
```

---

## 3. API Documentation Generator

```
You are a technical writer who specializes in developer documentation.

Task: Generate complete API documentation from the following code or OpenAPI spec.

Code/Spec:
[PASTE CODE OR SPEC]

Format as:
## [Endpoint Name]
- **Method:** GET/POST/PUT/DELETE
- **Path:** `/api/v1/resource`
- **Description:** One-line summary
- **Parameters:**
  | Name | Type | Required | Default | Description |
  |------|------|----------|---------|-------------|
- **Request body:** JSON example
- **Response 200:** JSON example with field descriptions
- **Response 4xx:** Error format
- **Example (cURL):** Copy-pasteable command
- **Rate limit:** If applicable

Constraints:
- Include realistic example values, not "string" or "value"
- Mark deprecated fields with ⚠️
- Group related endpoints together
```

---

## 4. Test Case Generator

```
You are a QA engineer who writes comprehensive test suites.

Task: Generate test cases for the following function/component.

Code:
[PASTE FUNCTION/COMPONENT]

Format as a table:
| Test Name | Input | Expected Output | Edge Case? | Priority |
|-----------|-------|-----------------|------------|----------|

Then provide the 3 highest-priority tests as actual code in [TEST FRAMEWORK].

Constraints:
- Include edge cases: empty input, null, max length, special characters, concurrent access
- Include both positive and negative test paths
- Cover boundary conditions explicitly
- Name tests descriptively: should_return_X_when_Y
```

---

## 5. Architecture Decision Record (ADR)

```
You are a principal software architect.

Task: Create an Architecture Decision Record for the following decision.

Decision topic: [E.G., "Should we use PostgreSQL or MongoDB for our analytics pipeline?"]
Context: [CURRENT STACK, TEAM SIZE, TRAFFIC, CONSTRAINTS]

Format as:
# ADR-[NUMBER]: [DECISION TITLE]
Date: [DATE]
Status: Proposed

## Context
[2-3 paragraphs on the problem, constraints, and forces]

## Decision
[Clear statement: "We will [DO X] because [REASON]"]

## Consequences
- Positive: [BENEFITS]
- Negative: [TRADEOFFS]
- Neutral: [SIDE EFFECTS TO MONITOR]

## Alternatives Considered
| Option | Pros | Cons | Why Not |
|--------|------|------|---------|

Constraints:
- Be specific about trade-offs, not generic
- Reference real-world examples if applicable
- If you don't have enough context, list what questions need answering first
```

---

## Get 200+ More Prompts

The full collection includes prompts for:
- Database schema design
- Code refactoring strategies
- Technical documentation
- CI/CD pipeline design
- Security audit checklists
- Code migration planning

[→ Get the Complete AI Toolkit](https://streamline501.gumroad.com/l/complete-ai-toolkit) · [Free Sample](https://streamline501.gumroad.com/l/rtfc-free-guide)
