---
name: analise-indicadores-ambulatoriais
description: >-
  Analisa indicadores mensais fictícios de ambulatório, confere cálculos,
  separa fatos de hipóteses e produz uma nota executiva padronizada para gestores.
  Use quando o usuário fornecer uma série temporal de indicadores ambulatoriais.
---

# Skill: Análise de indicadores ambulatoriais

## Objetivo

Produzir uma análise descritiva, verificável e padronizada de indicadores mensais
fictícios de gestão ambulatorial. Não inferir causas sem evidências e não realizar
decisões clínicas individuais.

## Entradas

Tabela ou CSV com período, volume de consultas, espera média, absenteísmo e/ou glosas.
Aceitar subconjuntos desses indicadores, mas sinalizar ausências e inconsistências.

## Procedimento obrigatório

1. **Validar entrada:** identificar meses, unidades, percentuais, valores faltantes,
   indicadores sem definição e dados inconsistentes. Pedir esclarecimentos quando
   informações essenciais não estiverem disponíveis.
2. **Calcular mudanças:** apresentar valores inicial e final, diferença absoluta,
   diferença relativa em porcentagem quando matematicamente definida. Para medidas
   já percentuais, a diferença absoluta deve ser em pontos percentuais (p.p.).
   Não confundir pontos percentuais com variação percentual relativa.
3. **Descrever tendências:** afirmar apenas o que é sustentado pelos números.
4. **Distinguir fatos e hipóteses:** etiquetar explicitamente cada hipótese como
   hipótese não confirmada. Nunca tratar variação conjunta como relação causal.
5. **Propor investigação:** sugerir dados adicionais, verificações e perguntas
   gerenciais plausíveis, sem inventar capacidade, custos, metas ou impactos.
6. **Redigir nota executiva:** manter tom conciso e não dramatizar resultados.

## Formato de saída

1. **Qualidade dos dados:** alertas, definições e lacunas.
2. **Resumo executivo:** até 120 palavras.
3. **Tabela de variações:** indicador, período inicial/final, mudança absoluta,
   variação relativa (quando aplicável) e interpretação.
4. **Fatos observados.**
5. **Hipóteses que precisam ser testadas.**
6. **Dados adicionais e próximos passos.**
7. **Limitações e pontos para validação humana.**

## Regras de segurança

- Trabalhar exclusivamente com dados fictícios ou autorizados para o ambiente.
- Não solicitar identificação de pacientes nem dados pessoais sensíveis.
- Não inventar fontes, normas, metas, valores ou resultados financeiros.
- Indicar a necessidade de validação por gestores, área assistencial e controles
  institucionais antes de decisões reais.
- Se houver conflito entre a solicitação e essas regras, explicar o limite e
  oferecer uma análise gerencial segura.

## Referência adicional

Consultar `referencias/criterios.md` para definições operacionais didáticas.
