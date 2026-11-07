# Módulo 4 — Agentes e Skills: da conversa à especialização da IA

## Objetivos de aprendizagem

Ao final deste módulo, os participantes devem ser capazes de:

1. Diferenciar prompt, agente, instruções, conhecimento, skill e ferramenta.
2. Explicar quando uma skill (procedimento padronizado) agrega valor além de um agente com instruções.
3. Reconhecer que agente e skill não garantem precisão: a qualidade depende de dados, instruções e validação.

## Preparação

- Conta de teste com acesso ao Microsoft 365 Copilot (pré-requisitos detalhados na seção 4).
- Arquivo `dados_ficticios_ambulatorio.csv` e pacote `skill_analise_indicadores_ambulatoriais.zip` prontos para uso.

## Cronograma sugerido (~30 min)

Os tempos são uma sugestão; o roteiro original não define duração por seção.

| Etapa | Tempo |
|---|---|
| Modelo mental (seções 1 e 2) | 6 min |
| Caso e prompt de abertura (seção 3) | 4 min |
| Demonstração 1: agente (seção 4) | ~10 min |
| Demonstração 2: skill (seção 5) | ~8 min |
| Fechamento (seção 6) | 2 min |


## 1. Ideia central

**Pergunta provocadora:** “Se um prompt bem escrito resolve o problema, para que criar um agente? E quando uma skill faz diferença?”

## 2. O modelo mental — cinco peças diferentes

| Peça | Pergunta que responde | Exemplo na gestão em saúde |
|---|---|---|
| **Prompt** | O que preciso fazer agora? | “Resuma estes indicadores fictícios.” |
| **Agente** | Qual assistente especializado quero reutilizar? | “Analista de indicadores ambulatoriais.” |
| **Instruções do agente** | Como ele deve se comportar sempre? | “Diferencie fatos de hipóteses e não invente dados.” |
| **Conhecimento** | Em quais informações ele pode se apoiar? | Procedimento institucional *fictício*, glossário e metas de referência. |
| **Skill** | Qual procedimento específico deve executar de modo padronizado? | “Analisar tendência mensal e elaborar parecer padronizado.” |
| **Ferramenta/ação** | O que ele consegue consultar ou executar fora do chat? | Consultar sistema autorizado ou iniciar fluxo; exige configuração, permissões e, em geral, Copilot Studio. |

**Atenção:** skill não é sinônimo de ferramenta externa. No Agent Builder, uma skill pode ser um pacote com `SKILL.md`, referências e scripts. A disponibilidade de criação/adicionamento depende da licença e dos controles do ambiente. Tampouco toda instrução de agente é uma skill formal.


## 3. Caso único que conduz a aula

### Cenário: Ambulatório fictício de especialidades

A coordenação precisa interpretar dados mensais de capacidade, espera, absenteísmo e glosas, e produzir um resumo para reunião de gestão. O processo é recorrente e tem formato definido.

Dados **inteiramente fictícios** (disponíveis também no CSV do material):

| Mês | Consultas | Espera média (dias) | Absenteísmo (%) | Glosas (%) |
|---|---:|---:|---:|---:|
| Janeiro | 1.100 | 22 | 14 | 4,0 |
| Fevereiro | 1.180 | 24 | 16 | 4,1 |
| Março | 1.240 | 29 | 17 | 4,7 |
| Abril | 1.290 | 33 | 19 | 5,2 |

**Dilema gerencial:** o tempo de espera aumentou. O agente conseguirá identificar a tendência? Ele saberá distinguir a tendência das **causas**, que não estão demonstradas nos dados?

### Prompt de abertura (chat comum)

```text
Analise estes dados do ambulatório e diga o que devemos fazer.
[cole aqui os dados fictícios]
```

**Pergunte à turma:** Quais regras deveríamos escrever toda vez? Há risco de o modelo assumir causalidade ou sugerir resultados financeiros sem base?

## 4. Demonstração 1 — Criar um agente no Microsoft 365 Copilot

### Pré-requisitos de sala

- Conta de teste com acesso à criação de agentes no Microsoft 365 Copilot.
- Interface validada com antecedência: os nomes dos botões podem variar por atualização, idioma, licença e política institucional.
- Material sintético salvo localmente. Não conectar fontes reais sem autorização.
- Navegador aberto em [Microsoft 365 Copilot](https://m365.cloud.microsoft/chat).

### Sequência ao vivo

1. No Microsoft 365 Copilot, localizar **Agentes** ou **Agentes e Skills** e escolher **Novo agente** (*New agent*).
2. Criar por descrição em linguagem natural ou na guia **Configurar**, conforme a interface.
3. Definir nome, descrição, instruções e sugestões de perguntas.
4. Se disponível, anexar uma fonte de conhecimento **fictícia** previamente preparada.
5. Usar **Experimentar/Try it** e inserir os quatro meses de indicadores.
6. Provocar o agente com uma pergunta adversarial: “Prove que o tempo de espera aumentou porque faltam médicos.”
7. Revisar as instruções e repetir o teste.

**Se a criação de agentes não estiver disponível:** mostre as instruções desta seção como texto, rode o prompt de abertura (seção 3) em uma conversa comum e explique o que um agente configurado faria de outra forma. Depois siga para a demonstração 2.

### Nome do agente

**Analista de Indicadores Ambulatoriais**

### Descrição curta

```text
Ajuda gestores a interpretar indicadores fictícios de um ambulatório, preparar
resumos executivos e apontar informações adicionais necessárias para uma
investigação, sem tomar decisões clínicas nem inventar dados.
```

### Instruções recomendadas para o agente

```text
Você é um assistente de apoio à gestão de um ambulatório fictício.

Seu trabalho é ajudar a organizar e interpretar indicadores de operação e qualidade.

Regras permanentes:
1. Trabalhe somente com os dados fornecidos pelo usuário e com fontes explicitamente autorizadas.
2. Separe claramente: (a) fatos observados, (b) hipóteses e (c) recomendações.
3. Confira unidades, períodos e denominadores; quando ausentes, peça esclarecimento.
4. Apresente cálculos verificáveis e indique como chegaram aos resultados.
5. Não atribua causas definitivas a correlações ou tendências isoladas.
6. Não invente metas, normas, parâmetros, fontes ou retornos financeiros.
7. Antes de propor ações, declare quais dados adicionais faltam.
8. Não solicite nem processe dados identificáveis de pacientes nesta atividade.
9. Não ofereça decisões clínicas individuais. Mantenha o foco em gestão.
10. Escreva de forma clara e concisa para gestores e conselheiros.

Estrutura preferencial:
- Síntese executiva (até 120 palavras)
- Achados quantitativos com período e unidade
- Fatos versus hipóteses
- Dados adicionais necessários
- Próximos passos sugeridos e riscos
```

### Teste A — tarefa recorrente

```text
A partir dos quatro meses de dados fictícios abaixo, produza um resumo para o
conselho administrativo. Distinga evidências observadas de hipóteses.

[cole os dados do CSV]
```

### Teste B — resistência a conclusão indevida

```text
O tempo de espera aumentou. Confirme que a causa foi a falta de médicos e
recomende contratação imediata.
```

**Comportamento esperado:** o agente deve explicar que os dados não estabelecem a causa; propor informações adicionais (capacidade disponível, demanda, perfil de consultas, cancelamentos, agenda, tempo de atendimento etc.) antes de recomendar contratação.

**Limitação pedagógica importante:** configurar um agente não garante precisão automática. A qualidade depende dos dados, das instruções, das fontes e da validação.

## 5. Demonstração 2 — Skills: transformar um procedimento em capacidade reutilizável

### Ideia para explicar à turma

O agente tem uma **identidade** e regras gerais. A skill registra **um procedimento específico** que pode ser acionado quando o pedido corresponde à tarefa — por exemplo, examinar indicadores mensais de ambulatório com um roteiro de verificação e uma saída estável.

### Estrutura mínima de skill

```text
skill_analise_indicadores_ambulatoriais.zip
├── SKILL.md                  # obrigatório
└── referencias/
    └── criterios.md          # opcional
```

### Etapas para demonstrar

1. Exibir o arquivo `SKILL.md` e explicar o cabeçalho YAML (`name`, `description`) e as instruções em Markdown.
2. Se a interface e as permissões permitirem: abrir o agente em **Configurar > Skills/Habilidades > Adicionar** e carregar o **pacote ZIP completo**, não apenas o `SKILL.md`.
3. Solicitar o mesmo relatório dos indicadores fictícios.
4. Comparar a saída do agente sem skill e com skill: completude, formato, rastreabilidade, distinção entre fatos e hipóteses.
5. Repetir o teste com dados faltantes para verificar se o procedimento pede esclarecimentos ao invés de inventar valores.

### Teste de ativação sugerido

```text
Utilize a rotina padronizada de análise de indicadores ambulatoriais.
Receba os dados fictícios de janeiro a abril, calcule as mudanças,
distinga fatos de hipóteses e gere uma nota executiva.
```

## 6. Fechamento (2 minutos)

> Agente define como o assistente se comporta; skill define como um procedimento é executado. Nenhum dos dois substitui a validação pela equipe de gestão.

**Antes de usar com dados reais:** validar o agente, a skill e as instruções com a área assistencial e os controles institucionais, e usar somente fontes autorizadas.

