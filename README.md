# Design Director

**[English](README.md) | [中文](README.zh-CN.md)**

An interview-first, full-spectrum design director skill for AI coding agents. Before any pixel is drawn, it interrogates your preferences (deliverable, audience, rebellion level, references, constraints), locks a **Design Read**, then routes execution across **22 style cards** and **7 cross-cutting treatments** — covering websites and every kind of printed matter (lecture notes, books, posters, flyers, covers, certificates).

> The 2026 shift: from "designed to look pretty" to "designed to have character."
> A style is **embodied, never labeled**.

---

## Why this exists

Most AI-generated design collapses into the same mean: purple gradients, rounded cards, centered heroes, emoji icons. Meanwhile real design in 2025–2026 is actively rebelling against the polished SaaS template — brutalism, zines, acid graphics, analog textures, notes-app chic.

This skill gives an agent two things it usually lacks:

1. **A real style vocabulary** — concrete tokens (hex, type pairings, layout grammar, print specs) for the whole spectrum from Swiss restraint to pure brutalism, not just the adjective "minimalist."
2. **Discipline** — hard rules that stop the three classic failure modes (below) before aesthetics even enter the picture.

## The three iron rules (before any aesthetics)

1. **Anti prompt-echo.** Your prompt is *private design direction, not page content*. "Futuristic" does not justify printing "FUTURE" on the page; "scientific" does not justify fake formulas. Every visible string passes a necessity test and a deletion test.
2. **Anti overcompensation ("此地无银三百两").** The style's name never appears inside the design. One loud move per canvas — the other 90% stays disciplined. Human traces (handwriting, tape, stains) must be sparse (≤20% of elements), asymmetric, and motivated; uniformly applied imperfection reads as fake. Anti-slop itself must not be performed.
3. **Anti AI-slop.** No hierarchy, no specificity, no restraint, no opinion — the four root causes, each with a countermeasure. Purple-blue gradients, Inter-as-default, three-equal-card rows: banned by default.

## How it works

```text
interview (≤2 AskUserQuestion rounds, with ASCII style previews)
   │  or: full-delegation path ("you decide") via scene defaults table
   ▼
Design Read — frozen one-paragraph spec:
   style × treatments (≤2) · rebellion level · the ONE loud move · color/type tokens
   ▼
execution routing:
   web      → delegates engineering rules to a frontend-taste skill
   print    → evidence-based pipeline (this repo, references/print-pipeline.md)
   image-gen → per-card English prompt blocks
   ▼
quality gate: prompt-echo scan · overcompensation scan · style-loyalty scan ·
              slop scan · print checks · judge visual acceptance
```

## The style spectrum

**Order axis (base styles — pick exactly one):**

| Card | Style | Rebellion |
|---|---|---|
| S01 | Swiss / International | ★ |
| S02 | Editorial | ★★ |
| S03 | Luxury Minimalism | ★ |
| S04 | Bold Minimalism | ★★ |
| S05 | Bento UI | ★ |
| S06 | Glassmorphism | ★ |
| S07 | Neo Futurism | ★★★ |
| S08 | Professor-minimal lecture notes | ★ |
| S09 | British book typography (Oxford/Penguin) | ★ |
| S10 | Digital textbook / Documentation | ★ |
| R01 | Experimental Swiss / Swiss Punk | ★★★ |
| R02 | Maximalism | ★★★ |
| R03 | Neo-Brutalism | ★★★★ |
| R04 | Brutalism | ★★★★★ |
| R05 | Anti-Design | ★★★★★ |
| R06 | Ugly Minimalism | ★★★★ |
| R07 | Zine / Punk | ★★★★★ |
| R08 | Grunge | ★★★★ |
| R09 | Y2K / Cyber Y2K | ★★★ |
| R10 | Acid Graphics | ★★★★★ |
| R11 | Cyberpunk | ★★★ |
| R12 | Retro-Futurism | ★★★ |

**Cross-cutting treatments (stack 0–2, must differ in kind from the base):**

T01 Analog × Digital · T02 Texture/Tactile · T03 Kinetic Typography · T04 Experimental Typography · T05 Reality Warp · T06 Digital Scrapbook · T07 Notes App Chic

Every card carries: essence / visual signature (hex + font tokens, Latin & CJK) / layout grammar / web notes / print notes / image-gen keywords / **failure modes (the style's overcompensation checklist)** / compatible pairings.

## Evidence-based print pipeline

`references/print-pipeline.md` is distilled from two shipped projects, not theory:

- a **108-page B5 textbook** built with markdown → HTML → Paged.js → headless Chrome → pymupdf merge → ghostscript font-outlining (all pages passed parallel visual review), and
- an **A4 Swiss-editorial poster** (single-file HTML at 96dpi, `assets/poster-template.html` — a validated skeleton you can copy and recolor via three CSS variables).

It includes the pitfall record: mirror page numbers must be injected into the body document only, front matter must occupy an even page count, cross-page table headers need a Paged.js handler, figcaption anti-hyphenation via flex-wrap, `print-color-adjust: exact`, Wikimedia Commons URL quirks and attribution manifests, and the ghostscript `-dNoOutputFonts` command (never `-dPDFSETTINGS`).

## Repository structure

```text
design-director/
├── SKILL.md                     # protocol: iron rules, interview, routing, quality gate
├── README.md / README.zh-CN.md  # you are here
├── references/
│   ├── styles-calm.md           # S01–S10 order-axis style cards
│   ├── styles-rebel.md          # R01–R12 rebellion-axis style cards
│   ├── treatments.md            # T01–T07 cross-cutting treatments + conflict table
│   └── print-pipeline.md        # evidence-based print engineering
└── assets/
    └── poster-template.html     # validated A4 Swiss editorial poster skeleton
```

## Dependencies (required)

This skill is a director, not a monolith — it deliberately delegates. **Three skills must be installed alongside it** (same skills directory), or the corresponding capabilities are missing:

| Skill | Level | What it powers | Without it |
|---|---|---|---|
| `design-taste-frontend` | **Required** | All web engineering rules for the execution phase: dial system, typography discipline, pre-flight checklist, performance & accessibility | Web projects get style tokens but no engineering guardrails |
| `anti-ai-slop` | **Required** | The full anti-slop checklist and countermeasures behind iron rule #3 | Anti-slop rule is reduced to a summary, no judgement criteria |
| `anti-prompt-echo` | **Required** | The full test procedures behind iron rule #1 (necessity test, deletion test) | Prompt-echo scans run on intuition and miss cases |
| `gov-admin-ui` | Optional | Routing target for Chinese government/institutional portal projects | Only that project type is affected |
| `minimal-zine-poster` | Optional | Prompt compiler for pure image-generation posters | Only that deliverable type is affected |

The interview protocol, style cards, and print pipeline in this repo are self-contained. The required trio powers the web execution path and the full quality gate; if one is missing, install it before running that path — never reconstruct its rules from memory.

## Installation

Any agent that loads markdown skills (Claude Code, ZCode, and similar):

```bash
git clone https://github.com/Cetirzine/design-director.git \
  ~/.zcode/skills/design-director        # or your agent's skills directory
```

Then obtain the three required skills (`design-taste-frontend`, `anti-ai-slop`, `anti-prompt-echo`) from their own sources and place them as sibling directories (`~/.zcode/skills/<name>/`). The final layout should read:

```text
~/.zcode/skills/
├── design-director/          # this repo
├── design-taste-frontend/    # required
├── anti-ai-slop/             # required
└── anti-prompt-echo/         # required
```

## Credit

Operates as a layer over a working installation of `design-taste-frontend`, `anti-ai-slop`, `anti-prompt-echo`, `gov-admin-ui`, and `minimal-zine-poster` (see Dependencies) — this skill handles direction and routing and deliberately delegates rather than duplicates them.
