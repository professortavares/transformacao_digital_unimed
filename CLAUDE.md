# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Course material in Brazilian Portuguese for a digital transformation course aimed at healthcare managers. It is Markdown lessons plus one agent-skill package built around fictitious outpatient (ambulatório) data. There is no application code, package manifest, build, linter, or test suite, so there are no build/lint/test commands to run.

## Layout and how the pieces connect

- `01_introdução/` — three lessons on prompting for managers, meant to be read in order: 01 (generic vs. contextualized prompts; "IA apoia ≠ IA decide"), 02 (zero/one/few-shot, chain-of-thought as auditable reasoning, prompt chaining, copy-paste prompts), 03 (RTF, TAG, RISE, CO-STAR, CARE, BAB frameworks, and metaprompting).
- `02_agentes/` — the agents-and-skills module (Módulo 4), which ties together four files:
  - `01_agentes_e_skills.md` — the lesson script. It separates prompt, agent, agent instructions, knowledge, skill, and tool, and gives the instructions text to paste into a Microsoft 365 Copilot agent.
  - `SKILL.md` + `referencias/criterios.md` — the skill itself (`analise-indicadores-ambulatoriais`). Given monthly indicators, it validates input, computes changes, separates facts from hypotheses, and returns a fixed seven-section output with a summary of at most 120 words.
  - `skill_analise_indicadores_ambulatoriais.zip` — the upload package for the skill. It must hold `SKILL.md` at its root and `referencias/` beside it.
  - `dados_ficticios_ambulatorio.csv` — the Jan–Apr fictitious dataset used across the lessons and the skill's activation test.
- `03_avançado/` — hands-on Microsoft 365 Copilot labs (Excel, Word, PowerPoint) around a separate fictitious case, "Centro de Especialidades Horizonte". It has its own files: the lab script `01_copilot_avançado.md`, the workbook `indicadores_ambulatoriais_ficticios.xlsx`, and the report template `modelo_contingencia_relatorio_executivo.docx`.

- `04_avaliação_llm/` — LLM-as-a-Judge oficina (Módulo 6): the roteiro `01_llm_as_a_judge_copilot.md` plus `materiais/` (the case with Respostas A, B and C, two judge prompts, a human evaluation sheet, and the professor's answer key, `gabarito_professor.md`).

The Jan–Apr dataset appears in the CSV, in the lesson tables, and in the RISE example in `03-frameworks…md`. If you change figures in one place, check the others. The Horizonte case in `03_avançado/` is a different dataset; don't mix the two.

## Conventions to keep

- **Keep the zip in sync.** The zip and the loose `SKILL.md`/`criterios.md` have the same text; they differ only in line endings. After editing either loose file, rebuild the zip, or the uploadable skill will drift from the documented one.
- **Percentage changes:** for metrics already in %, report the absolute difference in percentage points (p.p.), not a relative %. Relative % only when the initial value is nonzero and units are comparable. The skill, its reference file, and `03_avançado/01_copilot_avançado.md` all state this rule.
- **No causal claims from short series.** Lesson examples such as "a espera aumentou porque faltam médicos" are adversarial tests the material is designed to refuse, not recommendations to repeat.
- **Fictitious data only.** The skill and agent instructions forbid patient identifiers and individual clinical decisions. New examples must stay fictitious.
- **Language:** lesson content, skill output, and sample data are in Portuguese (pt-BR, with `1.100` thousands separators and `4,0` decimals in prose). The CSV uses unaccented `Marco` and plain `4.0` decimals. Match the language of the file you are editing.
- **Module numbering follows the folders:** `01_introdução/` = Módulos 1–3, `02_agentes/` = Módulo 4, `03_avançado/` = Módulo 5, `04_avaliação_llm/` = Módulo 6. Keep headings in that order if a module is added or moved.
- **Lesson structure.** The lessons in `01_introdução/`, `02_agentes/` and `04_avaliação_llm/` open with objetivos, preparação and an approximate cronograma, and close with Síntese and Fechamento. `03_avançado/` follows its own layout (proposta pedagógica, then labs with timed steps). Keep the pattern of the folder you are editing.
- **Judge prompts are duplicated.** The inline prompts in `04_avaliação_llm/01_llm_as_a_judge_copilot.md` (Bloco 4) are shorter or differently ordered versions of `materiais/prompt_juiz_absoluto.md` and `materiais/prompt_juiz_comparativo.md`. When you change one, update the other so the class gets the same rubric everywhere.
- **Answer key in the repo.** `materiais/gabarito_professor.md` is marked "NÃO DISTRIBUIR ANTES DA OFICINA" and is committed alongside the student materials. Don't copy its verdicts into student-facing files.
- **Copy-paste blocks.** The ```text blocks are prompts and agent instructions that participants copy. Don't change them as a side effect of formatting work. Where a lesson gives an expected result, such as the classification reference table in `02-prompt-engineering.md`, keep it consistent with the definitions in the prompt above it.
