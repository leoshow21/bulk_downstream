# bulk_downstream

## Curso de 5 dias (visao geral)

Este repositorio organiza um curso pratico de 5 dias para analise downstream de RNA-seq bulk usando o dataset GSE298393 (OSD-937). O objetivo e guiar do QC ate redes e interpretacao biologica.

- Dia 1: QC e exploracao (tamanho de biblioteca, genes detectados, correlacao entre amostras, PCA).
- Dia 2: Expressao diferencial com DESeq2 (desenho experimental, contrastes, MA plot e volcano).
- Dia 3: Enriquecimento funcional e PPI (ORA/GSEA com clusterProfiler e rede STRING).
- Dia 4: WGCNA e LIONESS (modulos, relacao com fenotipos e redes individuais).
- Dia 5: Mini-projeto (aplicar o fluxo completo e produzir relatorio com figuras e conclusoes).

## 🧬 Mini-projeto: análise integrada de RNA-seq bulk

Este mini-projeto tem como objetivo guiar os alunos na execução de um fluxo completo de análise de transcriptômica bulk, utilizando o pipeline disponível no repositório bulk_downstream. A proposta é que cada grupo selecione um artigo científico com dados públicos e reproduza — e estenda — a análise por meio de diferentes abordagens complementares: expressão diferencial, enriquecimento funcional e análise de redes.

Os datasets devem ser escolhidos a partir da curadoria disponível na planilha abaixo, garantindo que sejam adequados para todas as etapas propostas:
👉 [https://docs.google.com/spreadsheets/d/14z5cIBxONlymudCIgstCHYNNz1ZlDZc_Szfb71K69ME/edit?gid=0#gid=0](https://docs.google.com/spreadsheets/d/14z5cIBxONlymudCIgstCHYNNz1ZlDZc_Szfb71K69ME/edit?gid=0#gid=0)

Cada aluno deverá selecionar um estudo, compreender o desenho experimental e coletar os dados necessários (contagens ou matrizes normalizadas + metadados). A partir disso, será aplicado o pipeline completo incluindo:

* **DGE (Differential Gene Expression)**
* **GSEA e ORA (enriquecimento funcional)**
* **PPI (redes proteína-proteína via STRINGdb)**
* **WGCNA (redes de co-expressão)**
* **SSN (redes específicas por amostra, abordagem exploratória)**

O objetivo não é apenas executar as análises, mas também avaliar criticamente sua aplicabilidade ao dataset escolhido.

---

## 📊 Pré-requisitos dos datasets

Para garantir que todas as metodologias possam ser aplicadas de forma adequada, os datasets selecionados devem atender aos seguintes critérios mínimos:

* **Número de amostras independentes:**
  O dataset deve conter **pelo menos 30 amostras de "pacientes" distintos** (não apenas replicatas técnicas ou múltiplos tempos do mesmo indivíduo).
  Idealmente:

  * ≥ 30 para análises de expressão diferencial robustas
  * ≥ 50 recomendado para WGCNA confiável

* **Desenho experimental claro:**

  * Pelo menos **duas condições bem definidas** (ex: controle vs doença, tratado vs não tratado)
  * Metadados completos (condição, paciente, possíveis covariáveis)

* **Tipo de dado:**

  * RNA-seq bulk
  * Disponibilidade de **matriz de contagem ou expressão normalizada**

* **Independência das amostras:**

  * Evitar datasets dominados por medidas repetidas (longitudinais com poucos indivíduos)
  * Se houver repetição, deve ser possível modelar (ex: incluir paciente como efeito)

* **Qualidade para análise de redes:**

  * Variabilidade biológica suficiente entre amostras
  * Número de genes adequado após filtragem
  * Ausência de forte viés técnico não corrigido

* **Aplicabilidade das técnicas:**

  * **DGE / GSEA / ORA:** requerem contraste claro entre grupos
  * **PPI:** requer lista de genes diferencialmente expressos
  * **WGCNA:** requer número adequado de amostras independentes e boa variabilidade
  * **SSN:** requer matriz de expressão contínua e múltiplas amostras comparáveis

---

## 🧠 Enfoque do projeto

Os alunos deverão não apenas aplicar o pipeline, mas também discutir:

* Se o dataset escolhido é adequado para cada método
* Limitações (ex: tamanho amostral, heterogeneidade, composição celular)
* Coerência biológica entre os resultados (DEG ↔ GSEA ↔ redes)

---

## 🎯 Resultado esperado

Os resultados do mini-projeto deverão ser apresentados em formato de **mini-artigo ou pôster científico**, simulando uma comunicação real de pesquisa. A ideia é que os alunos não apenas executem as análises, mas organizem os achados de forma clara, objetiva e interpretável.

Cada aluno deverá incluir:

---

### 📊 Figuras principais

* Figuras reproduzindo ou inspiradas no paper original (quando possível)
* Figuras das **novas análises realizadas**, incluindo:

  * PCA / clustering
  * Resultados de DGE (volcano plots, heatmaps)
  * Enriquecimento funcional (GSEA / ORA)
  * Redes PPI (STRING)
  * Módulos de co-expressão (WGCNA)
  * Resultados de redes específicas por amostra (SSN, se aplicável)

---

### 🧪 Metodologia (resumo)

* Descrição breve do dataset (origem, número de amostras, condições)
* Pipeline aplicado com base no repositório bulk_downstream
* Principais decisões analíticas (ex: modelo de DGE, filtros, critérios de seleção)

---

### 📈 Resultados

* Principais achados de cada etapa da análise
* Integração entre resultados (ex: genes → pathways → redes)
* Destaque para padrões relevantes (módulos, hubs, vias enriquecidas)

---

### 💡 Nova abordagem proposta

* Aplicação de pelo menos uma estratégia **não explorada ou pouco explorada no paper original**, como:

  * WGCNA
  * análise de redes (PPI ou diferencial)
  * SSN

* Figuras específicas ilustrando essa abordagem

* Breve explicação do que foi encontrado

---

### 🧠 Discussão

* Comparação entre:

  * resultados do paper original
  * resultados obtidos pelo grupo

* Reflexão sobre:

  * O que a nova metodologia revelou de diferente?
  * Há novos genes, módulos ou vias relevantes?
  * As conclusões do paper são reforçadas ou questionadas?

---

## 📌 Objetivo final

A entrega deve demonstrar:

* Capacidade de **reproduzir e expandir análises científicas**
* Integração entre múltiplas abordagens (estatística + redes)
* Pensamento crítico sobre métodos e resultados

👉 Em essência, o trabalho deve se aproximar de um **mini-paper exploratório**, com narrativa científica clara e suporte visual consistente.
