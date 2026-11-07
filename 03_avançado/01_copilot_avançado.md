# Módulo 5 — Copilot na prática: do Excel ao Word e ao PowerPoint

## 1. Proposta pedagógica

### Pergunta norteadora

> Como transformar dados operacionais em uma recomendação executiva **sem confundir texto convincente com evidência confiável**?

Tarefa real de gestão:

```text
Dados fictícios de um ambulatório (Excel)
          ↓ análise e conferência
Achados validados e relatório executivo (Word)
          ↓ curadoria, síntese e adaptação ao público
Apresentação de 5 slides ao conselho (PowerPoint)
          ↓
Discussão: o que a IA fez bem, o que exigiu revisão humana?
```

### Regras de segurança

- **Não** inserir dados pessoais de pacientes, dados médicos identificáveis, números de prontuário, dados de colaboradores ou documentos institucionais sigilosos em ambientes não autorizados.
- Confirmar a política institucional sobre onde os arquivos são armazenados, compartilhados e processados.
- Avaliar sempre as recomendações humanas antes de aplicá-las a decisões assistenciais, financeiras ou regulatórias.
- Não apresentar outputs como parecer técnico, jurídico, contábil ou clínico validado.

---

## 2. Caso transversal: Centro de Especialidades Horizonte (fictício)

### Contexto apresentado à turma

> A diretoria de um centro de especialidades acompanha oito meses de indicadores de Cardiologia, Ortopedia e Endocrinologia. Existem preocupações com faltas, aumento do tempo médio de espera e glosas. O conselho administrativo solicitou uma apresentação curta, com fatos, riscos, perguntas que ainda precisam ser respondidas e um plano inicial de investigação. **Não foi fornecido orçamento nem evidência causal suficiente para recomendar investimentos específicos.**

### Arquivo de dados

`indicadores_ambulatoriais_ficticios.xlsx`

A guia `Indicadores` contém:

| Campo | Significado |
|---|---|
| `Mes` | Competência entre janeiro e agosto de 2026. |
| `Especialidade` | Cardiologia, Ortopedia ou Endocrinologia. |
| `Agendadas` | Consultas agendadas. |
| `Realizadas` | Consultas concluídas. |
| `Faltas` | Não comparecimentos. |
| `Espera_media_dias` | Tempo médio de espera da especialidade no mês. |
| `Receita_bruta` | Faturamento bruto fictício do mês (R$). |
| `Glosas` | Valor fictício glosado no mês (R$). |

A guia `Dicionario` explica os campos e as limitações. Para simplificar a atividade, a base foi construída com `Agendadas = Realizadas + Faltas`; não modela cancelamentos ou remarcações.

### Pergunta para provocar a turma

> O aumento das faltas **prova** que a instituição precisa contratar mais médicos?


## 3. Laboratório A — Copilot + Excel

### Aprendizado-chave

Usar IA para **explorar dados e acelerar análises**, mantendo a capacidade de refazer cálculos e questionar conclusões.

### Passo A1 — Explorar a planilha (5 min)

Abra a guia `Indicadores`, apresente o dicionário de dados e execute:

```text
Analise a tabela IndicadoresAmbulatoriais desta pasta de trabalho.
Antes de tirar conclusões:
1. Descreva as colunas e o período coberto.
2. Informe quantos registros e especialidades existem.
3. Identifique limitações da base e perguntas que ela NÃO pode responder.
4. Não use informações externas nem invente campos.
```

**Pergunta ao grupo:** o que ainda precisaríamos saber para orientar uma decisão gerencial?

### Passo A2 — Calcular métricas e criar gráficos (10 min)

```text
Usando somente a tabela IndicadoresAmbulatoriais:

1. Crie a métrica Taxa_absenteismo = soma(Faltas) / soma(Agendadas)
   para cada mês e cada especialidade.
2. Crie a métrica Taxa_glosa = soma(Glosas) / soma(Receita_bruta)
   para cada mês e especialidade.
3. Gere uma tabela-resumo mensal contendo: agendadas, realizadas,
   faltas, taxa de absenteísmo, receita bruta, glosas e taxa de glosa.
4. Gere um gráfico de linhas da taxa mensal de absenteísmo e outro
   da taxa mensal de glosa.
5. Compare janeiro e agosto de 2026 usando variação em PONTOS
   PERCENTUAIS para as taxas.
6. Informe as fórmulas, os filtros e as referências usados nos cálculos.

Não use a média simples das taxas por especialidade como taxa total.
Não atribua causalidade aos padrões encontrados.
```

**Nota de facilitação:** se o Copilot criar os cálculos em abas novas ou em células diretamente, mostre o que mudou e confira uma fórmula. Se apenas responder no chat, peça para criar uma tabela no arquivo — quando o recurso de edição estiver disponível.

### Passo A3 — Teste de pensamento crítico (5 min)

```text
O absenteísmo aumentou entre janeiro e agosto.
Confirme que o motivo é falta de médicos e recomende a
contratação imediata de mais profissionais.
```

**Resultado desejado:** a IA deve recusar a inferência como fato, explicar que falta informação para estabelecer causalidade e sugerir quais dados coletar. Se ela concordar sem ressalvas, a resposta vira material do debate sobre falhas de confiabilidade.

---

## 4. Laboratório B — Copilot + Word (15 min)

### Aprendizado-chave

Transformar achados numéricos validados em **comunicação gerencial**, sem acrescentar justificativas ou recomendações não fundamentadas.

### Passo B1 — Criar um relatório executivo (10 min)

1. Abra o Word e o Copilot, ou selecione o agente Word no Copilot Chat, se disponível.
2. Use o XLSX como referência **somente se o ambiente permitir e se os dados estiverem acessíveis**. Caso contrário, cole os achados validados da etapa A no prompt.
3. Solicite um rascunho do relatório.

```text
Atue como assessor de gestão de um centro ambulatorial fictício.
Crie um relatório executivo para o conselho administrativo, com
no máximo duas páginas, a partir EXCLUSIVAMENTE dos indicadores
confirmados a seguir.

DADOS VALIDADOS:
- Período: janeiro a agosto de 2026; três especialidades.
- Consultas agendadas no período: 6.650; realizadas: 5.649;
  faltas: 1.001; absenteísmo global: 15,05%.
- Receita bruta acumulada: R$ 1.862.320; glosas: R$ 67.795;
  taxa global de glosas: 3,64%.
- Janeiro: 740 agendadas; 86 faltas; 11,62% de absenteísmo;
  R$ 215.520 de receita bruta; R$ 5.072 em glosas; 2,35% de glosas.
- Agosto: 940 agendadas; 175 faltas; 18,62% de absenteísmo;
  R$ 252.290 de receita bruta; R$ 13.023 em glosas; 5,16% de glosas.

ESTRUTURA:
1. Resumo executivo (até 120 palavras).
2. Indicadores e evolução observada (tabela).
3. Fatos observados versus hipóteses que exigem investigação.
4. Riscos assistenciais, operacionais e financeiros a avaliar.
5. Plano de investigação para os próximos 30 dias,
   com responsáveis em aberto para designação humana.
6. Perguntas que o conselho deve fazer antes de autorizar ações.

RESTRIÇÕES:
- Não invente causas, referências externas, orçamentos ou metas.
- Não apresente hipóteses como diagnósticos.
- Evite recomendações clínicas.
- Indique que se trata de um exercício com dados fictícios.
- Use linguagem objetiva, adequada a conselheiros não especialistas.
```

### Passo B2 — Refinar a mensagem conforme o público (5 min)

```text
Reescreva o resumo executivo deste relatório para conselheiros
administrativos e fiscais. Mantenha todos os fatos numéricos,
reduza jargões assistenciais e destaque:
1. O que sabemos;
2. O que ainda não sabemos;
3. Qual decisão seria prematura;
4. Que informações o conselho deveria solicitar à diretoria.
Não altere os dados nem acrescente conclusões sem evidências.
```

**Pergunta à turma:** um texto bem redigido pode esconder um cálculo errado que veio do Excel? Como evitar que o erro seja propagado para o Word?

**Ponto importante:** o arquivo Word é o **produto revisado** desta etapa. Salve-o para fazer a transição ao PowerPoint. Se a edição no Word não estiver disponível, utilize o modelo `modelo_contingencia_relatorio_executivo.docx`, desta pasta.

---

## 5. Laboratório C — Copilot + PowerPoint (15 min)

### Aprendizado-chave

Produzir uma **narrativa visual para apoiar decisões**, em vez de apenas converter parágrafos em slides.

### Passo C1 — Criar uma apresentação (10 min)

**Caminho preferencial:** no PowerPoint, use o Copilot para criar uma apresentação a partir do documento Word finalizado, quando a opção de referenciar o arquivo estiver disponível.

**Caminho alternativo:** use o texto do relatório validado como referência no prompt ou utilize um agente PowerPoint para gerar um arquivo, conforme a experiência habilitada no ambiente.

```text
Crie uma apresentação executiva com EXATAMENTE 5 slides,
para uma reunião de 10 minutos do conselho administrativo de
um centro de especialidades fictício.

Use exclusivamente o relatório Word referenciado (ou o texto
validado que forneci) como fonte de dados. Não invente números.

ESTRUTURA:
Slide 1 — Pergunta de gestão e contexto do período.
Slide 2 — Três indicadores prioritários e evolução jan→ago.
Slide 3 — Principais riscos e limitações da base.
Slide 4 — Alternativas de investigação, sem inferência causal.
Slide 5 — Decisões e informações que o conselho deve solicitar.

REQUISITOS:
- Um título que expresse a conclusão de cada slide.
- Pouco texto, com gráficos legíveis e unidades claras.
- Sempre distinguir percentuais de pontos percentuais.
- Separar fatos observados de hipóteses de investigação.
- Não afirmar que algum fator causou outro.
- Não criar metas, valores de investimento ou ganhos previstos.
- Identificar os dados como fictícios.
- Caso possível, inclua notas do apresentador com as ressalvas.
```

### Passo C2 — Refinamento executivo (5 min)

```text
Revise esta apresentação como se você fosse um conselheiro fiscal
cético. Identifique slides com números sem fonte, conclusões
mais fortes do que as evidências, unidades ausentes, texto demais
ou recomendações sem estimativa de custo. Proponha correções e,
onde permitido, aplique-as mantendo a apresentação em 5 slides.
```

**Perguntas à turma:** o que foi perdido ao condensar duas páginas em cinco slides? O que ganhamos em clareza? Qual número merece uma checagem final antes da reunião?

