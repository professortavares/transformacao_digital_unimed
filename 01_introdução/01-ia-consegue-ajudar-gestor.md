# Módulo 1 — A IA consegue realmente ajudar um gestor?

## Objetivos de aprendizagem

Ao final deste módulo, os participantes devem ser capazes de:

1. Observar como o contexto e a definição do pedido mudam a qualidade da resposta da IA.
2. Distinguir sugestão de recomendação validada.
3. Reconhecer que a decisão continua sendo humana.

## Preparação

- Abra duas conversas novas e separadas na ferramenta de IA.
- Use apenas dados fictícios.

## Cronograma (~25 min)

| Etapa | Tempo |
|---|---|
| Abertura e objetivos | 3 min |
| Demonstração central (seção 1) | ~15 min |
| Discussão guiada (seção 2) | 4 min |
| Fechamento (seção 4) | 2 min |
| Demonstração opcional (seção 1) | ~1 min, se houver tempo |

## 1. Demonstração central: um problema, dois prompts

### O cenário de trabalho

Considere um ambulatório fictício que enfrenta desafios operacionais e financeiros. O objetivo da demonstração **não é solucionar o problema de gestão em 15 minutos**, e sim observar como a formulação da solicitação modifica a qualidade do apoio oferecido pela IA.

### Passo a passo de condução

1. Rode o Prompt 1 na primeira conversa e mostre a resposta à turma.
2. Discuta os pontos a observar e a provocação abaixo.
3. Abra a segunda conversa, rode o Prompt 2 e avalie a resposta com a tabela de critérios.
4. Compare as duas respostas lado a lado e, se houver tempo, faça a demonstração opcional.

### Prompt 1 — Solicitação genérica

**Nota ao instrutor:** o Prompt 1 fala de hospital de propósito, por ser o pedido genérico. O Prompt 2 usa o ambulatório do cenário.

Copie o texto abaixo na primeira conversa:

```text
Como posso melhorar a gestão de um hospital?
```

**Pontos a observar (sem presumir que sempre ocorrerão):**

- A resposta pode ser correta em termos gerais, mas pouco conectada a uma decisão específica.
- É possível que apresente listas de boas práticas sem prioridades explícitas.
- Pode não indicar quais informações são necessárias para avaliar a viabilidade das sugestões.
- O conteúdo pode soar convincente mesmo sem conhecer o contexto institucional.

**Provocação:**

> Se eu apresentasse apenas essa resposta em uma reunião do conselho, ela seria suficiente para escolher um investimento ou aprovar um plano de ação? Por quê?

### Prompt 2 — Solicitação contextualizada

Na segunda conversa, copie o texto abaixo:

```text
Atue como consultor de gestão em saúde e ajude a estruturar
uma análise inicial para uma reunião de diretoria.

Contexto: um ambulatório fictício enfrenta aumento do tempo de
espera por consultas, absenteísmo de pacientes e restrições
orçamentárias. Ainda não temos dados quantitativos suficientes
para atribuir causas ou estimar o impacto das intervenções.

Tarefa:
1. Proponha cinco iniciativas que merecem avaliação.
2. Organize as iniciativas em uma matriz com: objetivo,
   possível benefício, esforço de implementação, riscos e
   indicadores que permitiriam avaliar o resultado.
3. Sugira uma ordem preliminar de investigação, explicando
   os critérios utilizados e deixando claro que ela não
   representa uma priorização definitiva.
4. Identifique as informações adicionais necessárias antes
   de recomendar a adoção de qualquer iniciativa.

Restrições:
- Não invente números, evidências, custos ou resultados.
- Diferencie fatos do cenário, hipóteses e recomendações.
- Não presuma que aumento da espera decorre de falta de médicos.
- Considere qualidade assistencial, experiência do paciente,
  viabilidade operacional e sustentabilidade financeira.

Formato: tabela executiva, seguida de um resumo de até
150 palavras destinado à diretoria.
```

**O que avaliar na resposta:**

| Critério | Pergunta para observar o resultado | Nota (0–2) |
|---|---|---|
| Aderência ao contexto | A resposta leva em conta espera, absenteísmo e orçamento? | |
| Utilidade gerencial | Apresenta opções comparáveis e informações acionáveis? | |
| Transparência | Separa fatos disponíveis, hipóteses e informações ausentes? | |
| Priorização responsável | Evita tratar opiniões ou suposições como evidências de impacto? | |
| Qualidade da apresentação | O formato ajuda alguém a discutir o tema em uma reunião? | |
| Segurança | Evita recomendações clínicas individualizadas e dados sensíveis? | |

Escala: 0 = não atende; 1 = atende parcialmente; 2 = atende bem. A mesma escala é usada no Metaprompt 3 do Módulo 3.

**Atenção:** um prompt melhor não garante uma resposta correta. Mesmo o segundo resultado é apenas um **insumo exploratório** para o trabalho do gestor.

### Demonstração opcional — Uma pergunta que melhora a segunda resposta

Se houver cerca de um minuto disponível, envie uma mensagem de acompanhamento na segunda conversa:

```text
Agora atue como um conselheiro fiscal crítico. Identifique
três fragilidades ou premissas não demonstradas na análise
anterior. Diga quais evidências seriam necessárias antes de
autorizar despesas com as iniciativas propostas.
```

Esse terceiro passo introduz a ideia de **interação iterativa** e evidencia como diferentes responsabilidades institucionais mudam as perguntas feitas à mesma análise.

## 2. Discussão guiada (4 minutos)

1. **Qual resposta vocês levariam para uma reunião de diretoria?** O que a torna mais útil?
2. **A segunda resposta é necessariamente verdadeira?** Que dados ainda precisariam ser levantados?
3. **Quem deveria avaliar a recomendação?** O diretor técnico, a área financeira, a operação ou uma equipe multidisciplinar?
4. **Há algum risco em seguir uma recomendação que parece organizada e segura, mas foi gerada sem evidências locais?**
5. **O que mudou entre os dois prompts: a inteligência da ferramenta ou a definição do trabalho solicitado?**

## 3. Síntese

- **Texto bem escrito ≠ diagnóstico confiável.** A forma de apresentação não comprova a qualidade das conclusões.
- **Sugestão ≠ recomendação validada.** Antes de implantar ações, é preciso testar premissas, checar dados e avaliar consequências.
- **Hipótese ≠ causa demonstrada.** Aumento de espera, por exemplo, pode envolver agenda, perfil de demanda, processos, capacidade, encaminhamentos ou outros fatores.
- **IA apoia ≠ IA decide.** O gestor e as instâncias de governança permanecem responsáveis pela avaliação e pelas decisões.

## 4. Fechamento: regra prática para levar adiante (2 minutos)

> **Não pergunte apenas “o que devo fazer?”. Explique o problema, o contexto, os limites e como uma boa resposta será avaliada.**

Exemplos:

| Em vez de perguntar… | Experimente solicitar… |
|---|---|
| “Como reduzir custos?” | “Quais categorias de custos devo analisar primeiro, considerando a preservação da qualidade assistencial? Quais dados são necessários?” |
| “Como melhorar minha equipe?” | “Ajude a estruturar hipóteses e indicadores para investigar atrasos de uma equipe assistencial antes de propor intervenções.” |
| “Esse projeto é bom?” | “Organize os benefícios alegados, riscos, premissas e critérios de decisão desse projeto. Aponte o que não pode ser concluído com os dados disponíveis.” |

**Ponte para o módulo 2:**

> “Agora que vimos a diferença que uma boa instrução pode fazer, vamos praticar um método para construir solicitações mais úteis, críticas e verificáveis.”

Próxima aula: [Módulo 2 — Como conversar com a IA de maneira eficiente](02-prompt-engineering.md).
