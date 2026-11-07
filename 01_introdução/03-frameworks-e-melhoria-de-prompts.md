# Módulo 3 — Frameworks e melhoria de prompts

## Objetivos de aprendizagem

Ao final deste módulo, os participantes devem ser capazes de:

1. Escolher um framework (RTF, TAG, RISE, CO-STAR, CARE ou BAB) conforme a situação.
2. Usar metaprompting em três passos: diagnóstico, reescrita e comparação de versões.
3. Reconhecer que um framework bem preenchido não substitui dados, premissas validadas nem revisão humana.

## Preparação

- Abra uma conversa para o metaprompt e outra para executar o prompt original e o revisado.
- Use o cenário fictício da seção 2.5 e apenas dados fictícios.

## Cronograma sugerido (~22 min)

Os tempos são uma sugestão; o roteiro original não define duração por seção.

| Etapa | Tempo |
|---|---|
| Abertura e objetivos | 2 min |
| Frameworks (seção 1) | ~8 min |
| Metaprompting (seção 2) | ~7 min |
| Síntese (seção 3) | 3 min |
| Fechamento (seção 4) | 2 min |

## Distinção essencial

| Conceito | Pergunta que responde | Exemplo |
|---|---|---|
| **Zero-shot** | Quantos exemplos forneço? | Solicitar um resumo sem mostrar um resumo-modelo |
| **Few-shot** | Quantos exemplos de entrada/saída forneço? | Demonstrar 3 classificações antes de pedir outra |
| **RTF, TAG, RISE etc.** | Como organizo a instrução? | Separar papel, tarefa, insumos e entrega |
| **Metaprompting** | Como uso a IA para melhorar a instrução? | Pedir diagnóstico, reescrita e testes do prompt |


## 1. Os frameworks de prompts

**Sugestão de condução:** não apresente os seis frameworks com o mesmo peso. Use o quadro de escolha rápida (item 1.7) para situar a turma e aprofunde dois: RTF, por ser o mais simples, e RISE, por unir dados, etapas e critérios de qualidade. Os demais servem como consulta.

### 1.1 RTF — Role, Task, Format

| Elemento | Significado | Pergunta de apoio |
|---|---|---|
| **R — Role (Papel)** | Perspectiva ou competência desejada | “Sob qual perspectiva a IA deve trabalhar?” |
| **T — Task (Tarefa)** | Ação concreta | “O que exatamente ela deve produzir?” |
| **F — Format (Formato)** | Estrutura da resposta | “Como desejo receber o resultado?” |

**Quando utilizar:** resumos, roteiros, checklists, comunicações e tarefas simples de produtividade.

**Exemplo — preparação de reunião de coordenação assistencial:**

```text
[PAPEL]
Atue como assessor de uma coordenação técnico-assistencial.

[TAREFA]
Crie uma pauta de reunião sobre o aumento de faltas em consultas
ambulatoriais de uma instituição fictícia. Inclua tópicos para levantar
hipóteses, definir dados adicionais e organizar próximos passos.

[FORMATO]
Entregue uma tabela com: tópico, objetivo da discussão, pergunta-chave
e tempo previsto. Limite a reunião a 30 minutos.

Não atribua causas ao absenteísmo sem evidências.
```

**Ponto a ressaltar:** atribuir um “papel” não concede acesso a conhecimentos institucionais que não foram fornecidos, nem substitui um especialista real.

### 1.2 TAG — Task, Action, Goal

| Elemento | Significado | Pergunta de apoio |
|---|---|---|
| **T — Task (Tarefa)** | Problema a enfrentar | “Qual é a missão?” |
| **A — Action (Ação)** | Trabalho solicitado à IA | “Qual operação ela deve executar?” |
| **G — Goal (Objetivo final)** | Utilidade prática do resultado | “Para qual decisão ou resultado isso servirá?” |

**Quando utilizar:** transformar necessidades vagas em solicitações orientadas a resultados.

**Exemplo — apoio ao conselho fiscal:**

```text
[TAREFA]
Avaliar criticamente uma proposta fictícia de investimento em
modernização de um ambulatório.

[AÇÃO]
Liste perguntas que o conselho fiscal deveria fazer sobre orçamento,
premissas financeiras, riscos de execução e mecanismos de controle.

[OBJETIVO]
Preparar uma reunião de diligência, sem emitir aprovação ou reprovação
antes de analisar o projeto completo.

Entregue 12 perguntas priorizadas e diga quais documentos seriam
necessários para respondê-las.
```

**Diferença em relação ao RTF:** TAG explicita o **para quê**. RTF costuma ser mais útil quando o formato de entrega é o requisito principal.

### 1.3 RISE — Role, Input, Steps, Expectation

| Elemento | Significado | Pergunta de apoio |
|---|---|---|
| **R — Role** | Perspectiva de atuação | “Qual expertise é relevante?” |
| **I — Input** | Insumos e informações disponíveis | “Com base em quais dados?” |
| **S — Steps** | Etapas observáveis da tarefa | “Em que sequência a resposta deve ser organizada?” |
| **E — Expectation** | Resultado esperado e critérios de qualidade | “Que entrega permitirá agir?” |

**Quando utilizar:** análise de indicadores, construção de planos, revisão de documentos e processos com múltiplas etapas.

**Exemplo — análise de indicadores fictícios:**

```text
[ROLE]
Atue como analista de gestão em saúde, com foco em operações ambulatoriais.

[INPUT]
Considere apenas estes dados fictícios:
- Janeiro: 1.100 consultas; 14% de absenteísmo; 22 dias de espera média.
- Fevereiro: 1.180 consultas; 16% de absenteísmo; 24 dias de espera média.
- Março: 1.240 consultas; 17% de absenteísmo; 29 dias de espera média.
- Abril: 1.290 consultas; 19% de absenteísmo; 33 dias de espera média.

[STEPS]
1. Descreva as tendências observáveis.
2. Calcule a mudança absoluta e relativa entre janeiro e abril
   para cada indicador, quando aplicável.
3. Separe fatos de hipóteses sobre possíveis causas.
4. Indique informações adicionais necessárias para testar as hipóteses.
5. Proponha ações exploratórias, sem prometer efeitos não demonstrados.

[EXPECTATION]
Entregue uma tabela de indicadores e um resumo executivo de até 150
palavras. Identifique premissas e limitações e não invente dados.
```

**Atenção:** a expressão “etapas” pede um **fluxo verificável de trabalho** ou uma resposta por fases; não é necessário exigir que o modelo revele raciocínio interno detalhado.

### 1.4 CO-STAR — Context, Objective, Style, Tone, Audience, Response

Este framework, divulgado pela **GovTech Singapore**, é especialmente interessante quando a informação será comunicada a públicos diferentes.

| Elemento | Aplicação em gestão |
|---|---|
| **C — Context** | Situação institucional e restrições |
| **O — Objective** | Objetivo específico da comunicação |
| **S — Style** | Estilo de redação: técnico, executivo, didático |
| **T — Tone** | Tom: objetivo, cuidadoso, propositivo |
| **A — Audience** | Público: diretoria, médicos, conselheiros, equipes |
| **R — Response** | Entrega: e-mail, síntese, apresentação ou tabela |

**Exemplo — comunicar resultados para conselheiros administrativos:**

```text
[CONTEXTO]
Uma rede fictícia de ambulatórios percebeu aumento do tempo de espera
nos últimos quatro meses. As causas ainda não foram determinadas.

[OBJETIVO]
Redigir uma nota de atualização gerencial que apresente o problema,
os pontos que precisam ser investigados e os próximos passos.

[ESTILO]
Comunicação executiva, clara e sem jargões desnecessários.

[TOM]
Objetivo, prudente e orientado a prestação de contas.

[PÚBLICO]
Conselheiros administrativos que não acompanham a operação diariamente.

[RESPOSTA]
Texto de até 250 palavras com: cenário, achados preliminares,
informações faltantes, riscos e encaminhamentos. Não apresente
hipóteses como causas comprovadas.
```

**Pergunta para os alunos:** o mesmo conteúdo deveria ser escrito da mesma maneira para o conselho e para a equipe do ambulatório?

### 1.5 CARE — Context, Action, Result, Example

| Elemento | Significado |
|---|---|
| **Context** | Situação de partida |
| **Action** | O que deve ser produzido ou transformado |
| **Result** | Resultado desejado |
| **Example** | Exemplo do que é aceitável ou desejado |

**Quando utilizar:** quando o padrão de saída é importante e um exemplo curto reduz ambiguidades. O elemento *Example* pode apoiar um prompt *one-shot* ou *few-shot* se houver exemplos concretos de entrada e saída.

```text
[CONTEXTO]
Preciso padronizar atas de reuniões de uma unidade de saúde fictícia.

[AÇÃO]
Converta as notas fornecidas em uma ata estruturada.

[RESULTADO]
Uma ata sucinta que diferencie decisões, pendências e responsáveis.

[EXEMPLO DE FORMATO]
Decisão: [conteúdo] | Responsável: [nome ou "não informado"]
| Prazo: [data ou "não informado"]

Não invente responsáveis, prazos ou decisões ausentes nas notas.
```

### 1.6 BAB — Before, After, Bridge

| Elemento | Significado |
|---|---|
| **Before (Antes)** | Situação atual indesejada |
| **After (Depois)** | Estado futuro desejado |
| **Bridge (Ponte)** | Caminho proposto para chegar lá |

**Quando utilizar:** discussão de melhorias de processo e propostas de transformação. Funciona como moldura de comunicação; não substitui análise de viabilidade.

```text
[ANTES]
Os pacientes de um ambulatório fictício enfrentam dificuldades para
remarcar consultas, e a unidade não monitora esse processo.

[DEPOIS]
Queremos um fluxo de remarcação claro, mensurável e acessível.

[PONTE]
Proponha um piloto de 30 dias com etapas, responsáveis funcionais,
indicadores e riscos. Liste também as informações que faltam para
validar a viabilidade do piloto.
```

### 1.7 Quadro de escolha rápida

| Situação | Framework inicial sugerido | Complemento importante |
|---|---|---|
| Criar uma pauta ou checklist | **RTF** | Prazo e restrições |
| Transformar um objetivo vago em uma tarefa | **TAG** | Critérios de sucesso |
| Analisar indicadores e propor um plano | **RISE** | Dados, premissas e validação |
| Preparar mensagem para diretoria ou conselho | **CO-STAR** | Informação documental verificável |
| Padronizar atas e relatórios | **CARE** | Exemplos e campos “não informado” |
| Explicar proposta de mudança | **BAB** | Viabilidade, risco e medição |

**Evite o “framework pelo framework”:** se uma solicitação simples já está clara, não há necessidade de preencher seis blocos. Se uma decisão depende de dados ausentes, nenhum acrônimo resolve essa lacuna.

---

## 2. Como pedir para a própria IA melhorar um prompt

A técnica é chamada de **metaprompting**: o objeto da tarefa é o próprio prompt.

### 2.1 Ciclo de trabalho recomendado

1. **Escreva o prompt original**, mesmo que esteja incompleto.
2. **Peça um diagnóstico**: ambiguidades, dados ausentes, restrições e riscos.
3. **Peça uma reescrita**: uma versão curta e uma versão completa.
4. **Responda às perguntas essenciais** ou mantenha lacunas explicitadas.
5. **Execute o original e o revisado** com o mesmo material de entrada.
6. **Compare as respostas** com critérios e faça ajustes.

> **Importante:** pedir “melhore meu prompt” pode gerar uma versão mais longa, porém não necessariamente mais útil. O teste é parte da técnica.

### 2.2 Metaprompt 1 — Revisor universal de prompts

Copie o texto abaixo, substitua o campo indicado e **não peça para executar a tarefa original nesse momento**.

```text
Você é um revisor de instruções para modelos de linguagem.
Seu trabalho NÃO é resolver a tarefa descrita no prompt, mas melhorar
sua clareza, precisão, verificabilidade e utilidade.

PROMPT ORIGINAL:
"""
[COLE AQUI O PROMPT QUE DESEJA MELHORAR]
"""

Faça o seguinte:
1. Identifique o objetivo principal em uma frase.
2. Avalie: contexto, instrução, dados necessários, restrições,
   formato de saída, público-alvo e critérios de validação.
3. Aponte até cinco ambiguidades ou lacunas importantes.
4. Faça no máximo três perguntas de esclarecimento, apenas se
   indispensáveis; caso contrário, declare suas premissas.
5. Reescreva o prompt em duas versões:
   A) ESSENCIAL: concisa e pronta para uso.
   B) ESTRUTURADA: detalhada, escolhendo o framework mais adequado.
6. Explique em até cinco itens o que mudou e por quê.
7. Sugira dois testes objetivos para comparar o prompt original
   com as versões revisadas.

Regras:
- Não invente dados institucionais, fontes nem requisitos.
- Preserve a intenção original, a menos que você identifique conflito.
- Inclua avisos de incerteza quando necessário.
- Não solicite nem exponha dados pessoais ou sigilosos.
- Não atribua a si mesmo autoridade para tomar decisões clínicas,
  administrativas ou legais em nome de profissionais.
```

### 2.3 Metaprompt 2 — Modo entrevista (quando o problema está mal definido)

Adequado quando o gestor sabe **qual problema deseja resolver**, mas ainda não sabe quais informações deve reunir.

```text
Quero construir um bom prompt para a seguinte necessidade:
[DESCREVA A NECESSIDADE EM UMA OU DUAS FRASES]

Atue como facilitador de definição do problema.
Não execute a tarefa ainda.

1. Faça uma pergunta de cada vez, priorizando as informações que
   mais alterariam a qualidade da resposta.
2. Limite-se a cinco perguntas no total.
3. Se eu não souber responder, registre a lacuna e proponha uma
   forma segura de tratá-la.
4. Ao terminar, entregue um prompt final reutilizável com campos
   entre colchetes para as variáveis que precisarei preencher.
5. Inclua como validar a resposta gerada por esse prompt.
```

### 2.4 Metaprompt 3 — Comparador de versões

Este prompt só deve ser executado **após** obter as duas respostas reais; não permita que a IA invente resultados dos testes.

```text
Compare as duas respostas abaixo para o MESMO problema e os MESMOS dados.

PROMPT A: [COLE A VERSÃO ORIGINAL]
RESPOSTA A: [COLE A RESPOSTA REAL]

PROMPT B: [COLE A VERSÃO REVISADA]
RESPOSTA B: [COLE A RESPOSTA REAL]

Avalie cada resposta de 0 a 2 em:
- aderência ao objetivo;
- uso fiel dos dados fornecidos;
- distinção entre fatos e hipóteses;
- clareza para o público-alvo;
- utilidade gerencial;
- explicitação de limitações e riscos.

Entregue:
1. Uma tabela com as notas e justificativas específicas.
2. Evidências textuais que sustentem cada avaliação.
3. Erros factuais ou alegações que exigem verificação externa.
4. Uma recomendação de qual prompt vale a pena manter, com ressalvas.

Não crie resultados, números ou referências ausentes.
Sua avaliação é uma análise auxiliar; a decisão final será humana.
```

### 2.5 Demonstração ao vivo: do prompt vago ao prompt testável

**Prompt original:**

```text
Me ajude a diminuir o absenteísmo do ambulatório.
```

**Como conduzir no projetor:**

1. Cole o prompt original no Metaprompt 1 e solicite o diagnóstico.
2. Destaque na resposta as lacunas mais importantes: perfil de faltas, especialidades, período, canais de agendamento e capacidade de equipe.
3. Mostre que uma reescrita responsável pode **solicitar informações adicionais** em vez de recomendar ações como se conhecesse a operação.
4. Execute o original e a versão revisada com o **mesmo cenário fictício**.
5. Pergunte: “A resposta revisada trouxe evidências ou apenas pareceu mais profissional?”

**Cenário fictício para teste:**

```text
Uma unidade ambulatorial fictícia apresenta absenteísmo de 19% em abril,
contra 14% em janeiro. Não sabemos ainda o perfil das faltas por
especialidade, faixa de horário ou antecedência do agendamento.
O gestor dispõe de 30 dias para organizar um diagnóstico inicial.
Não há autorização para alterar a equipe ou o orçamento neste momento.
```

**Resultado pedagógico esperado:** o prompt melhor deve ajudar a priorizar **perguntas diagnósticas, dados necessários, riscos e medidas testáveis**, sem inventar as causas.

## 3. Síntese

- **Framework organiza, não garante.** Um acrônimo bem preenchido não substitui dados ausentes.
- **Escolha pelo objetivo.** Se a solicitação já está clara, um prompt simples basta.
- **Metaprompting exige teste.** Compare o original e o revisado com o mesmo material; uma versão mais longa nem sempre é melhor.
- **A decisão continua humana.** Revise as premissas que a IA assumiu antes de usar o resultado.

## 4. Fechamento (2 minutos)

> Um bom prompt torna a conversa com a IA mais verificável. Ele não torna a decisão automática.

**Ponte para o próximo bloco:** agora que sabemos instruir e revisar prompts, vamos ver como a IA pode atuar como agente com skills reutilizáveis. Próxima etapa: [Agentes e skills](../02_agentes/01_agentes_e_skills.md).
