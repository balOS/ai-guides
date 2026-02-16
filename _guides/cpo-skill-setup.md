---
layout: guide
title: "Chief Product Officer Skill"
icon: "🎯"
description: "Build a Chief Product Officer skill for Claude Code. Template-ready SKILL.md based on production patterns from Factory.ai and open-source PM frameworks."
date: 2026-02-15
author: "Human Agency"
permalink: /guides/cpo-skill/
guide_title: "Build a Chief Product Officer Skill for Claude Code"
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
    title: "CPO Skill Template"
  - id: "customize"
    icon: "04"
    title: "Customization"
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

## Chief Product Officer SKILL.md Template

Copy this template and customize it for your organization. Replace the placeholder URLs and company-specific references with your own.

```markdown
---
name: chief-product-officer
description: >
  Chief Product Officer assistant. Use when working on PRDs, product specs,
  design documents, feature prioritization, roadmap planning, product strategy,
  or any product management work. Provides access to product principles,
  frameworks, templates, and organizational context.
---

# Skill: Chief Product Officer

## Purpose

Serve as a product leadership assistant by providing access to foundational
product documents, strategic frameworks, and organizational context. This
skill ensures all product work aligns with established principles and uses
the latest source-of-truth documents.

## When to use this skill

- Writing or reviewing PRDs and product specs
- Working on design documents or technical specs
- Discussing feature prioritization or trade-offs
- Planning roadmaps or quarterly objectives
- Evaluating product strategy or positioning
- Reviewing product metrics or KPIs
- Understanding team structure, pod ownership, or areas of responsibility
- Referencing product principles, vision, or positioning
- Creating go-to-market or launch plans

## Source of Truth Documents

**IMPORTANT**: Always fetch these documents to get the latest content.
These are the authoritative sources for all product work.

### Product Vision & Strategy

1. **Product Vision** -- Our north star and long-term product direction
   [URL to your product vision doc]

2. **Product Principles** -- Foundational beliefs that guide how we build
   [URL to your product principles doc]

3. **Value Proposition** -- What we uniquely offer and why customers choose us
   [URL to your value proposition doc]

4. **Product Positioning** -- How we position in the market vs. alternatives
   [URL to your positioning doc]

### Frameworks & Process

5. **Prioritization Framework** -- How we decide what to build and in what order
   [URL to your prioritization framework]

6. **Product Development Process** -- How we go from idea to shipped feature
   [URL to your dev process doc]

7. **Launch Playbook** -- Standard process for shipping and GTM
   [URL to your launch playbook]

### Templates

8. **PRD Template** -- Standard template for product requirements documents
   [URL to your PRD template]

9. **Design Doc Template** -- Template for technical/UX design documents
   [URL to your design doc template]

10. **Product Brief Template** -- Lightweight brief for smaller initiatives
    [URL to your product brief template]

### Current Plans & Context

11. **Current Quarterly Plan** -- Active quarter's goals, ownership, and key results
    [URL to your quarterly plan]

12. **Team & Pod Structure** -- Current team organization, pod ownership areas
    [URL to your team structure doc]

13. **Product Metrics Dashboard** -- Key metrics and how we measure success
    [URL to your metrics dashboard]

## Required Behavior

1. **Fetch live documents**: When working on product tasks, use FetchUrl
   to pull the relevant source docs listed above. These are the source of
   truth and may be updated at any time.

2. **Align with principles**: All product work must reflect the Product
   Principles and Value Proposition. Flag any conflicts.

3. **Use templates**: When creating PRDs or design docs, follow the
   corresponding template structure. Do not invent new formats.

4. **Check ownership**: Reference the quarterly plan and team structure
   to understand who owns what before making recommendations.

5. **Stay current**: Plans, metrics, and team structure change frequently.
   Always fetch fresh content rather than relying on cached knowledge.

6. **Apply the prioritization framework**: When discussing what to build
   or trade-offs, apply the established prioritization framework rather
   than ad-hoc reasoning.

7. **Cite sources**: When referencing a principle, metric, or decision,
   note which source document it comes from.

## Workflow

When asked to help with product work:

1. Identify which source documents are relevant to the task
2. Fetch those documents using FetchUrl
3. Apply the context from those documents to the work at hand
4. For PRDs, follow the PRD Template structure
5. For prioritization, apply the Prioritization Framework
6. For strategy questions, ground answers in the Vision and Positioning docs
7. Flag any conflicts between the request and established principles
```

</section>

<section id="customize">

## Customization Guide

### Step 1: Replace document URLs

The template has placeholder `[URL to your ...]` entries. Replace these with actual URLs to your docs. Supported sources:

| Platform | URL Format | Notes |
|----------|-----------|-------|
| **Notion** | `https://www.notion.so/your-workspace/Page-Name-abc123` | Claude can fetch public or shared Notion pages |
| **Confluence** | `https://your-company.atlassian.net/wiki/spaces/PROD/pages/123` | Requires accessible URLs |
| **Google Docs** | `https://docs.google.com/document/d/DOC_ID/edit` | Must be viewable via link |
| **GitHub** | `https://github.com/org/repo/blob/main/docs/principles.md` | Raw URLs work best |

### Step 2: Adjust sections to match your org

Not every organization has all 13 document types. Remove what you don't have and add what you do. Common additions:

- **Customer Personas** -- If you maintain persona docs
- **Competitive Landscape** -- If you have a competitive intel doc
- **Technical Architecture** -- If PMs need to reference system design
- **User Research Repository** -- If you maintain a research library
- **OKR Tracking** -- If you use OKRs instead of quarterly plans

### Step 3: Tune the required behaviors

The "Required Behavior" section is where you encode your team's norms. Examples:

- If your team uses RICE scoring: *"Apply RICE scoring (Reach, Impact, Confidence, Effort) when evaluating feature requests"*
- If you have a specific review process: *"All PRDs must include a section for eng lead review comments"*
- If you use specific metrics: *"Reference NPS, activation rate, and weekly active users as the core health metrics"*

### Step 4: Install the skill

**Global (all projects):**
```bash
mkdir -p ~/.claude/skills/chief-product-officer
cp SKILL.md ~/.claude/skills/chief-product-officer/SKILL.md
```

**Per-project:**
```bash
mkdir -p .claude/skills/chief-product-officer
cp SKILL.md .claude/skills/chief-product-officer/SKILL.md
```

### Step 5: Test it

Open Claude Code and try:
- "Write a PRD for [feature]"
- "How should we prioritize [feature A] vs [feature B]?"
- "What does our product vision say about [topic]?"

Claude should automatically load the skill and fetch your source documents.

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
