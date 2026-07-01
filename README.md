# miniguia-nps-notebooklm
Caderno temático sobre Net Promoter Score (NPS) construído com NotebookLM — curadoria de fontes, engenharia de prompts e miniguia de estudo. Desafio de projeto DIO.
# 📊 Miniguia de Estudos: Net Promoter Score (NPS)

> Caderno Temático criado no NotebookLM como parte do desafio de projeto da DIO — "Explorando a IA como ferramenta de aprendizagem ativa".

---

## 🎯 Contexto e Objetivos

O assunto escolhido para este Caderno Temático foi o **Net Promoter Score (NPS)**, metodologia criada por Frederick Reichheld em 2003 (artigo *"The One Number You Need to Grow"*, publicado na Harvard Business Review) para medir a satisfação e a lealdade de clientes através de uma única pergunta-chave: *"De 0 a 10, o quanto você recomendaria esta empresa/produto/serviço a um amigo ou colega?"*

Escolhi o tema por sua relevância direta para a área de **Gestão de Serviços e Atendimento ao Cliente**, disciplina que estou cursando na Tecnologia em Processos Gerenciais (UFF), e por ser uma métrica amplamente cobrada em contextos de gestão da qualidade, CRM e experiência do cliente — conteúdo que também aparece em provas e em entrevistas de estágio na área administrativa.

### Objetivos de estudo

- Entender a origem, o conceito e a lógica por trás do NPS.
- Dominar o cálculo do indicador (fórmula, classificação de promotores/neutros/detratores).
- Compreender como o NPS se relaciona com outras áreas da gestão, como Qualidade e Comunicação.
- Analisar um caso prático de implementação do NPS em uma empresa real (estudo de caso).
- Conhecer modelos complementares de avaliação de qualidade em serviços (ex: SERVQUAL), para ter repertório comparativo além do NPS.
- Construir um material de revisão rápida (glossário + prompts) para usar antes de provas.

---

## 📚 Curadoria de Fontes

Fontes selecionadas e carregadas no NotebookLM (mescla de texto acadêmico, artigo de blog especializado e transcrição de vídeo):

| # | Fonte | Tipo | Foco principal |
|---|-------|------|-----------------|
| 1 | ANDRADE, G. G.; CUNHA, P. H. **"Integração entre o Net Promoter Score e a gestão da Qualidade e Comunicação"**. Revista Gestão & Gerenciamento, v.19, 2023. | Artigo acadêmico (PDF) | Fundamentação teórica de NPS + Gestão da Qualidade + Comunicação; estudo de caso na empresa Concet Engenharia |
| 2 | ALONSO, Roberto. **"Net Promoter Score (NPS): o que é, como aplicar e estudos de caso"**. Blog FIA Business School, 2024. | Artigo de blog | Guia prático completo: como calcular, aplicar, ferramentas (Google Forms, SurveyMonkey etc.) e exemplos reais (Tesla, Nubank, Natura...) |
| 3 | Transcrição de vídeo — **"Você sabe o que é NPS?"**, Mateus Pedorim (SEOS Force) | Transcrição de vídeo | Explicação didática do conceito, fórmula e faixas de classificação (excelente/muito bom/razoável/ruim) |
| 4 | SANTOS, C. H.; GONÇALVES, A. T. P. **"Avaliação da qualidade do serviço prestado pelo aplicativo de transporte da Uber: uma aplicação da escala SERVQUAL"**. Journal of Management & Technology, v.23, n.2, 2023. | Artigo acadêmico (PDF) | Fonte complementar: outro modelo de avaliação de qualidade em serviços (SERVQUAL, GAP = Percepção − Expectativa), útil para comparar com o NPS |

> 💡 No README final, troque a coluna "Fonte" por links reais (DOI, URL do blog, link do vídeo no YouTube) sempre que a fonte for pública. Os PDFs acadêmicos, se você não tiver o link direto do periódico, pode simplesmente citar a referência completa (como acima) sem precisar hospedar o PDF no repositório — isso evita problemas de direitos autorais.

---

## 🧪 Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Aqui documentei o processo de tentativa e erro ao interrogar o NotebookLM sobre as fontes.

### Prompt 1 — Pergunta ampla (baseline)
**Prompt:** `O que é NPS e como ele é calculado?`
**Resultado:** resposta correta, mas genérica — misturou definição do artigo 1 e do artigo 2 sem diferenciar contexto (empresarial vs. teórico).
**Aprendizado:** perguntas amplas geram respostas "médias". Funciona bem para primeiro contato com o tema, mas não é ideal para fixação.

### Prompt 2 — Pedindo comparação entre fontes
**Prompt:** `Compare como o artigo da Revista Gestão & Gerenciamento e o artigo da FIA definem a fórmula do NPS. Há alguma diferença na forma de calcular?`
**Resultado:** o NotebookLM identificou corretamente que a fórmula é a mesma (% promotores − % detratores), mas que a FIA apresenta em formato decimal (ex: 0,4 = 40%) enquanto o artigo acadêmico trabalha direto em pontos percentuais.
**Cicatriz:** na primeira tentativa eu não citei os nomes das fontes, só disse "os dois textos", e o modelo confundiu com a transcrição do vídeo (que também explica a fórmula). **Correção:** sempre nomear a fonte explicitamente no prompt quando o objetivo é comparação.

### Prompt 3 — Pedindo aplicação prática / estudo de caso
**Prompt:** `Segundo o estudo de caso da empresa Concet Engenharia, quais foram os passos práticos para implementar o NPS gratuitamente?`
**Resultado:** ótimo — o modelo listou corretamente os 4 sistemas gratuitos do Google usados (Forms, Sheets, Drive, Gmail) e as etapas (criação da pesquisa, cálculo, análise, divulgação).
**Aprendizado:** perguntas que citam o nome da empresa/estudo de caso funcionam muito bem para "ancorar" a resposta na fonte certa e evitar alucinação.

### Prompt 4 — Pedindo conexão entre conceitos de fontes diferentes
**Prompt:** `Como o conceito de "lucro bom" e "lucro ruim" de Reichheld se relaciona com a dimensão de Confiabilidade da escala SERVQUAL?`
**Resultado:** aqui apareceu a primeira "cicatriz" real — o NotebookLM tentou relacionar os dois conceitos, mas como são de fontes diferentes (NPS x SERVQUAL) e não conectados diretamente nos textos originais, a resposta ficou especulativa demais.
**Correção aplicada:** reformulei para `Resuma separadamente o conceito de "lucro bom/lucro ruim" (fonte NPS) e o conceito de GAP de confiabilidade (fonte SERVQUAL), sem tentar uni-los.` — resposta ficou muito mais precisa e sem inferências forçadas.
**Aprendizado principal do desafio:** quando as fontes não conversam diretamente sobre o mesmo ponto, é melhor pedir resumos paralelos em vez de forçar uma síntese — reduz alucinação.

### Prompt 5 — Preservando perguntas de prova / formato professor
**Prompt:** `Liste, no formato de pergunta de prova, os pontos que um professor de Gestão de Serviços provavelmente cobraria sobre NPS com base nestas fontes.`
**Resultado:** gerou uma boa lista de possíveis questões (definição, fórmula, classificação de clientes, faixa de excelência, diferença NPS x SERVQUAL).
**Uso:** esse prompt virou a base do "conjunto de prompts reutilizáveis" abaixo, porque simula muito bem o que cai em avaliação.

---

## 📖 Miniguia de Estudo (Entrega Final)

### 🔹 Resumo Estruturado

**1. O que é o NPS**
Metodologia criada por Frederick Reichheld em 2003, publicada originalmente na Harvard Business Review e depois aprofundada nos livros *The Ultimate Question* (2006) e *The Ultimate Question 2.0* (2011). Mede satisfação e lealdade do cliente a partir de uma pergunta central de recomendação, numa escala de 0 a 10.

**2. Classificação dos clientes**
- **Promotores** (nota 9-10): clientes muito satisfeitos, leais, compram mais e recomendam ativamente a marca.
- **Neutros/Passivos** (nota 7-8): satisfeitos, mas sem lealdade real; podem migrar para a concorrência com facilidade.
- **Detratores** (nota 0-6): insatisfeitos, fazem propaganda negativa, mas trazem feedback valioso sobre falhas.

**3. Fórmula de cálculo**
> NPS = % Promotores − % Detratores

O resultado varia de -100 (todos detratores) a +100 (todos promotores). Os neutros entram na base de cálculo do total de respondentes, mas não entram no numerador da subtração.

**4. Faixas de classificação do resultado**
- Excelente: 75 a 100
- Muito bom / zona de qualidade: 50 a 74
- Razoável: 0 a 49
- Ruim: abaixo de 0 (indicador de alerta — risco de perda de clientes)

**5. "Lucro bom" x "lucro ruim" (Reichheld)**
Reichheld argumenta que nem todo lucro é saudável: lucro obtido às custas da má experiência do cliente ("lucro ruim") corrói a confiança da marca no longo prazo, enquanto o "lucro bom" vem de clientes satisfeitos que compram novamente e indicam a empresa espontaneamente.

**6. NPS e Gestão da Qualidade / Comunicação**
O artigo da Revista Gestão & Gerenciamento conecta o NPS às áreas de Gestão da Qualidade (que busca atender às expectativas das partes interessadas) e Gestão da Comunicação (planejamento, gerenciamento e monitoramento da troca de informação com o cliente). A ideia central é que a qualidade percebida de um serviço é definida pela diferença entre o que o cliente espera e o que ele efetivamente recebe — o mesmo raciocínio por trás do modelo SERVQUAL (GAP = Percepção − Expectativa).

**7. Estudo de caso — Concet Engenharia**
Empresa de projetos de engenharia civil implementou o NPS de forma 100% gratuita, usando apenas ferramentas do Google (Forms para coleta, Sheets para cálculo automático, Drive para armazenamento, Gmail para envio). O caso mostra que pequenas empresas, sem orçamento para plataformas pagas, conseguem estruturar um sistema de medição de satisfação simples e funcional.

**8. Modelo complementar — SERVQUAL**
Desenvolvido por Parasuraman, Zeithaml e Berry (1985/1988), avalia a qualidade do serviço através do GAP entre expectativa e percepção em 5 dimensões: **tangibilidade, confiabilidade, responsividade, segurança e empatia**. Diferente do NPS (uma pergunta, resposta rápida), o SERVQUAL usa 22 afirmativas de expectativa + 22 de percepção, sendo mais detalhado, porém mais trabalhoso de aplicar. O estudo sobre a Uber em Caruaru (PE) usou esse modelo e identificou GAPs críticos em acessibilidade para PCD, descontos e cancelamento de viagens.

---

### 🔹 Glossário

| Termo | Definição |
|---|---|
| **NPS (Net Promoter Score)** | Indicador de satisfação/lealdade calculado pela diferença entre % de promotores e % de detratores |
| **Promotor** | Cliente que dá nota 9 ou 10; altamente satisfeito e propenso a recomendar a marca |
| **Neutro / Passivo** | Cliente que dá nota 7 ou 8; satisfeito, mas sem engajamento ativo com a marca |
| **Detrator** | Cliente que dá nota de 0 a 6; insatisfeito, pode gerar propaganda negativa |
| **Lucro bom** | Lucro gerado por clientes satisfeitos e fidelizados (termo de Reichheld) |
| **Lucro ruim** | Lucro obtido à custa da insatisfação do cliente, prejudicial no longo prazo |
| **KPI** | Key Performance Indicator — indicador-chave de desempenho; o NPS é considerado um dos principais |
| **SERVQUAL** | Escala de avaliação de qualidade em serviços baseada no GAP entre expectativa e percepção, em 5 dimensões |
| **GAP (nos modelos de qualidade)** | Diferença entre o que o cliente esperava e o que percebeu na prática (Percepção − Expectativa) |
| **Customer Centricity** | Filosofia de gestão que coloca o cliente no centro de todas as decisões da empresa |
| **CRM** | Customer Relationship Management — sistema/estratégia de gestão do relacionamento com o cliente |
| **Amostragem por conveniência** | Método de coleta de dados em que participam apenas quem se disponibiliza a responder (usado no estudo do SERVQUAL/Uber) |

---

### 🔹 Prompts Reutilizáveis (templates com papel + contexto + tarefa)

A ideia aqui não é só ter uma pergunta pronta, mas um **template estruturado**: você define um papel para a IA, dá o contexto da sua necessidade (ex: prova amanhã) e só depois pede a tarefa. Isso reduz respostas genéricas e faz o NotebookLM "vestir a camisa" certa antes de responder. Estrutura usada em todos os prompts abaixo:

> **[Papel]** + **[Contexto/situação]** + **[Tarefa específica]** + **[Formato de saída]**

Basta trocar os trechos entre colchetes pela sua necessidade do momento.

---

**1. Revisão relâmpago pré-prova**
```
Atue como professor(a) de Gestão de Serviços e Atendimento ao Cliente.
Contexto: tenho prova amanhã sobre NPS e preciso revisar rápido.
Tarefa: com base nas fontes carregadas, monte um resumo dos 5 pontos que você,
como professor, mais cobraria sobre NPS.
Formato: tópicos curtos, sem enrolação, ordenados por importância.
```

**2. Simulação de prova (questões objetivas)**
```
Atue como professor(a) de Gestão de Serviços elaborando uma prova.
Contexto: quero testar se realmente entendi a classificação de clientes no NPS
(promotores, neutros, detratores) e a fórmula de cálculo.
Tarefa: crie 5 questões de múltipla escolha com base nas fontes, sem repetir o
mesmo subtema em mais de uma questão.
Formato: pergunta + 4 alternativas + gabarito no final (separado, não junto de cada questão).
```

**3. Simulação de prova (questão dissertativa)**
```
Atue como professor(a) de Gestão de Serviços.
Contexto: a prova costuma ter uma questão dissertativa relacionando conceitos
diferentes do conteúdo.
Tarefa: elabore uma questão dissertativa relacionando NPS com Gestão da
Qualidade e Gestão da Comunicação, e escreva também um gabarito-modelo
baseado apenas nas fontes carregadas.
Formato: pergunta primeiro, gabarito depois, separados por linha.
```

**4. Explicação para quem está começando do zero**
```
Atue como um tutor paciente que explica para iniciantes.
Contexto: estou revisando o assunto pela primeira vez e não posso me confundir
com termos técnicos sem explicação.
Tarefa: explique a fórmula do NPS com um exemplo numérico simples, como se eu
nunca tivesse ouvido falar do assunto.
Formato: texto corrido curto, sem jargão sem explicação.
```

**5. Comparação entre modelos (NPS x SERVQUAL)**
```
Atue como um consultor de gestão da qualidade explicando para um cliente leigo.
Contexto: preciso entender quando usar cada modelo de avaliação de qualidade
em serviços.
Tarefa: compare NPS e SERVQUAL apontando: forma de coleta, complexidade de
aplicação e tipo de negócio mais indicado para cada um.
Formato: tabela comparativa.
```

**6. Estudo de caso aplicado**
```
Atue como um analista de qualidade resumindo um caso para a diretoria.
Contexto: preciso apresentar rapidamente como uma empresa real aplicou o NPS
sem gastar dinheiro.
Tarefa: resuma o estudo de caso da empresa Concet Engenharia (fonte
acadêmica), focando só nas ferramentas gratuitas usadas e nos passos seguidos.
Formato: até 5 linhas, tom direto.
```

**7. Autoavaliação de erros comuns**
```
Atue como um auditor de processos de pesquisa de satisfação.
Contexto: quero garantir que, se eu for aplicar um NPS na prática, não cometa
os erros mais comuns.
Tarefa: liste os erros mais citados nas fontes ao aplicar pesquisas de NPS e,
para cada um, sugira uma forma prática de evitá-lo.
Formato: lista "Erro → Como evitar".
```

> 💡 Dica de uso: quanto mais específico o **contexto** (ex: "prova amanhã", "vou apresentar pra diretoria", "nunca vi isso antes"), melhor o NotebookLM calibra o nível de profundidade e o tom da resposta.

---

## 🗂️ Estrutura sugerida do repositório

```
miniguia-estudos-nps/
├── README.md          ← este arquivo (contém todo o conteúdo do desafio)
└── fontes/             ← opcional: PDFs ou links das fontes usadas (se puder disponibilizar)
```

---

*Projeto desenvolvido como parte do Desafio de Projeto da DIO — "Explorando a IA como ferramenta de aprendizagem ativa com NotebookLM".*
