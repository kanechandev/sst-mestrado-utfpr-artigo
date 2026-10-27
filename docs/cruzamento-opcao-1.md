# Cruzamento metodológico para a Opção 1

**Tema:** epidemiologia dos acidentes graves na construção civil, fatores causais de perda de estabilidade e limites dos sistemas abertos de SST  
**Versão:** 1.0 — 27/10/2026  
**Status:** base integrada para a redação do artigo

## 1. Tese central do artigo

Os dados oficiais permitem demonstrar a magnitude e a gravidade dos acidentes registrados na construção civil, mas não permitem contar diretamente, com validade nacional, os acidentes de colapso, desabamento ou desmoronamento. A combinação entre estatística setorial, triagem exploratória da CAT e análise documental de casos do MTE permite avançar em duas frentes: caracterizar o contexto epidemiológico no qual esses eventos ocorrem e explicar, por meio das investigações fiscais, os mecanismos técnicos, humanos e organizacionais associados à perda de estabilidade.

O artigo não deve apresentar agentes como “andaime”, “plataforma” ou “escavação” como sinônimos de colapso. Eles são marcadores candidatos e precisam ser validados por narrativa, situação geradora ou relatório técnico.

## 2. Pergunta, objetivo e contribuição

### Pergunta de pesquisa

Qual é o perfil dos acidentes registrados na construção civil brasileira entre 2022 e 2024, quais fatores causais aparecem nas investigações fiscais de acidentes por soterramento, desabamento e desmoronamento, e quais limitações dos sistemas abertos de SST dificultam a mensuração específica desses eventos?

### Objetivo geral

Analisar, por triangulação quali-quanti, a relação entre a magnitude dos acidentes na construção civil, os indicadores candidatos de perda de estabilidade e os fatores causais identificados em investigações do MTE, discutindo as barreiras de informação para o monitoramento desses eventos.

### Objetivos específicos

1. Descrever a evolução dos acidentes nos CNAEs 41, 42 e 43 em 2022–2024.
2. Caracterizar, na CAT, agentes candidatos, lesões, ocupações, localização, tipo de acidente e indicação de óbito.
3. Classificar os registros candidatos segundo evidência confirmada, provável, candidata ou não classificável.
4. Extrair dos casos do MTE fatores técnicos, humanos, organizacionais e ambientais.
5. Comparar o que cada fonte consegue observar e propor melhorias para o PGR/GRO, a fiscalização e a transparência dos dados.

## 3. Cruzamento das fontes

| Fonte | Unidade observada | O que sustenta | O que não sustenta | Papel no artigo |
|---|---|---|---|---|
| AEAT 2024, tabela 1.1 | Acidentes agregados por CNAE e situação do registro | Magnitude, tendência e denominador setorial | Identificação individual do mecanismo de colapso | Panorama epidemiológico |
| AEAT 2024, tabela 59.2 | Indicadores por atividade econômica | Incidência, mortalidade e letalidade, se extraídas e conferidas | Atribuição de causalidade a um tipo de evento | Comparação de gravidade setorial |
| CAT/INSS aberta | Registro individual disponibilizado pelo INSS | Perfil de agente, lesão, CBO, CNAE, tipo, UF e óbito | Narrativa, situação geradora e confirmação de colapso | Triagem e perfil dos candidatos |
| eSocial, tabelas 14 e 15 | Vocabulário normativo de códigos | Definição de `200020700` e agentes correlatos | Presença desses códigos no CSV aberto da CAT | Crosswalk semântico |
| MTE/SIT | Relatórios e casos investigados | Sequência causal, falhas de controle e condições da obra | Contagem censitária comparável ao AEAT | Análise causal qualitativa |
| Literatura 2021–2025 | Estudos científicos | Modelos de causalidade, métodos de classificação e contexto brasileiro | Evidência direta sobre os casos brasileiros deste estudo | Referencial e discussão |

## 4. Resultados quantitativos já validados

Para os CNAEs 41, 42 e 43, a soma das linhas detalhadas da tabela 1.1 do AEAT apresenta:

| Indicador | 2022 | 2023 | 2024 | Variação 2022–2024 |
|---|---:|---:|---:|---:|
| Total de acidentes | 43.452 | 46.672 | 50.789 | 16,9% |
| Acidentes com CAT registrada | 37.905 | 40.292 | 44.091 | 16,3% |
| Acidentes típicos com CAT registrada | 31.858 | 33.451 | 35.907 | 12,7% |

Esses dados devem ser interpretados como crescimento do volume de acidentes registrados no recorte setorial, não como crescimento comprovado de colapsos. A unidade do AEAT é adequada para contextualização, mas não resolve a pergunta específica sobre o mecanismo do acidente.

## 5. Resultado da inspeção da CAT: o que pode e o que não pode ser afirmado

O arquivo preservado em `data/raw/cat/CAT-2024-12-INSS.zip` contém 9.731 registros e 27 colunas. O cabeçalho apresenta agente causador, datas, CBO, CID-10, CNAE, natureza da lesão, parte do corpo, tipo de acidente, UF e indicação de óbito. Não apresenta campo narrativo explícito nem situação geradora.

Na reprodução direta do filtro por código CNAE iniciado em 41, 42 ou 43, foram encontrados 563 registros, dos quais 6 indicam óbito. Ao acrescentar a regra anterior de incluir qualquer descrição de atividade contendo “Construção”, o total sobe para 575 porque entram 12 registros de construção de embarcações, CNAE 3011/3012. Esses 12 registros não pertencem ao recorte CNAE 41–43 e devem ser excluídos do universo principal.

Uma busca textual no agente causador, usando termos como andaime, plataforma, escavação, forma, escoramento, demolição, estrutura, desabamento e colapso, encontrou 24 registros dentro dos 563 registros dos CNAEs 41–43. A composição observada foi:

- 12 registros com “Andaime, Plataforma”;
- 9 com “Piso de Andaime e Plataforma”;
- 2 com “Escavação, Fosso, Túnel”;
- 1 com “Escavação (Para Edifício...)”.

Nenhum dos 24 registros candidatos indicava óbito no arquivo-piloto. Esse resultado é apenas uma inspeção de viabilidade, pois o arquivo não informa se houve ruptura ou colapso. A diferença entre os 563 registros reproduzidos agora e os 575 registrados na documentação anterior decorre do critério ampliado por descrição da atividade. O total atual de 24 candidatos passa a ser o valor de referência da triagem, enquanto o número anterior de 12 é mantido apenas como registro histórico não reproduzido.

## 6. Modelo de classificação dos eventos

O filtro primário, caso esteja disponível em uma base de registros compatível, é a situação geradora `200020700`: aprisionamento em, sob ou entre desabamento ou desmoronamento de edificação, barreira etc. Como esse campo não está no CSV público da CAT analisada, ele deve ser tratado no artigo como referência normativa e não como variável observada.

Os agentes `30205xxxx` e `30207xxxx` são candidatos secundários. A classificação proposta é:

| Classe | Evento | Evidência mínima |
|---|---|---|
| A | Colapso de estrutura permanente | perda de estabilidade e queda/ruptura documentada |
| B | Colapso de estrutura provisória | ruptura/queda de andaime, forma, cimbramento ou escoramento |
| C | Desabamento de parede/alvenaria | queda do elemento, não apenas impacto contra ele |
| D | Desmoronamento/soterramento | desmoronamento de escavação, talude, fosso ou túnel |
| E | Colapso em demolição/reforma | relação documentada entre a atividade e a perda de estabilidade |
| F | Ruptura/queda de elemento estrutural ou pré-moldado | diferenciação entre falha estrutural e queda de objeto isolado |
| G | Outro evento de perda de estabilidade | evidência documental, mas fora de A–F |
| H | Indeterminado | informação insuficiente |

Cada registro deve receber também `nivel_evidencia` — confirmado, provável, candidato ou não classificável — e `fonte_confirmacao`. A unidade inicial é o registro de trabalhador da CAT. Um evento coletivo pode gerar vários registros e não deve ser contado como vários acidentes sem tratamento específico.

## 7. Matriz qualitativa para os casos do MTE

Os relatórios do MTE devem ser lidos com uma matriz única, evitando transformar o estudo em uma coleção de narrativas:

| Dimensão | Perguntas de extração |
|---|---|
| Evento físico | O que perdeu estabilidade? Houve soterramento, ruptura, queda ou aprisionamento? |
| Projeto/engenharia | Existiam projeto, dimensionamento, escoramento, contenção, sequência executiva e inspeção? |
| Condições do local | Havia sobrecarga, água, chuva, vibração, solo instável, interferências ou alteração da estrutura existente? |
| Gestão e organização | O PGR/GRO contemplava o risco? Havia responsável, planejamento, treinamento, supervisão e comunicação? |
| Trabalho real | Como a tarefa era executada e quais adaptações ocorreram no canteiro? |
| Barreiras | Quais controles deveriam impedir o evento e quais estavam ausentes, inadequados ou degradados? |
| Consequência | Houve morte, lesão grave, múltiplas vítimas ou interrupção da obra? |
| Norma relacionada | Qual requisito da NR-1, NR-18 ou norma técnica aparece como referência? |

O corpus inicial da planilha contém casos de 2018 e 2019. Eles podem ser usados como documentação complementar, mas o artigo deve declarar que não pertencem ao recorte temporal da revisão bibliográfica 2021–2025. Brumadinho e Mariana devem ser excluídos da análise principal se o objeto permanecer limitado a acidentes durante obras, pois são rompimentos de barragem em contexto distinto.

## 8. Integração com a literatura

O estado da arte apoia quatro decisões do desenho:

1. Chen et al. (2023) e Zang et al. (2025) sustentam a leitura sistêmica, com fatores técnicos, humanos, organizacionais e ambientais.
2. Luo, Liu e Qiu (2021), Chen et al. (2022) e Yao, She e Zhou (2024) apoiam o uso de classificação, mineração de texto e associação como referências metodológicas, sem importar automaticamente seus modelos ao presente estudo.
3. Sadeghi et al. (2024) oferece a ponte conceitual com robustez e colapso progressivo, mas não deve ser usado como evidência epidemiológica de acidentes ocupacionais.
4. O estudo brasileiro com CAT na Amazônia (2024), Santos Júnior e Fischer (2023), Paiva et al. (2025), Andersen et al. (2025) e os trabalhos sobre completude do SINAN sustentam o contexto nacional, a escolha das fontes e a discussão de cobertura, subnotificação e comparabilidade.

O diferencial do artigo será combinar a epidemiologia agregada e exploratória com a investigação documental dos mecanismos de acidente e, simultaneamente, tratar a ausência de variáveis específicas como um achado metodológico.

## 9. Estrutura recomendada para a redação

### Introdução

Apresentar a relevância da construção civil, a gravidade dos eventos de perda de estabilidade e o problema de rastreabilidade. Encerrar com a pergunta e os objetivos. A hipótese interpretativa é que a severidade do evento não é acompanhada por igual capacidade de identificação nos dados abertos.

### Referencial teórico e normativo

Organizar em causalidade sistêmica, mecanismos de colapso e estruturas provisórias, NR-1/NR-18/PGR-GRO e sistemas brasileiros de informação. Explicar que a CAT, o AEAT, o SINAN e o eSocial possuem populações, fluxos e variáveis diferentes.

### Métodos

Descrever o estudo retrospectivo, documental e quali-quanti. Separar claramente: (a) AEAT como análise agregada; (b) CAT como triagem de registros; (c) MTE como análise qualitativa; (d) eSocial como vocabulário de referência. Informar regras de inclusão, exclusão, unidade de análise, níveis de evidência e tratamento de duplicidades.

### Resultados

1. Panorama AEAT 2022–2024.
2. Caracterização da CAT-piloto e auditoria de cobertura/variáveis.
3. Classificação dos candidatos, somente após revisão manual e reconciliação dos números.
4. Matriz dos casos MTE e fatores causais recorrentes.
5. Comparação entre variáveis disponíveis e variáveis necessárias para identificar colapso.

### Discussão

Interpretar a triangulação: o AEAT mostra escala, a CAT mostra perfis registrados, e o MTE explica mecanismos e falhas de barreira. Discutir por que agentes candidatos não equivalem a mecanismos confirmados, os efeitos da subnotificação e as consequências para priorização da fiscalização e o PGR/GRO.

### Conclusão

Sustentar três conclusões: (1) houve crescimento dos acidentes registrados no recorte setorial entre 2022 e 2024; (2) os dados abertos disponíveis não permitem estimar diretamente a incidência nacional de colapsos; e (3) a triangulação com investigações do MTE é uma estratégia viável para produzir conhecimento causal e orientar o aperfeiçoamento dos sistemas.

## 10. Quatro pendências críticas para avançar

As quatro tarefas abaixo precisam ser resolvidas antes de apresentar resultados quantitativos definitivos sobre a CAT ou conclusões específicas sobre colapsos. Elas não impedem o início da redação da introdução, do referencial teórico e da metodologia.

### 10.1 Reconciliar a base CAT utilizada — concluído na auditoria do arquivo preservado

O arquivo preservado em `data/raw/cat/CAT-2024-12-INSS.zip` contém 9.731 linhas de dados no CSV, confirmadas pela contagem direta do arquivo. O JSON e o XML presentes no mesmo ZIP correspondem ao mesmo conjunto de registros. O valor anterior de 291.936 foi retirado da documentação por não ser reproduzível a partir do arquivo local e deve ser tratado como erro de registro ou referência a outra extração não preservada.

**Base adotada para a etapa piloto:** competência dezembro de 2024, 9.731 registros, 27 colunas, separador `;`, codificação legada compatível com Latin-1/Windows-1252. A divergência histórica foi documentada e não bloqueia mais o avanço, desde que o artigo apresente essa base como piloto e não como série nacional completa.

### 10.2 Fixar o universo da construção civil

O universo principal deve ser definido pelos CNAEs 41, 42 e 43. A regra adicional baseada no nome da atividade incluiu 12 registros de construção de embarcações, dos CNAEs 3011/3012, que não pertencem ao recorte adotado.

**Produto esperado:** filtro reproduzível por código CNAE, tabela de inclusão e exclusão e declaração explícita de que “construção civil” está sendo operacionalizada pelos grupos 41–43.

### 10.3 Revisar os registros candidatos a colapso — triagem preliminar concluída

A busca textual identificou 24 registros candidatos nos CNAEs 41–43, principalmente relacionados a andaimes, plataformas e escavações. A revisão preliminar não confirmou nenhum colapso. Vinte e dois registros são típicos e dois apresentam características de doença ou trajeto, sendo falsos positivos prováveis para o objeto específico. Os detalhes estão em [`triagem-cat-piloto-2024-12.md`](metodologia/triagem-cat-piloto-2024-12.md).

**Produto produzido:** classificação preliminar dos 24 registros, nível de evidência, identificação dos falsos positivos prováveis e justificativa auditável. A etapa de confirmação documental permanece aberta.

### 10.4 Consolidar o corpus qualitativo do MTE — corpus preliminar definido

Foi definido um corpus preliminar com dois casos centrais de perda de estabilidade confirmada — Center Pav e Cirlene — e dois casos de contraste — Yeshua e Borges — para separar ruptura/queda e queda de andaime de colapso estrutural ou desmoronamento. A matriz está em [`corpus-mte-selecionado.md`](metodologia/corpus-mte-selecionado.md).

**Produto produzido:** corpus delimitado, fontes oficiais identificadas e matriz comparativa inicial. Falta concluir a ficha de extração integral dos quatro relatórios antes da versão final dos resultados qualitativos.

### Atividades que podem ocorrer em paralelo

Enquanto essas quatro tarefas são concluídas, o grupo pode redigir a introdução, o referencial teórico e normativo, a metodologia, a seção de limitações e a estrutura da discussão. A tabela 59.2 do AEAT, o detalhamento das fórmulas e a revisão independente da classificação devem ser concluídos antes da versão final para submissão.

O artigo não deve publicar uma contagem nacional de colapsos baseada apenas no agente causador da CAT ou no código eSocial `200020700`, pois esse código não foi observado no CSV aberto analisado.

