# PRD Evaluation Rubric

Detailed scoring criteria for each evaluation dimension. Use this as a reference when assessing PRDs.

---

## 1. Context & Why

**Purpose**: Ensure the PRD explains the reasoning behind the initiative so future readers understand without tribal knowledge.

### 🟢 Strong
- Clear problem statement that explains the user pain point or business need
- Historical context included (what was tried before, why it didn't work, or why this is new)
- Compelling "why now" explanation (market timing, technical enablement, strategic priority)
- Hypotheses are explicitly stated and testable
- A new team member could understand the decision rationale by reading only this document

### 🟡 Adequate
- Has an overview section but missing some context
- Problem is stated but "why now" is unclear
- Hypotheses are present but vaguely worded
- Some background requires insider knowledge to fully understand

### 🔴 Needs Work
- Missing "why" - jumps straight to "what" we're building
- No historical context or alternatives considered
- No hypotheses stated
- Assumes reader already knows the backstory
- Problem statement is a disguised solution ("Build feature X")

### Questions to Ask
- "If I read this in 2 years, would I understand why this decision was made?"
- "What problem does this solve? For whom?"
- "What would happen if we didn't build this?"

---

## 2. Technical Specification Depth

**Purpose**: Ensure engineers have enough detail to estimate, design, and implement without extensive back-and-forth.

### 🟢 Strong
- API endpoints and payloads defined (request/response shapes)
- Data models and schemas specified
- Edge cases and error states explicitly addressed
- Performance requirements stated (latency targets, expected scale, SLOs)
- Integration points with other systems documented
- Security and privacy considerations noted

### 🟡 Adequate
- High-level technical approach described
- Some API or data model details but missing specifics
- Happy path clear but edge cases not thoroughly covered
- Performance mentioned but not quantified

### 🔴 Needs Work
- No technical details - "engineering will figure it out"
- Hand-wavy implementation section
- No data model or API surface defined
- Performance and scale not considered
- Security/privacy not mentioned

### Questions to Ask
- "Could an engineer start sprint planning from this spec?"
- "What happens when X fails? What does the user see?"
- "What data do we need to store? For how long?"

---

## 3. Hypothesis → Measurement Rigor

**Purpose**: Ensure every claim about impact has a measurable way to validate or invalidate it.

### 🟢 Strong
- Each hypothesis has a corresponding metric
- Metrics are operationally defined:
  - What event triggers the measurement?
  - What calculation produces the number?
  - What tool/system captures it?
- Success thresholds stated (specific numbers, not "improved")
- Measurement timeline specified (when do we evaluate?)
- Potential confounds acknowledged (what else could affect the metric?)
- Baseline metrics provided or plan to capture them

### 🟡 Adequate
- Metrics defined but missing operational details
- Success described qualitatively ("users find it easier")
- Thresholds vague ("significant increase")
- Timeline not specified
- Confounds not considered

### 🔴 Needs Work
- Vague success metrics ("improve user experience")
- No clear way to validate hypotheses
- No specific numbers - just directional goals
- No timeline for measurement
- No baseline to compare against

### Questions to Ask
- "How will we know if this succeeded?"
- "What specific number are we trying to move? By how much?"
- "When do we measure? What's the expected timeline to see impact?"
- "What else could cause this metric to change?"

---

## 4. Scope & Constraints

**Purpose**: Ensure clear boundaries and explicit prioritization to prevent scope creep and misaligned expectations.

### 🟢 Strong
- Goals clearly stated with measurable outcomes
- Non-goals explicitly listed (what we're NOT doing and why)
- Priorities assigned (P1/P2/P3 or MoSCoW)
- Constraints documented:
  - Technical constraints (system limitations, tech debt)
  - Legal/compliance constraints
  - Timeline constraints
  - Resource constraints
- Risks identified with severity and mitigation strategies
- Dependencies explicit (other teams, external services, prerequisite work)

### 🟡 Adequate
- Goals stated but non-goals missing or sparse
- Priorities unclear or inconsistent
- Some constraints mentioned but not comprehensive
- Risks identified but mitigations vague
- Dependencies mentioned but not detailed

### 🔴 Needs Work
- Scope unclear or unbounded
- No non-goals (everything seems in scope)
- No prioritization - everything is P1
- Constraints not documented
- Risks not addressed
- Dependencies implicit or missing

### Questions to Ask
- "What are we explicitly NOT building in this phase?"
- "If we have to cut scope, what goes first?"
- "What could block this project? What's the mitigation?"
- "Who else needs to deliver for this to succeed?"

---

## 5. Future Reader Test

**Purpose**: Ensure the document is self-contained and will remain useful over time.

### 🟢 Strong
- Document is self-contained - no tribal knowledge required
- All figures and tables have captions and are referenced in text
- Jargon and acronyms explained on first use or in glossary
- External documents referenced with context (not just links)
- Links point to durable locations (not Slack, not ephemeral docs)
- Change log maintained with dates and what changed
- Version clearly indicated

### 🟡 Adequate
- Mostly readable but some unexplained terms
- Some figures not referenced or captioned
- External links present but some may rot
- No change log but document is recent
- Minor tribal knowledge assumptions

### 🔴 Needs Work
- Requires significant tribal knowledge to understand
- Heavy link rot risk (Slack links, temporary docs)
- No change log on a document with history
- Acronyms and jargon unexplained
- Figures/data referenced but not included or linked
- Reader would need to ask author for clarification

### Questions to Ask
- "Could a new hire understand this without asking questions?"
- "Will these links still work in 6 months?"
- "If I updated this doc, would I know what changed before?"

---

## Scoring Summary Table

| Dimension | Key Question | Strong Signal | Weak Signal |
|-----------|-------------|---------------|-------------|
| Context & Why | "Why this, why now?" | Clear problem + history + hypotheses | Jumps to solution |
| Technical Depth | "Can eng estimate this?" | APIs, schemas, edge cases defined | "TBD by engineering" |
| Hypothesis Rigor | "How do we know it worked?" | Metric + threshold + timeline | "Improve engagement" |
| Scope & Constraints | "What are we NOT doing?" | Explicit non-goals + priorities | Everything is P1 |
| Future Reader | "Will this make sense later?" | Self-contained + durable refs | Slack links + jargon |

---

## Common Anti-Patterns

### Context Anti-Patterns
- **Solution-as-problem**: "Problem: We need to build a dashboard" (that's a solution)
- **Missing adversary**: No explanation of what happens if we don't act
- **Amnesia**: No mention of previous attempts or related work

### Technical Anti-Patterns
- **Magic wand**: "AI will handle this" without detail
- **Copy-paste optimism**: Assuming another team's solution applies directly
- **Performance afterthought**: No scale or latency requirements

### Measurement Anti-Patterns
- **Vanity metrics**: Measuring activity instead of outcomes
- **Moving goalposts**: Success criteria defined after launch
- **Metric soup**: Too many metrics, unclear which matter most

### Scope Anti-Patterns
- **Non-goals as goals**: "Non-goal: Make it fast" (that's a constraint)
- **Priority inflation**: Everything is P1/critical/must-have
- **Invisible dependencies**: Assuming other teams will deliver without coordination

### Future Reader Anti-Patterns
- **Ephemeral evidence**: Key decisions documented only in Slack
- **Acronym soup**: ACME, QRT, and LMNO without definition
- **Time bombs**: "As discussed in yesterday's meeting" without summary
