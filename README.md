# PRD Review Skill for Claude Code

A Claude Code skill that reviews Product Requirement Documents (PRDs) for completeness, clarity, and rigor.

## Philosophy

PRDs are **context artifacts** - they exist to explain "why" decisions were made, enabling future readers to understand the reasoning without talking to the original author.

## Installation

Copy the skill to your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills/review-prd
cp -r . ~/.claude/skills/review-prd/
```

## Usage

Invoke the skill by saying:
- "Review this PRD" + paste content
- "Check my product spec at /path/to/prd.md"
- "Evaluate this requirements doc"
- `/review-prd`

### Supported Input Formats
- File paths (`.md`, `.txt`, `.docx`, `.pdf`)
- Pasted text
- Google Docs URLs

## Evaluation Framework

The skill evaluates PRDs across 5 dimensions:

| Dimension | What It Checks |
|-----------|----------------|
| **Context & Why** | Problem statement, historical context, hypotheses, "why now" |
| **Technical Depth** | APIs, data models, edge cases, performance requirements |
| **Hypothesis Rigor** | Metrics, success thresholds, timelines, confounds |
| **Scope & Constraints** | Goals, non-goals, priorities, risks, dependencies |
| **Future Reader Test** | Self-contained, jargon explained, durable references |

Each dimension is scored:
- 🟢 **Strong** - Meets best practices
- 🟡 **Adequate** - Acceptable but could improve
- 🔴 **Needs Work** - Missing critical elements

## Output

The skill generates a structured review with:
- Overall assessment
- Section-by-section scores
- Specific issues with actionable recommendations
- Questions for the PM to consider
- Prioritized next steps

## Files

```
review-prd/
├── SKILL.md                    # Main skill definition
├── README.md                   # This file
└── references/
    └── evaluation-rubric.md    # Detailed scoring criteria
```

## License

MIT
