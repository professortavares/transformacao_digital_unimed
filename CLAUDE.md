# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Course material in Brazilian Portuguese for a digital transformation course aimed at healthcare managers. It is Markdown lessons plus one agent-skill package built around fictitious outpatient (ambulatório) data. There is no application code, package manifest, build, linter, or test suite, so there are no build/lint/test commands to run.

## Layout and how the pieces connect

- `01_introdução/` — three lessons on prompting for managers, meant to be read in order: 01 (generic vs. contextualized prompts; "IA apoia ≠ IA decide"), 02 (zero/one/few-shot, chain-of-thought as auditable reasoning, prompt chaining, copy-paste prompts), 03 (RTF, TAG, RISE, CO-STAR, CARE, BAB frameworks, and metaprompting).
- `02_agentes/` — the agents-and-skills module, which ties together four files:
  - `01_agentes_e_skills.md` — the lesson script. It separates prompt, agent, agent instructions, knowledge, skill, and tool, and gives the instructions text to paste into a Microsoft 365 Copilot agent.
  - `SKILL.md` + `referencias/criterios.md` — the skill itself (`analise-indicadores-ambulatoriais`). Given monthly indicators, it validates input, computes changes, separates facts from hypotheses, and returns a fixed seven-section output with a summary of at most 120 words.
  - `skill_analise_indicadores_ambulatoriais.zip` — the upload package for the skill. It must hold `SKILL.md` at its root and `referencias/` beside it.
  - `dados_ficticios_ambulatorio.csv` — the Jan–Apr fictitious dataset used across the lessons and the skill's activation test.

The same four-month dataset appears in the CSV, in the lesson tables, and in the RISE example in `03-frameworks…md`. If you change figures in one place, check the others.

## Conventions to keep

- **Keep the zip in sync.** The zip and the loose `SKILL.md`/`criterios.md` are currently identical. After editing either loose file, rebuild the zip, or the uploadable skill will drift from the documented one.
- **Percentage changes:** for metrics already in %, report the absolute difference in percentage points (p.p.), not a relative %. Relative % only when the initial value is nonzero and units are comparable. The skill and the lessons both state this rule.
- **No causal claims from short series.** Lesson examples such as "a espera aumentou porque faltam médicos" are adversarial tests the material is designed to refuse, not recommendations to repeat.
- **Fictitious data only.** The skill and agent instructions forbid patient identifiers and individual clinical decisions. New examples must stay fictitious.
- **Language:** lesson content, skill output, and sample data are in Portuguese (pt-BR, with `1.100` thousands separators and `4,0` decimals in prose). The CSV uses unaccented `Marco` and plain `4.0` decimals. Match the language of the file you are editing.
- **Module numbering is inconsistent.** Both `01_introdução/` and `02_agentes/01_agentes_e_skills.md` are labelled "Módulo 1" in their headings. Don't rely on the labels to order content; use the folder and filename prefixes.
