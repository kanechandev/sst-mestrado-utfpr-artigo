# Dados brutos do projeto

Os arquivos desta pasta são cópias locais das fontes públicas utilizadas na exploração. Não editar, renomear ou substituir os arquivos sem registrar a nova versão no diário do projeto.

## Ponto atual da pesquisa

O grupo está investigando acidentes de trabalho associados à perda de estabilidade, desabamento, desmoronamento e colapso durante a construção civil. Nesta etapa, já existem insumos suficientes para iniciar uma análise exploratória e estruturar o artigo, mas ainda não para afirmar a frequência nacional de acidentes de colapso estrutural.

### O que já está disponível

- estatísticas iniciais do AEAT para os CNAEs 41, 42 e 43, referentes a 2022–2024;
- microdados piloto da CAT/INSS e o glossário correspondente;
- artigos nacionais e internacionais sobre acidentes na construção e o cenário brasileiro;
- tabela operacional de classificação dos eventos relacionados a colapso;
- casos qualitativos de desabamento, desmoronamento e soterramento em relatórios do MTE;
- cruzamento exploratório com códigos do eSocial, incluindo o marcador primário `200020700`.

### O que a análise já permite

O desenho atual permite combinar:

1. análise descritiva dos acidentes na construção civil por CNAE, ano, tipo de acidente, óbito e localização; e
2. classificação exploratória dos eventos potencialmente relacionados a colapso, com validação por fontes narrativas e relatórios técnicos.

### Limitação central

O CSV público piloto da CAT não apresenta, no cabeçalho, um campo explícito de “situação geradora”. Por isso, agentes como andaime, escavação ou edifício são indicadores candidatos, não provas de colapso. O código `200020700` é um marcador metodológico promissor, mas ainda precisa ser localizado em uma base de registros que contenha essa variável, como uma extração vinculada ao eSocial.

Consequentemente, o projeto ainda não deve declarar que ocorreram “X acidentes de colapso” no Brasil. Os números setoriais e os eventos classificados devem ser apresentados como análise exploratória até a validação da fonte, dos códigos e dos falsos positivos.

### Próximas validações

1. Recalcular os totais de 2022–2024 diretamente nas tabelas oficiais do [AEAT](https://www.gov.br/previdencia/pt-br/assuntos/previdencia-social/arquivos/AEAT-2024).
2. Confirmar a versão das tabelas de agente causador e situação geradora na documentação oficial do [eSocial](https://www.gov.br/esocial/pt-br/documentacao-tecnica/leiautes-esocial-versao-s-1-3-nt-07-2026/tabelas.html/view).
3. Verificar a disponibilidade dos códigos nos microdados que serão usados na análise.
4. Revisar manualmente uma amostra dos candidatos, principalmente andaimes, plataformas e escavações.
5. Registrar as decisões, versões e resultados no [diário exploratório](../docs/diario-exploratorio.md).

Os detalhes metodológicos estão em [`docs/metodologia/base-estatistica-colapso.md`](../docs/metodologia/base-estatistica-colapso.md), [`docs/metodologia/classificacao-colapso.md`](../docs/metodologia/classificacao-colapso.md) e [`docs/cenario-brasil-2021-2025.md`](../docs/cenario-brasil-2021-2025.md).

## Glossário do recorte e das fontes

### CNAEs 41, 42 e 43

CNAE significa **Classificação Nacional de Atividades Econômicas**. Neste projeto, os códigos são usados para delimitar as atividades da construção civil:

| Código | Grupo de atividade | O que representa no estudo |
|---:|---|---|
| **41** | Construção de edifícios | Incorporação e construção de edifícios residenciais, comerciais e outros edifícios |
| **42** | Obras de infraestrutura | Rodovias, ferrovias, pontes, viadutos, redes de água e esgoto, energia, telecomunicações e outras obras de engenharia civil |
| **43** | Serviços especializados para construção | Demolição, preparação do terreno, perfurações, terraplenagem, instalações elétricas e hidráulicas, acabamento e outros serviços especializados |

O recorte 41–43 representa o setor da construção em sentido amplo. A planilha também apresenta atividades em níveis mais detalhados, como `4120` — construção de edifícios. O CNAE identifica a atividade econômica do empregador; ele não descreve, sozinho, o mecanismo do acidente nem prova que houve colapso.

### CAT

**CAT** significa **Comunicação de Acidente de Trabalho**. É o registro usado para comunicar à Previdência Social a ocorrência de acidente de trabalho, acidente de trajeto ou doença ocupacional. Na base pública utilizada, cada registro corresponde a uma comunicação disponibilizada pelo INSS e pode conter data, agente causador, atividade econômica, natureza da lesão, parte do corpo atingida, tipo de acidente e indicação de óbito.

A CAT é útil para analisar frequência, perfil e gravidade dos acidentes registrados. Ela não representa necessariamente todos os acidentes ocorridos, pois depende da comunicação e da cobertura do sistema. No arquivo piloto analisado, não foi identificado um campo narrativo explícito capaz de confirmar sozinho um desabamento ou colapso.

### INSS

**INSS** significa **Instituto Nacional do Seguro Social**. É a autarquia federal responsável pela administração de benefícios do Regime Geral de Previdência Social e pela divulgação da base pública de CAT utilizada nesta exploração.

Neste projeto, “dados do INSS” não significa que o INSS tenha investigado tecnicamente cada acidente. Significa que os registros foram disponibilizados ou organizados pela Previdência Social a partir das comunicações e informações previdenciárias.

### MTE

**MTE** significa **Ministério do Trabalho e Emprego**. O ministério atua, entre outras áreas, na inspeção do trabalho e na produção de informações e relatórios técnicos sobre segurança e saúde no trabalho.

Os relatórios e casos do MTE são importantes porque podem fornecer a narrativa do acidente, sua sequência causal, as condições da obra e as falhas de segurança. Por isso, são usados no projeto para validar candidatos identificados nas bases estatísticas, e não para substituir automaticamente os dados da CAT ou do AEAT.

### Código `200020700`

O código `200020700` pertence ao conjunto de códigos de **situação geradora do acidente** utilizado como referência metodológica nas tabelas do eSocial. Sua descrição é:

> Aprisionamento em/sob/entre desabamento ou desmoronamento de edificação, barreira etc.

Por ser específico, ele foi definido na classificação do projeto como **marcador primário** de evento relacionado a desabamento ou desmoronamento. Isso significa que, se o código estiver presente na base de registros analisada, o caso deve ser selecionado para revisão como forte candidato ao grupo de colapso.

O código não deve ser confundido com uma contagem pronta de acidentes. Ele precisa estar efetivamente presente na base utilizada, e o registro ainda deve ser conferido quanto ao CNAE, à fase da obra, à existência de colapso estrutural e à possibilidade de duplicidade. O CSV público piloto da CAT analisado pelo grupo não continha esse campo no cabeçalho; portanto, por enquanto, o código é um critério operacional derivado das tabelas do eSocial, não uma variável observada naquele arquivo CAT.

Referência: [tabelas oficiais do eSocial](https://www.gov.br/esocial/pt-br/documentacao-tecnica/leiautes-esocial-versao-s-1-3-nt-07-2026/tabelas.html/view).

## Arquivos atualmente utilizados

| Arquivo | Fonte | Competência/versão |
|---|---|---|
| `raw/cat/CAT-2024-12-INSS.zip` | [INSS — CAT](https://dadosabertos.inss.gov.br/dataset/comunicacoes-de-acidente-de-trabalho-cat-plano-de-dados-abertos-jun-2023-a-jun-2025/resource/8e594e61-e4fc-4249-99fe-5419ca6ba617) | dezembro/2024 |
| `raw/glossario/Glossario-CAT-INSS.xlsx` | [INSS — glossário da CAT](https://dadosabertos.inss.gov.br/pt_PT/dataset/glossarios-dos-arquivos-de-beneficios-plano-de-dados-abertos-jun-2023-a-jun-2025/resource/d5c33f7a-73a3-43f6-bcf5-cce07eef8c8c?inner_span=True) | atualização indicada no portal: 11/09/2024 |
| `../base_estatistica_colapso_desabamento_construcao.xlsx` | Arquivo de trabalho fornecido ao projeto; fontes declaradas na própria planilha: AEAT, INSS/CAT, eSocial e MTE/SIT | AEAT 2022–2024; arquivo recebido em 17/09/2026 |

## Proveniência

Data de download local: 17/09/2026. O ZIP da CAT contém o CSV, JSON e XML publicados pelo INSS. Os arquivos não foram transformados; as análises devem ser reproduzíveis a partir deles.

### SHA-256

```text
495c80abf2db5d57bd085c4ebe8a3d54e70956570d80ca7aaddd9865a832ade5  raw/cat/CAT-2024-12-INSS.zip
a25c4ddf30ad62a80cbfa079d81034ad7ec35c88102698f0a39f550585e9dedc  raw/glossario/Glossario-CAT-INSS.xlsx
91565928d82a86e28535f34b72b470ace39fdd56c0346d1c8ea241fffeb9aeff  base_estatistica_colapso_desabamento_construcao.xlsx
```

## Observação sobre a planilha de trabalho

A planilha é uma base derivada/de trabalho, não uma publicação oficial independente. Seus valores estatísticos devem ser conferidos nas tabelas originais do AEAT antes da submissão. O cruzamento de códigos e a classificação exploratória nela contidos foram preservados e auditados em [`docs/metodologia/base-estatistica-colapso.md`](../docs/metodologia/base-estatistica-colapso.md).
