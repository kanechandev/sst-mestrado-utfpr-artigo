# Proposta de Reenquadramento Temático e Metodológico do Artigo de Mestrado

**Disciplina:** Segurança do Trabalho  
**Programa:** Pós-Graduação / Mestrado — UTFPR  
**Data da Proposta:** Outubro de 2026  
**Status:** Documento base para alinhamento com o grupo e orientador(a)

---

## 1. Contexto e Diagnóstico do Problema Inicial

### 1.1 A intenção original
O projeto iniciou com o objetivo de investigar e mensurar quantitativamente os acidentes de trabalho decorrentes de **desabamentos e colapsos estruturais** na indústria da construção civil brasileira.

### 1.2 O obstáculo empírico identificado
A auditoria técnica dos dados públicos abertos (AEAT, microdados da CAT/INSS e eSocial) revelou uma barreira intransponível para uma medição censitária direta:
1. **Ausência da variável de Situação Geradora no CSV aberto da CAT:** Embora a tabela do eSocial defina o código específico `200020700` (*"Aprisionamento em/sob/entre desabamento ou desmoronamento de edificação, barreira etc."*), os microdados abertos disponibilizados mensalmente pelo INSS **não trazem essa coluna** em sua extração pública.
2. **Inexistência de campo narrativo/descritivo na CAT aberta:** A base aberta não traz texto livre explicando como o acidente aconteceu.
3. **Ambiguidade do "Agente Causador":** Agentes presentes na CAT como *"Andaime, plataforma"*, *"Edifício ou estrutura"* ou *"Piso de edifício"* registram majoritariamente quedas de trabalhadores em altura (NR-35) ou quedas no mesmo nível (tropeços/escorregões), e não o colapso da estrutura em si. Classificar esses agentes genericamente como "colapso" geraria uma taxa inaceitável de falsos positivos.
4. **Inexistência de microdados individuais públicos do eSocial:** As informações do eSocial com situação geradora são restritas a empregadores e fiscalização, não havendo disponibilização em dados abertos desagregados.

### 1.3 Conclusão preliminar
**Não é cientificamente viável nem metodologicamente ético afirmar uma taxa ou frequência absoluta de "desabamentos estruturais" no Brasil apenas com a CAT pública aberta.** Declarar isso em um artigo acadêmico de mestrado resultaria em imediata fragilidade metodológica na banca avaliadora.

---

## 2. Oportunidade Científica: Como Reenquadrar para o Mestrado

Em pesquisas de pós-graduação, **a identificação de uma lacuna crítica nos sistemas públicos de informação não é um fracasso, mas sim uma contribuição científica de alto impacto**.

O paradoxo entre a **alta letalidade dos eventos de colapso/desmoronamento** e a sua **invisibilidade nos sistemas de dados abertos** de Segurança e Saúde no Trabalho (SST) é exatamente o problema de pesquisa que confere maturidade a um artigo científico.

---

## 3. Quatro Opções de Reenquadramento para o Artigo

### Opção 1 (RECOMENDADA): Abordagem Mista (Quali-Quanti) — Epidemiologia, Fatores Causais e Crítica aos Sistemas de Informação
* **Título Proposto:** *Riscos de Colapso e Perda de Estabilidade na Construção Civil: Epidemiologia dos Acidentes Graves (2022–2024), Análise Causal Multidirecional e os Limites dos Sistemas Abertos de SST*
* **Pergunta de Pesquisa:** *Qual é o perfil epidemiológico dos acidentes de alta severidade potencialmente associados a perda de estabilidade na construção civil brasileira, quais fatores causais explicam sua ocorrência nas investigações fiscais e por que as bases públicas abertas ainda enfrentam barreiras para mensurar esses eventos?*
* **Estrutura Metodológica (3 Camadas):**
  1. **Macro / Epidemiológica:** Análise dos dados do AEAT 2022–2024 (CNAEs 41, 42 e 43) demonstrando a magnitude dos acidentes típicos, mortalidade e letalidade. Nos microdados da CAT, traçar o perfil de gravidade dos agentes candidatos estruturais (andaimes, escavações, estruturas), cruzando com a gravidade das lesões (fraturas, esmagamentos, amputações), ocupações atingidas (CBO) e desfechos fatais.
  2. **Micro / Forense (Qualitativa):** Estudo aprofundado dos relatórios de fiscalização de acidentes fatais do MTE/SIT na categoria *"Soterramento, Desabamento, Desmoronamento"*, categorizando fatores técnicos (falha de escoramento, sobrecarga, intempéries), humanos e organizacionais (falta de ART, ausência de projeto, omissão do PGR/GRO).
  3. **Epistemológica / Gestão de SST:** Discussão crítica sobre o descompasso entre a legislação (NR-1, NR-18, eSocial) e a transparência em dados abertos, apontando recomendações para o aprimoramento dos sistemas e da gestão de riscos nas obras.
* **Por que adotar:** É a abordagem mais completa, robusta e diretamente publicável em periódicos nacionais e internacionais (ex.: *Revista Brasileira de Saúde Ocupacional - RBSO*, *Safety Science* ou periódicos da área de Engenharia/Construção).

---

### Opção 2: Foco em Estruturas Provisórias (Andaimamento e Cimbramento) e Trabalho em Altura
* **Título Proposto:** *Segurança em Estruturas Provisórias na Construção Civil: Análise de Severidade de Acidentes Envolvendo Andaimes e Plataformas (2022–2024) e Interfaces com as NRs 18 e 35*
* **Pergunta de Pesquisa:** *Qual o perfil de gravidade dos acidentes de trabalho com andaimes e plataformas na construção civil brasileira e como as exigências normativas de dimensionamento e estabilidade impactam a mitigação desses eventos?*
* **Abordagem:** Focar nos registros da CAT que envolvem "Andaime, Plataforma" e "Escadas", comparando sua letalidade e severidade clínica com os demais agentes causadores da construção civil, correlacionando com as NRs de segurança estrutural de canteiro.

---

### Opção 3: Foco em Obras de Infraestrutura, Geotecnia e Escavações (Soterramentos)
* **Título Proposto:** *Acidentes Ocupacionais por Soterramento e Desmoronamento em Serviços de Escavação e Infraestrutura: Análise de Gravidade e Conformidade com a NR-18*
* **Pergunta de Pesquisa:** *Quais são os perfis de morbidade e os fatores determinantes para a alta letalidade de acidentes em escavações e obras subterrâneas (CNAEs 42 e 4313/4391) no Brasil?*
* **Abordagem:** Isolar as obras de terraplenagem, redes de tubulação e fundações. Os acidentes em valas sem escoramento representam uma das formas mais severas e evitáveis de desmoronamento na construção civil.

---

### Opção 4: Foco em Demolição, Reformas e Intervenções em Estruturas Existentes
* **Título Proposto:** *Riscos Ocupacionais e Perda de Estabilidade em Obras de Reforma e Demolição: Análise Estatística (CNAE 4311) e Requisitos de Gestão de Riscos Estruturais*
* **Pergunta de Pesquisa:** *Como as atividades de demolição e preparação de canteiros se comportam em termos de frequência e gravidade de acidentes frente às obras convencionais de edifícios?*
* **Abordagem:** Dialoga fortemente com as linhas de pesquisa de restauração, estruturas existentes, patologias e concreto/madeira submetidos a danos prévios (como incêndio).

---

## 4. Estrutura Padrão Sugerida para o Artigo Científico (Opção 1)

```
1. INTRODUÇÃO
   - Cenário da construção civil brasileira: relevância socioeconômica e alta acidentabilidade.
   - A criticidade dos eventos de perda de estabilidade e colapso (alta letalidade e impacto sistêmico).
   - O problema da pesquisa: o descompasso entre a severidade desses eventos e sua rastreabilidade nos registros oficiais.
   - Objetivos do artigo.

2. REFERENCIAL TEÓRICO E NORMATIVO
   - Modelos de causalidade de acidentes na construção civil (fatores técnicos, humanos e organizacionais - STAMP / AcciMap).
   - O quadro regulamentador brasileiro: NR-18 (condições e meio ambiente de trabalho na indústria da construção), NR-1 (PGR/GRO) e normas estruturais da ABNT.
   - Sistemas de informação em SST no Brasil: AEAT, CAT, SINAN, eSocial e os desafios de completude e subnotificação na literatura recente (2021–2025).

3. METODOLOGIA
   - Desenho do estudo: pesquisa mista (quali-quantitativa), retrospectiva, documental e descritiva.
   - Fontes de dados e recorte temporal:
     * AEAT 2022–2024: séries temporais agregadas por CNAE (41, 42 e 43).
     * Microdados da CAT (INSS): variáveis de gravidade, lesão, ocupação e agentes candidatos.
     * Relatórios técnicos de fiscalização do MTE (2016–2025): casos de soterramento/desabamento.
   - Critérios de triagem e classificação de eventos de perda de estabilidade.
   - Limitações metodológicas declaradas e controle de viés de seleção.

4. RESULTADOS
   - 4.1 Panorama Setorial da Construção Civil (2022–2024): evolução dos acidentes totais, com CAT e típicos.
   - 4.2 Perfil Epidemiológico dos Agentes Candidatos Estruturais: lesões predominantes, ocupações mais vulneráveis e taxa de óbito.
   - 4.3 Análise Qualitativa dos Fatores Causais em Casos Fatais do MTE: falhas de escoramento, falta de projeto, ausência de contenção e intempéries.
   - 4.4 Avaliação Crítica dos Sistemas de Notificação: a barreira da ausência do campo de situação geradora nos dados abertos.

5. DISCUSSÃO
   - A "invisibilidade estatística" dos colapsos e suas consequências para a política pública de SST.
   - Falhas sistêmicas de engenharia e gestão de segurança no canteiro de obras.
   - Triangulação de achados: o que a estatística não mostra, a investigação forense do MTE revela.
   - Recomendações práticas para PGR de obras e para o aperfeiçoamento das bases abertas de dados do governo federal.

6. CONCLUSÃO
   - Síntese das contribuições do estudo.
   - Recomendações para a fiscalização, empresas e academia.
```

---

## 5. Próximos Passos Imediatos para o Grupo

1. **Reunião de Alinhamento:** Discutir com os colegas de grupo e com o(a) docente/orientador(a) qual das 4 opções atende melhor ao escopo do mestrado.
2. **Consolidação dos Dados Quantitativos:** Definir se a base microdados da CAT será analisada para uma amostra piloto (como 2024 ou triênio 2022–2024) combinada com as tabelas consolidadas do AEAT.
3. **Seleção dos Casos Qualitativos do MTE:** Rastrear 3 a 5 relatórios de acidentes fatais por desmoronamento/escoramento no portal do MTE para estruturar a análise qualitativa forense.
4. **Redação do Artigo:** Distribuir as seções do artigo entre os membros da equipe.
