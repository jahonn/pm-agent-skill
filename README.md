# PM Agent Skill

4-agent product management workflow covering the full PM lifecycle: **Research → Define → Validate → Launch**. Built on 7 proven frameworks including JTBD, Opportunity Solution Tree, Amazon Working Backwards, and Lean Startup.

Works with any [Agent Skills](https://agentskills.io) compatible tool: Claude Code, OpenAI Codex, Trae, Cursor, Gemini CLI, and more.

## What This Is

Every PM tool does one thing well: ChatPRD writes PRDs, Dovetail does research, Linear tracks tasks. But nobody connects them. You still manually shuttle context between tools.

This skill gives you a **complete PM workflow as AI subagents** — each phase produces a structured artifact that feeds the next. One problem statement in, full product plan out.

## Phases

| # | Phase | Agent Does | Framework | Output |
|---|-------|-----------|-----------|--------|
| 1 | **Research** | JTBD analysis, competitor map, market sizing, personas | JTBD + Design Thinking | `DISCOVERY.md` |
| 2 | **Define** | Opportunity tree, RICE scoring, Amazon PRD, user stories | Opp. Tree + Amazon Working Backwards | `PRD.md` |
| 3 | **Validate** | Assumption mapping, experiment design, prototype plan | Design Sprint + Lean BML | `EXPERIMENT.md` |
| 4 | **Launch** | GTM strategy, OKRs, release checklist, feedback loop | Dual-Track Agile + OKR | `GTM.md` |

## Install

### Via npm
```bash
npm install -g @jahonn/agentskills-cli
agentskills install ./pm-agent-skill -t all
```

### Via ClawHub (OpenClaw)
```bash
clawhub install ai-pm-agent
```

### Manual
```bash
cp -r pm-agent-skill ~/.claude/skills/pm-agent
```

## Usage

### Full workflow
```
"I want to build an app that does X" → runs all 4 phases
"Run pm-agent on [problem statement]"
```

### Single phase
```
"/research [product idea]"
"/define [research findings]"
"/validate [PRD]"
"/launch [validated product]"
```

### Partial workflow
```
"Just do a competitor analysis" → Research only
"Help me prioritize my backlog" → Define (RICE section)
"Write a PRD for this feature" → Define with feature description
```

## Example

**Input:**
> Small business owners struggle to track invoices across multiple payment platforms, leading to cash flow blind spots.

**Output (4 phases, ~20 min):**
1. `DISCOVERY.md` — JTBD analysis, 3 competitors mapped, TAM/SAM/SOM, 2 personas
2. `PRD.md` — Opportunity tree with 5 opportunities, RICE scored, press release + FAQ, 8 user stories
3. `EXPERIMENT.md` — 3 riskiest assumptions identified, Lean BML experiments with pass/fail criteria
4. `GTM.md` — ICP, positioning statement, 90-day OKRs, release checklist

## Frameworks Used

| Framework | Phase | What It Does |
|-----------|-------|-------------|
| **Jobs-to-be-Done** | Research | Understand what "job" users hire the product for |
| **Design Thinking** | Research | Empathize → Define → Ideate framework |
| **Opportunity Solution Tree** | Define | Map outcomes → opportunities → solutions |
| **RICE Scoring** | Define | Prioritize by Reach × Impact × Confidence / Effort |
| **Kano Model** | Define | Classify features: must-have / performance / delighter |
| **Amazon Working Backwards** | Define | Write press release before PRD |
| **Design Sprint** | Validate | 5-day prototype testing methodology |
| **Lean Startup BML** | Validate | Build → Measure → Learn experiment cycles |
| **Dual-Track Agile** | Launch | Discovery + Delivery running in parallel |
| **OKR** | Launch | Objectives and Key Results for 90-day sprints |

## Human-in-the-Loop

Each phase ends with a checkpoint:
- **Approve** — proceed as-is
- **Edit** — modify the artifact, then continue
- **Rerun** — provide feedback, regenerate

AI drafts. Humans decide.

## Related

- [Dev Workflow Skill](https://github.com/jahonn/dev-workflow-skill) — development sprint workflow
- [Agent Skills Spec](https://agentskills.io/specification) — the open standard
- [Convoke Agents](https://github.com/amalik/convoke-agents) — 7-agent product discovery (inspiration)

## License

MIT
