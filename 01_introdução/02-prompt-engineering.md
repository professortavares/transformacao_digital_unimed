# Módulo 2 — Como conversar com a IA de maneira eficiente

## Objetivos de aprendizagem

Ao final deste módulo, os participantes devem ser capazes de:

1. Escolher entre zero-shot, few-shot e análise estruturada conforme a tarefa.
2. Pedir resultados auditáveis (critérios, premissas, cálculos) em vez de "raciocínio completo".
3. Reconhecer que toda técnica pode falhar e exige validação.

## Preparação

- Abra uma conversa nova para cada comparação (A1 e A2; B1 e B2).
- Use apenas dados fictícios.

## Cronograma sugerido (~22 min)

Os tempos abaixo são uma sugestão; no roteiro original, só a Demonstração B tem duração definida.

| Etapa | Tempo |
|---|---|
| Abertura e objetivos | 3 min |
| Demonstração A (seção 2) | ~8 min |
| Demonstração B (seção 2) | ~5 min |
| Síntese (seção 3) | 3 min |
| Fechamento (seção 4) | 3 min |

## 1. Técnicas de prompting: o que são e quando usar

### 1.1. Visão comparativa

| Técnica | Ideia central | Quando utilizar | Cuidado principal |
|---|---|---|---|
| **Zero-shot** | Pedir uma tarefa **sem exemplos resolvidos**. | Resumos, classificações simples, rascunhos, exploração inicial. | O modelo pode interpretar categorias ou padrões de forma diferente do esperado. |
| **One-shot** | Fornecer **um exemplo** de entrada e saída. | Quando um único modelo de resposta já ajuda a mostrar o padrão. | Um exemplo ruim pode induzir um formato ruim. |
| **Few-shot** | Fornecer **alguns exemplos** de entrada e saída. | Classificações, padronização de atas, relatórios e comunicações. | Exemplos podem conter vieses, ambiguidades ou regras inconsistentes. |
| **CoT / raciocínio estruturado** | Decompor uma análise em **critérios, etapas verificáveis e justificativa**. | Comparar alternativas, calcular indicadores, discutir riscos. | Justificativa eloquente **não comprova** que o raciocínio ou a conclusão é válido. |
| **Decomposição / prompt chaining** | Separar uma tarefa complexa em **entregas encadeadas**, validando uma antes da próxima. | Analisar documentos → levantar problemas → propor opções → redigir parecer. | Erros iniciais podem ser propagados para as etapas seguintes. |
| **Contexto, papel e restrições** | Definir público, finalidade, dados, limites e formato. | Quase toda tarefa gerencial. | “Atue como especialista” não cria certificação nem garante precisão. |
| **Refinamento / crítica iterativa** | Avaliar a resposta e pedir mudanças específicas. | Revisão de documentos, análise de riscos, melhoria de propostas. | A IA pode repetir ou justificar seus próprios erros; exige validação externa. |

> **Nota didática sobre CoT:** o termo *Chain-of-Thought* é frequentemente usado para prompts que incentivam raciocínio em etapas. Na prática gerencial, prefira solicitar **resultados auditáveis**: critérios utilizados, premissas explícitas, cálculos reproduzíveis, evidências, pontos de incerteza e uma justificativa concisa. Não é necessário — nem garantia de acerto — pedir que o modelo revele todo o seu raciocínio interno.

### 1.2. Como escolher rapidamente

- **Quero uma primeira proposta, sem padrão especial:** comece com **zero-shot** contextualizado.
- **Quero que várias saídas tenham o mesmo padrão:** use **few-shot** com exemplos bem escolhidos.
- **Quero comparar opções de gestão:** peça **critérios explícitos**, evidências, restrições e justificativa resumida.
- **Quero executar uma atividade extensa:** use **decomposição** e valide cada entrega antes de avançar.
- **Recebi uma resposta superficial:** **refine** com objeções, dados adicionais e critérios de qualidade.

**Lembrete:** todas as técnicas podem falhar. Não existe superioridade universal de uma técnica: sua utilidade depende da tarefa, do modelo, dos dados e do modo de avaliação.

---

## 2. Demonstração — prompts prontos para copiar

### Demonstração A — Zero-shot x few-shot

#### Passo a passo de condução

1. Rode A1 em uma conversa nova e projete a tabela resultante.
2. Faça a pergunta ao grupo (logo abaixo do A1).
3. Abra outra conversa, rode A2 e compare as categorias atribuídas.
4. Confira as respostas com o quadro de referência, sem projetá-lo antes da discussão.

**Cenário:** a coordenação de um ambulatório fictício recebeu comentários curtos e deseja classificá-los em categorias operacionais para posterior análise. São exemplos criados para ensino, não dados de pacientes.

#### A1. Zero-shot: a tarefa sem exemplos

```text
Você apoia a coordenação de um ambulatório fictício.

Classifique cada comentário em UMA das categorias:
- AGENDAMENTO
- TEMPO_DE_ESPERA
- COMUNICACAO
- OUTROS

Comentários:
1. "Não consegui remarcar minha consulta pelo telefone."
2. "Fui atendido quarenta minutos depois do horário."
3. "Ninguém avisou que o horário tinha sido alterado."
4. "A sala de espera estava muito fria."
5. "Esperei na linha, mas não consegui confirmar a consulta."

Retorne uma tabela com número, comentário, categoria e justificativa
breve. Não acrescente fatos que não estejam nos comentários.
```

**Pergunta ao grupo:** a categoria atribuída ao comentário 5 será consistente com o critério que a equipe usaria? A instrução ainda permite interpretações diferentes?

#### A2. Few-shot: a mesma tarefa com exemplos de referência

> Execute em **outra conversa nova** para comparar de maneira mais justa.

```text
Você apoia a coordenação de um ambulatório fictício.

Use exatamente as categorias:
- AGENDAMENTO: marcar, remarcar ou confirmar consultas.
- TEMPO_DE_ESPERA: atraso ou demora para atendimento no dia.
- COMUNICACAO: falta, divergência ou atraso em avisos e orientações.
- OUTROS: aspectos não incluídos nas categorias anteriores.

Exemplos de classificação:
Entrada: "Tentei alterar a data da consulta e não consegui."
Saída: AGENDAMENTO

Entrada: "A consulta começou com uma hora de atraso."
Saída: TEMPO_DE_ESPERA

Entrada: "Não fui informado de que o médico havia mudado."
Saída: COMUNICACAO

Entrada: "A recepção estava sem cadeiras suficientes."
Saída: OUTROS

Agora classifique:
1. "Não consegui remarcar minha consulta pelo telefone."
2. "Fui atendido quarenta minutos depois do horário."
3. "Ninguém avisou que o horário tinha sido alterado."
4. "A sala de espera estava muito fria."
5. "Esperei na linha, mas não consegui confirmar a consulta."

Retorne apenas uma tabela com número e categoria. Para comentários
ambíguos, acrescente a coluna "revisão humana necessária" = SIM.
```

**Debate rápido:** os exemplos podem melhorar a consistência, mas também podem **induzir erros** caso as definições e exemplos não estejam alinhados. Observe se a IA marcou ambiguidades e lembre que a comparação tem apenas cinco registros.

**Nota metodológica:** A1 pede tabela com justificativa e A2 pede apenas a tabela de categorias. Como os formatos diferem, compare a **categoria atribuída**, não a estrutura da resposta.

**Ponto pedagógico:** com o few-shot, o usuário não só descreve a tarefa: ele **mostra como quer que a tarefa seja realizada**.

**Quadro de referência para o instrutor** (não projetar antes da discussão):

| # | Comentário | Categoria esperada (A2) |
|---|---|---|
| 1 | Não consegui remarcar minha consulta pelo telefone. | AGENDAMENTO |
| 2 | Fui atendido quarenta minutos depois do horário. | TEMPO_DE_ESPERA |
| 3 | Ninguém avisou que o horário tinha sido alterado. | COMUNICACAO |
| 4 | A sala de espera estava muito fria. | OUTROS |
| 5 | Esperei na linha, mas não consegui confirmar a consulta. | AGENDAMENTO ou TEMPO_DE_ESPERA (ambíguo; "revisão humana necessária" = SIM) |

O comentário 5 é propositalmente ambíguo: "confirmar" aponta para AGENDAMENTO e "esperei" para TEMPO_DE_ESPERA. Ele serve para discutir o que fazer quando as definições não decidem o caso.

### Demonstração B — CoT aplicado como justificativa auditável (aprox. 5 minutos)

**Cenário fictício:** o ambulatório precisa selecionar uma iniciativa para um projeto-piloto. Não há dados suficientes para estimar retorno financeiro com segurança.

**Correspondência entre as alternativas:** em B1, as opções são "ampliar horários" (A), "automatizar lembretes" (B) e "reorganizar a agenda" (C). Em B2, o texto é mais detalhado, mas as letras correspondem às mesmas alternativas.

#### B1. Pedido direto

```text
Qual iniciativa é melhor para um ambulatório que está enfrentando
absenteísmo e aumento da espera: ampliar horários, automatizar lembretes
ou reorganizar a agenda? Escolha uma.
```

#### B2. Pedido com análise estruturada

```text
Você está preparando material para discussão de um comitê gestor.

Cenário fictício: ambulatório com aumento de faltas e da espera por
consultas. A equipe avalia três alternativas:
A. Ampliar horários de atendimento.
B. Melhorar confirmação de consultas e gestão das faltas.
C. Revisar regras de agendamento e fluxos internos.

Não há dados confiáveis de custo, capacidade ociosa, perfil das faltas
nem resultado de intervenções anteriores.

Faça uma análise organizada:
1. Declare o objetivo da decisão.
2. Compare as opções por impacto potencial, facilidade de implantação,
   risco operacional e necessidade de dados adicionais.
3. Para cada opção, diferencie fatos fornecidos, hipóteses e
   informações ainda não disponíveis.
4. Apresente os critérios usados na comparação e uma justificativa
   curta e verificável; não invente números ou evidências.
5. Em vez de afirmar que existe uma opção definitivamente superior,
   recomende o que precisa ser medido ou testado antes de decidir.

Formato: tabela comparativa + até 120 palavras de conclusão.
```

**Pergunte:** o segundo prompt tornou a resposta mais útil para **discussão e auditoria**, mesmo sem garantir que a recomendação seja correta?

**Explique:** *CoT* não deve ser vendido como “pedir para pensar passo a passo resolve tudo”. Para decisões relevantes, o ganho desejado é a **transparência dos critérios e a verificabilidade do resultado** — nunca a transferência da responsabilidade decisória à IA.

**O que comparar entre B1 e B2:**

| Aspecto | B1 (pedido direto) | B2 (análise estruturada) |
|---|---|---|
| Tipo de resposta | Pede uma única escolha | Compara as três opções |
| Fatos e hipóteses | Não solicitados | Separados para cada opção |
| Dados faltantes | Não solicitados | Listados explicitamente |
| Conclusão | "Escolha uma" | Recomenda o que medir antes de decidir |

## 3. Síntese

- **Nenhuma técnica é universal.** Zero-shot, few-shot e análise estruturada servem a tarefas diferentes.
- **Exemplos moldam a resposta.** Um exemplo ruim induz um formato ruim.
- **Justificativa bem escrita não comprova nada.** Verifique critérios, cálculos e evidências.
- **IA apoia, não decide.** A responsabilidade pela conclusão continua sendo humana.

## 4. Fechamento (3 minutos)

> Uma boa técnica organiza a instrução; a verificação dos resultados continua sendo responsabilidade de quem usa a IA.

**Ponte para o módulo 3:** agora que vimos as técnicas, vamos organizar instruções com frameworks e aprender a melhorar um prompt com a própria IA. Próxima aula: [Módulo 3 — Frameworks e melhoria de prompts](03-frameworks-e-melhoria-de-prompts.md).
