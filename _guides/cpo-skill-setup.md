---
layout: guide
title: "Chief Product Officer Skill"
icon: "🎯"
description: "Human Agency's Chief Product Officer skill for Claude Code. Production-ready SKILL.md with document creation backlog, based on Factory.ai's pattern and open-source PM frameworks."
date: 2026-02-15
author: "Human Agency"
permalink: /guides/cpo-skill/
guide_title: "Chief Product Officer Skill for Human Agency"
sources:
  - name: "Carl Vellotti / Factory.ai"
    url: "https://www.youtube.com/watch?v=j7CaMx2c56M"
  - name: "product-on-purpose/pm-skills"
    url: "https://github.com/product-on-purpose/pm-skills"
  - name: "deanpeters/Product-Manager-Skills"
    url: "https://github.com/deanpeters/Product-Manager-Skills"
sections:
  - id: "overview"
    icon: "01"
    title: "Overview"
  - id: "reference"
    icon: "02"
    title: "Reference Pattern"
  - id: "template"
    icon: "03"
    title: "CPO Skill (Human Agency)"
  - id: "backlog"
    icon: "04"
    title: "Document Backlog"
  - id: "resources"
    icon: "05"
    title: "Resources"
---

<section id="overview">

## What is a CPO Skill?

A **SKILL.md** file teaches Claude Code how to perform a specific domain task. When placed in your project's `.claude/skills/` directory (or `~/.claude/skills/` for global access), Claude automatically loads it when relevant work is detected.

A **Chief Product Officer skill** gives Claude deep context on your product organization: your principles, how you prioritize, your PRD templates, team structure, and source-of-truth documents. Instead of re-explaining your product philosophy every session, the skill file does it for you.

### Why build one?

- **Consistency** -- Every PRD, spec, and prioritization discussion aligns with your actual frameworks
- **Speed** -- Claude fetches your live Notion/Confluence docs instead of working from stale context
- **Onboarding** -- New team members get your full product philosophy baked into their AI assistant
- **Institutional knowledge** -- Your product culture persists across sessions and team members

### How skills work

```
~/.claude/skills/
  chief-product-officer/
    SKILL.md              <- Auto-loaded by Claude Code
```

Or per-project:

```
your-repo/.claude/skills/
  chief-product-officer/
    SKILL.md
```

Claude reads the skill's frontmatter (`name`, `description`) to decide when to activate it. When it matches, the full skill content is loaded as context.

</section>

<section id="reference">

## Reference: Factory.ai's Production PM Skill

This pattern comes from **Eno Reyes at Factory.ai**, demonstrated in [Carl Vellotti's "8 Months of Claude Code Lessons"](https://www.youtube.com/watch?v=j7CaMx2c56M) at the 19-23 minute mark. This is a real production skill used daily by Factory's product team.

### Structure breakdown

Factory's skill follows a five-part structure:

| Section | Purpose |
|---------|---------|
| **Frontmatter** | `name` and `description` for auto-detection |
| **Purpose** | One-paragraph explanation of what the skill does |
| **When to use** | Trigger conditions (bullet list) |
| **Source of Truth Documents** | Live URLs to Notion docs, grouped by category |
| **Required Behavior** | Rules Claude must follow (fetch fresh, reference principles, use templates) |
| **Workflow** | Step-by-step process when the skill activates |

### Key design decisions

1. **External documents over embedded content** -- Factory links to Notion pages and tells Claude to `FetchUrl` them at runtime. This means the skill never goes stale.

2. **Grouped source docs** -- Documents are organized by function: Core Philosophy, How We Work, Templates & Plans. This helps Claude pick the right docs per task.

3. **Explicit behavioral rules** -- "Always fetch fresh content rather than relying on cached knowledge" prevents Claude from hallucinating outdated information.

4. **Numbered workflow** -- A clear 1-5 step process ensures Claude follows a consistent approach every time.

</section>

<section id="template">

## Human Agency CPO Skill

This is Human Agency's Chief Product Officer skill. Documents marked `TODO` need to be created -- see the **Document Backlog** section for best-practice specs on each.

Human Agency operates three pillars: **Creative Agency** (full-service marketing and brand), **AI Consulting** (business-first AI transformation, custom agent development), and **Ventures** (building and scaling companies like Formli). The CPO skill spans all three.

```markdown
---
name: chief-product-officer
description: >
  Chief Product Officer assistant for Human Agency. Use when working on
  PRDs, product specs, design documents, feature prioritization, roadmap
  planning, product strategy, client proposals, AI agent architecture,
  or any product management work across our three pillars: Creative
  Agency, AI Consulting, and Ventures. Provides access to Human Agency's
  product principles, frameworks, templates, and organizational context.
---

# Skill: Human Agency Chief Product Officer

## Purpose

Serve as a product leadership assistant for Human Agency by providing
access to our foundational product documents, strategic frameworks, and
organizational context. This skill ensures all product work -- whether
for client engagements, internal ventures, or AI consulting projects --
aligns with our mission of expanding human agency through technology,
consulting, and company-building.

## When to use this skill

- Writing or reviewing PRDs and product specs (internal or client)
- Scoping AI consulting engagements or agent architectures
- Working on design documents or technical specs
- Discussing feature prioritization or trade-offs
- Planning roadmaps or quarterly objectives
- Evaluating product strategy or market positioning
- Writing client proposals, SOWs, or engagement briefs
- Reviewing product metrics or KPIs
- Understanding team structure or ownership areas
- Referencing product principles, vision, or positioning
- Creating go-to-market or launch plans
- Planning venture builds or new product incubation
- Designing AI agents or automation workflows for clients

## Source of Truth Documents

**IMPORTANT**: Always fetch these documents to get the latest content.
These are the authoritative sources for all product work.

### Vision & Strategy

1. **Product Vision & Mission** -- Our north star: expanding human
   agency through AI consulting, creative services, and ventures
   TODO: Create document (see backlog)

2. **Product Principles** -- Foundational beliefs that guide how we
   build across all three pillars
   TODO: Create document (see backlog)

3. **Value Proposition** -- What Human Agency uniquely offers across
   consulting, creative, and ventures
   TODO: Create document (see backlog)

4. **Positioning & Competitive Landscape** -- How we position vs.
   other AI consultancies, creative agencies, and venture studios
   TODO: Create document (see backlog)

### Frameworks & Process

5. **Prioritization Framework** -- How we decide what to build, which
   clients to pursue, and which ventures to invest in
   TODO: Create document (see backlog)

6. **Product Development Process** -- How we go from idea to shipped
   feature across client work, ventures, and internal tools
   TODO: Create document (see backlog)

7. **AI Consulting Methodology** -- Our business-first approach:
   organizational interviews, gap analysis, agent design, deployment
   TODO: Create document (see backlog)

8. **Launch Playbook** -- Standard process for shipping features,
   client deliverables, and venture launches
   TODO: Create document (see backlog)

### Templates

9. **PRD Template** -- Standard template for product requirements
    documents at Human Agency
    TODO: Create document (see backlog)

10. **Client Proposal / SOW Template** -- Template for scoping and
    pricing consulting and creative engagements
    TODO: Create document (see backlog)

11. **AI Agent Design Template** -- Template for specifying custom
    AI agent architecture, data sources, and behavior
    TODO: Create document (see backlog)

12. **Product Brief Template** -- Lightweight brief for smaller
    initiatives and experiments
    TODO: Create document (see backlog)

### Current Plans & Context

13. **Current Quarterly Plan** -- Active quarter's goals, ownership
    areas, and key results across all pillars
    TODO: Create document (see backlog)

14. **Team & Ownership Structure** -- Current team organization and
    ownership areas across Creative, AI, and Ventures
    TODO: Create document (see backlog)

15. **Product Metrics Dashboard** -- Key metrics: client revenue,
    venture growth, AI engagement outcomes, NPS
    TODO: Create document (see backlog)

### Pillar Overviews

16. **Creative Agency** -- Service offerings, client engagement
    model, capabilities, and case study portfolio
    TODO: Create document (see backlog)

17. **AI Consulting** -- Methodology, agent development stack,
    client onboarding process, and delivery model
    TODO: Create document (see backlog)

18. **Ventures Portfolio** -- Active ventures (Formli, etc.),
    investment thesis, incubation process, and roadmaps
    TODO: Create document (see backlog)

## Required Behavior

1. **Fetch live documents**: When working on product tasks, use
   FetchUrl to pull the relevant source docs listed above. These are
   the source of truth and may be updated at any time.

2. **Align with principles**: All product work must reflect the
   Product Principles and Value Proposition. Flag any conflicts.

3. **Use templates**: When creating PRDs, proposals, or agent specs,
   follow the corresponding template structure. Do not invent formats.

4. **Check ownership**: Reference the quarterly plan and team
   structure to understand who owns what before making recommendations.

5. **Stay current**: Plans, metrics, and team structure change
   frequently. Always fetch fresh content rather than relying on
   cached knowledge.

6. **Apply the prioritization framework**: When discussing what to
   build or trade-offs, apply the established prioritization framework
   rather than ad-hoc reasoning.

7. **Cite sources**: When referencing a principle, metric, or
   decision, note which source document it comes from.

8. **Business-first for AI work**: Follow Human Agency's AI
   methodology -- start with organizational understanding and business
   challenges before recommending technology solutions.

9. **Cross-pillar awareness**: Work often spans multiple pillars
   (e.g., a client engagement may involve creative, AI, and a venture
   spinout). Always consider cross-pillar dependencies.

10. **Earned wisdom**: Leverage institutional knowledge from past
    engagements. Reference case studies and prior client work when
    relevant to current decisions.

## Workflow

When asked to help with product work:

1. Identify which source documents are relevant to the task
2. Fetch those documents using FetchUrl
3. Determine which pillar(s) the work touches (Creative, AI, Ventures)
4. Apply the context from those documents to the work at hand
5. For PRDs, follow the PRD Template structure
6. For client work, follow the Proposal/SOW Template
7. For AI agent design, follow the Agent Design Template
8. For prioritization, apply the Prioritization Framework
9. For strategy questions, ground answers in Vision and Positioning
10. Flag any conflicts between the request and established principles
11. Note cross-pillar dependencies that need coordination
```

### Installation

**Global (all projects):**
```bash
mkdir -p ~/.claude/skills/chief-product-officer
# Copy the skill content above into:
# ~/.claude/skills/chief-product-officer/SKILL.md
```

**Per-project:**
```bash
mkdir -p .claude/skills/chief-product-officer
# Copy the skill content above into:
# .claude/skills/chief-product-officer/SKILL.md
```

</section>

<section id="backlog">

## Document Creation Backlog

Each source document referenced in the skill needs to be created. Below is the backlog with best-practice specs for what each should contain, priority level, and guidance.

### P0 -- Create First (Skill is weak without these)

#### 1. Product Vision & Mission

**What it is**: A 1-2 page document that defines Human Agency's north star.

**Best practice -- should contain**:
- **Mission statement**: One sentence. Start from "You have a right to agency, we're here to advance it" and sharpen it for product decisions
- **Vision** (3-5 year): What the world looks like when people and organizations fully harness AI to expand their capabilities
- **Problem statement**: Why most organizations struggle to adopt AI effectively (tool-first thinking, no organizational understanding, generic solutions)
- **Three pillars**: How Creative, AI Consulting, and Ventures each advance the mission
- **What we are NOT**: Explicit boundaries -- e.g., we are not an outsourced dev shop, not a pure-play agency, not a VC fund

**Reference**: Gibson Biddle's DHM Model (Delight, Hard-to-copy, Margin-enhancing), Patagonia's mission statement as a model for mission-driven companies

---

#### 2. Product Principles

**What it is**: 5-10 decision-making heuristics that resolve ambiguity when building product.

**Best practice -- should contain**:
- **Each principle**: Short name + one-paragraph explanation + a concrete example of a decision it would resolve
- **Tensions**: Where principles might conflict and how to resolve
- **Anti-patterns**: What each principle explicitly rejects

**Example principles for Human Agency**:
- *Business first, technology second* -- Understand the organizational challenge deeply before recommending any AI solution. Never lead with tech.
- *Earned wisdom over generic advice* -- We interview people, map challenges, and build from an organization's actual strengths. No cookie-cutter playbooks.
- *Expand agency, don't replace it* -- AI should make humans more capable, not redundant. Design for augmentation.
- *Ship and learn* -- For ventures and internal tools, bias toward getting something live and iterating. For client work, set clear success criteria upfront.
- *Borderless by default* -- Build for distributed teams. No process should require physical co-location.

**Reference**: Factory.ai's Product Principles pattern, Stripe's operating principles, Basecamp's principles

---

#### 3. Value Proposition

**What it is**: A crisp articulation of what Human Agency offers that nobody else does.

**Best practice -- should contain**:
- **One-liner**: "Human Agency is [what] for [who] that [differentiator]"
- **Per-pillar value**: What each pillar uniquely offers
  - *Creative*: Full-service agency with AI-native workflows
  - *AI Consulting*: Business-first AI transformation that starts with organizational understanding, not tool demos
  - *Ventures*: Experienced builders who use technology to solve real-world problems (Formli, Detect, C16 Bio track record)
- **Client segments and JTBD**: What each segment (startups, enterprises, nonprofits, political orgs) is trying to accomplish
- **Why us vs. alternatives**: vs. Accenture/McKinsey (too expensive, too generic), vs. boutique AI shops (no creative/brand capability), vs. pure agencies (no AI depth), vs. venture studios (no consulting revenue to fund experiments)
- **Proof points**: UNHCR ($153K P2P raised), Harvard (40% bounce rate decrease, 5x page views), Detect (first PCR-quality home COVID test)

**Reference**: Strategyzer Value Proposition Canvas, JTBD framework

---

#### 4. PRD Template

**What it is**: A standard structure for every product requirements document at Human Agency.

**Best practice -- should contain these sections**:
- **Title & metadata** (author, status, reviewers, pillar: Creative/AI/Ventures)
- **Context** (is this client work, internal tooling, or a venture product?)
- **Problem statement** (who has the problem, evidence it exists)
- **Proposed solution** (what we're building, how it works)
- **Success metrics** (how we'll know it worked, with specific targets)
- **User stories / use cases**
- **Scope** (in scope, out of scope, future considerations)
- **Technical considerations** (dependencies, integrations, AI model requirements)
- **Launch plan** (rollout strategy, feature flags, monitoring)
- **Open questions**
- **Client alignment** (if client work: sign-off requirements, feedback loops)

**Reference**: Factory.ai's WIP PRD Template, Lenny's PRD template, Coda's PRD template

---

### P1 -- Create Next (Operational effectiveness)

#### 5. Prioritization Framework

**What it is**: How Human Agency decides what to build and in what order.

**Best practice -- should contain**:
- **Scoring model**: e.g., RICE (Reach, Impact, Confidence, Effort), ICE, or custom weighted scoring
- **Strategic alignment check**: Does this advance one of our three pillars?
- **Agency multiplier**: Does this expand human agency (the mission), or is it purely operational?
- **Cross-pillar leverage**: Features that serve multiple pillars get priority (e.g., an AI tool built for a client that becomes a venture product)
- **Decision log**: Template for recording prioritization decisions and rationale

**Recommendation**: Adapt RICE with an "A" (Agency) multiplier -- how directly this work expands human agency for our users/clients. RICE-A scoring.

---

#### 6. Positioning & Competitive Landscape

**What it is**: How Human Agency positions against alternatives in the market.

**Best practice -- should contain**:
- **Competitive landscape by pillar**:
  - *Creative*: vs. Huge, R/GA, Instrument, smaller boutiques
  - *AI Consulting*: vs. McKinsey/BCG AI practices, Palantir, smaller AI consultancies
  - *Ventures*: vs. Atomic, Pioneer Square Labs, High Alpha, other venture studios
- **Positioning statement**: Following April Dunford's "Obviously Awesome" framework
- **Unique intersection**: No competitor combines creative agency + AI consulting + venture building. This is the core differentiator.
- **Messaging hierarchy**: Per audience (startup founders, enterprise CDOs, nonprofit leaders)

**Reference**: April Dunford's "Obviously Awesome," Crossing the Chasm positioning

---

#### 7. Product Development Process

**What it is**: How a feature goes from idea to production at Human Agency.

**Best practice -- should contain**:
- **Stages**: Discovery, Definition, Design, Build, QA, Launch, Measure
- **Gate criteria**: What must be true to move between stages
- **Roles at each stage**: Who's responsible, accountable, consulted, informed (RACI)
- **Three tracks**: Different process for client deliverables vs. venture products vs. internal tools
- **Cadence**: Sprint length, planning rhythm, review cadence

---

#### 8. AI Consulting Methodology

**What it is**: Human Agency's business-first approach to AI transformation, codified.

**Best practice -- should contain**:
- **Phase 1: Discovery** -- Interview stakeholders across the organization, map challenges and strengths, identify "earned wisdom" worth preserving
- **Phase 2: Gap Analysis** -- AI readiness assessment, tool audit, capability mapping
- **Phase 3: Solution Design** -- Recommend existing tools or design custom AI agents, grounded in the organization's actual workflows
- **Phase 4: Build & Deploy** -- Agent development, integration, training (executives to analysts)
- **Phase 5: Measure & Iterate** -- Success metrics, adoption tracking, ongoing optimization
- **Principles**: Always start with people, not technology. Build on earned wisdom. Secure by default.

This is one of Human Agency's key differentiators -- codifying it makes it teachable and scalable.

---

#### 9. Client Proposal / SOW Template

**What it is**: Standard structure for scoping and pricing consulting and creative engagements.

**Best practice -- should contain**:
- **Client overview** (organization, key stakeholders, industry)
- **Problem / opportunity** (what the client is trying to achieve)
- **Proposed approach** (phases, deliverables per phase)
- **Scope & boundaries** (what's included, what's excluded)
- **Timeline** (milestones, dependencies)
- **Team** (who from Human Agency, roles, time commitment)
- **Investment** (pricing model: fixed, retainer, or hybrid)
- **Success criteria** (measurable outcomes tied to the client's goals)
- **Terms** (payment schedule, IP, confidentiality)

---

#### 10. Current Quarterly Plan

**What it is**: Living document for the active quarter's goals and ownership.

**Best practice -- should contain**:
- **Quarter theme/name** (like Factory's "The Droid Redemption")
- **Top 3-5 company objectives**
- **Per-pillar goals**: What Creative, AI, and Ventures are each shipping/delivering
- **Key results**: Measurable targets per goal
- **Ownership map**: Who owns what
- **Client pipeline**: Major engagements in flight
- **Dependencies and risks**

---

### P2 -- Create When Needed (Rounds out the system)

#### 11. AI Agent Design Template

**Best practice**: Template for specifying custom AI agents built for clients. Sections: agent purpose, persona/tone, data sources and connectors, tools/capabilities, guardrails and boundaries, testing plan, deployment environment, success metrics.

---

#### 12. Launch Playbook

**Best practice**: Checklist-driven. Sections for pre-launch (feature flags, monitoring, docs), launch day (rollout stages, war room), post-launch (metrics review, retro). Separate tracks for client launches vs. venture releases.

---

#### 13. Product Brief Template

**Best practice**: One-page format. Problem, hypothesis, proposed experiment, success criteria, effort estimate. Used for small bets and rapid experiments.

---

#### 14. Team & Ownership Structure

**Best practice**: Org chart with ownership areas mapped to pillars. Include: Creative team leads, AI consulting team (Managing Director of AI), Ventures leads, shared functions. Updated quarterly.

---

#### 15. Product Metrics Dashboard

**Best practice**: Define north star metrics per pillar:
- *Creative*: Client retention, NPS, revenue per engagement, campaign performance
- *AI Consulting*: Engagement outcomes, client adoption rates, time-to-value, expansion revenue
- *Ventures*: MRR, user growth, activation rates, burn rate per venture
- *Company-wide*: Total revenue, margin, team utilization, pipeline value

---

#### 16. Creative Agency Pillar Overview

**Best practice**: Service catalog (strategy, brand, content, web, performance marketing, data/insights), engagement model, case study portfolio (UNHCR, Harvard, Detect, C16 Bio), team capabilities.

---

#### 17. AI Consulting Pillar Overview

**Best practice**: Methodology summary, technology stack, agent development capabilities, client onboarding flow, training curriculum (executive to analyst), case studies.

---

#### 18. Ventures Portfolio Overview

**Best practice**: Active ventures (Formli, etc.), investment thesis, incubation process (idea to launch), success/failure criteria, spin-out model, current roadmaps.

---

### Backlog summary

| # | Document | Priority | Status |
|---|----------|----------|--------|
| 1 | Product Vision & Mission | **P0** | TODO |
| 2 | Product Principles | **P0** | TODO |
| 3 | Value Proposition | **P0** | TODO |
| 4 | PRD Template | **P0** | TODO |
| 5 | Prioritization Framework | **P1** | TODO |
| 6 | Positioning & Competitive Landscape | **P1** | TODO |
| 7 | Product Development Process | **P1** | TODO |
| 8 | AI Consulting Methodology | **P1** | TODO |
| 9 | Client Proposal / SOW Template | **P1** | TODO |
| 10 | Current Quarterly Plan | **P1** | TODO |
| 11 | AI Agent Design Template | **P2** | TODO |
| 12 | Launch Playbook | **P2** | TODO |
| 13 | Product Brief Template | **P2** | TODO |
| 14 | Team & Ownership Structure | **P2** | TODO |
| 15 | Product Metrics Dashboard | **P2** | TODO |
| 16 | Creative Agency Pillar Overview | **P2** | TODO |
| 17 | AI Consulting Pillar Overview | **P2** | TODO |
| 18 | Ventures Portfolio Overview | **P2** | TODO |

As each document is created, replace the `TODO: Create document (see backlog)` line in the skill with the actual URL.

</section>

<section id="resources">

## Open-Source PM Skills & Frameworks

### Ready-made skill collections

**[product-on-purpose/pm-skills](https://github.com/product-on-purpose/pm-skills)** -- 24 production-ready PM skills organized in a Triple Diamond Framework (Discover, Define, Develop, Deliver, Measure, Iterate). Apache 2.0 licensed. Each skill includes a SKILL.md, reference template, and example output. Install via slash commands, AGENTS.md, or MCP server.

**[deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills)** -- 42 PM frameworks in three tiers: Component (19 focused tools), Interactive (18 multi-step frameworks), and Workflow (5 comprehensive processes). CC BY-NC-SA 4.0. Includes shell utilities for creating and testing skills.

**[menkesu/awesome-pm-skills](https://github.com/menkesu/awesome-pm-skills)** -- 28 curated PM skills sourced from Lenny's Podcast top frameworks.

### Skill architecture patterns

From studying these repos, the most effective skills follow this pattern:

```
SKILL.md          <- Core skill definition (what you're building)
references/
  TEMPLATE.md     <- Output template for the skill
  EXAMPLE.md      <- Example of good output
```

The CPO skill above follows the single-file pattern (just SKILL.md) for simplicity. If you want Claude to produce more structured output, add a `references/` directory with templates and examples.

### Further reading

- [Claude Code Skills Documentation](https://docs.anthropic.com/en/docs/claude-code/skills) -- Official docs on skill files
- [Carl Vellotti's Claude Code for PMs Course](https://ccforpms.com) -- Free course on using Claude Code for product management
- [Aakash Gupta's Growth Podcast](https://www.youtube.com/watch?v=j7CaMx2c56M) -- "8 Months of Claude Code Lessons in 80 Minutes" featuring Factory.ai's PM setup

</section>
