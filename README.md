# Transformacao digital unimed

Material para o curso de transformação digital, voltado a gestores de saúde. Reúne aulas sobre o uso de IA generativa na gestão e um exemplo prático de agente e skill para análise de indicadores ambulatoriais.

Todos os dados utilizados são **fictícios**.

## Conteúdo

### `01_introdução/` — Como conversar com a IA

Três módulos, na ordem:

1. **A IA consegue realmente ajudar um gestor?** Compara um pedido genérico com um pedido contextualizado.
2. **Como conversar com a IA de maneira eficiente.** Técnicas de prompting (zero-shot, few-shot, raciocínio estruturado, encadeamento de tarefas) com prompts prontos para copiar.
3. **Frameworks e melhoria de prompts.** RTF, TAG, RISE, CO-STAR, CARE e BAB, além de metaprompting.

### `02_agentes/` — Agentes e skills (Módulo 4)

- `01_agentes_e_skills.md`: roteiro da aula sobre a diferença entre prompt, agente, instruções, conhecimento, skill e ferramenta, com demonstração no Microsoft 365 Copilot.
- `SKILL.md` e `referencias/criterios.md`: a skill `analise-indicadores-ambulatoriais`, que analisa indicadores mensais, calcula variações, separa fatos de hipóteses e produz uma nota executiva.
- `skill_analise_indicadores_ambulatoriais.zip`: pacote para carregar a skill em uma plataforma que aceite esse formato. Contém `SKILL.md` e `referencias/`.
- `dados_ficticios_ambulatorio.csv`: série mensal fictícia (janeiro a abril) usada nos exemplos e nos testes.

Ao alterar `SKILL.md` ou `referencias/criterios.md`, gere novamente o ZIP para que ele reflita a versão atual.

## Uso em sala

- Os nomes de botões e menus das plataformas de IA podem mudar conforme a versão, o idioma e a licença. Valide a interface antes da aula.
- Não conecte fontes de dados reais sem autorização. Use apenas o material sintético.
- Cada módulo começa com objetivos de aprendizagem, preparação e um cronograma sugerido. Os tempos são estimativas e podem ser ajustados à turma.

## Licença

Distribuído sob a [licença MIT](LICENSE). Copyright (c) 2026 Prof. Tavares.
