# Diário exploratório — acidentes de trabalho e colapso de estruturas

**Projeto:** artigo do grupo de Segurança do Trabalho — UTFPR  
**Data do registro:** 17/09/2026  
**Etapa:** exploração de fontes e definição preliminar do objeto

## 1. Contexto e problema inicial

O grupo busca um tema de artigo que dialogue com restauração de edificações de madeira, incêndio, concreto submetido ao fogo e segurança do trabalho. A ideia inicial foi estudar acidentes envolvendo desabamento ou colapso de estruturas durante a fase de obras.

A hipótese de trabalho adotada nesta etapa é que os registros oficiais não necessariamente usam “desabamento” como categoria única. O fenômeno pode aparecer associado a escavações, soterramentos, formas, cimbramentos, escoramentos, demolições, paredes, elementos pré-moldados e estruturas parcialmente executadas.

## 2. Decisão exploratória provisória

O objeto será tratado, inicialmente, como:

> Acidentes de trabalho associados à perda de estabilidade e ao colapso de estruturas na construção civil.

Não se deve afirmar, antes da inspeção dos microdados, que será possível contar todos os “desabamentos” no Brasil. A pesquisa deverá distinguir:

1. uma análise estatística ampla da construção civil; e
2. uma identificação/classificação específica dos eventos relacionados a colapso.

## 3. Fontes externas verificadas

### AEAT — Ministério da Previdência Social

Fonte oficial: [AEAT 2024](https://www.gov.br/previdencia/pt-br/assuntos/previdencia-social/arquivos/AEAT-2024).

Permite consultar acidentes por CNAE, situação do registro, motivo, UF, óbitos, incapacidade e indicadores. É adequada para a série histórica e para o contexto setorial, mas é uma fonte predominantemente agregada e não deve ser usada sozinha para localizar eventos individuais de colapso.

### CAT — INSS

Fonte oficial: [Dados abertos de Comunicação de Acidente de Trabalho](https://dadosabertos.inss.gov.br/dataset/inss-comunicacao-de-acidente-de-trabalho-cat).

O portal disponibiliza arquivos mensais em CSV/ZIP e dicionário de dados. O catálogo informa campos como agente causador, data, CBO, CID, CNAE, município e UF do acidente, natureza da lesão, parte do corpo atingida, sexo, tipo de acidente e indicação de óbito.

**Ponto a confirmar na inspeção:** se os arquivos possuem descrição narrativa e/ou situação geradora suficientemente detalhada. A existência de “agente causador” não garante, por si só, a identificação de colapso estrutural.

### SINAN — Ministério da Saúde/DATASUS

Fontes oficiais: [Acidente de trabalho grave — SINAN](https://www.portalsinan.saude.gov.br/drt-acidente-de-trabalho-grave) e [dados de agravos de notificação](https://www.gov.br/saude/pt-br/acesso-a-informacao/sic/dados-em-transparencia-ativa/svsa/agravos-de-notificacoes).

É complementar à CAT por abranger notificações de acidentes de trabalho graves na rede de saúde. A ficha prevê tipo de acidente, outros trabalhadores atingidos, evolução do caso, atendimento e descrição sumária da ocorrência. Deve ser analisada separadamente, pois sua população, fluxo de notificação e cobertura não são idênticos aos da Previdência.

### SmartLab — MPT/OIT

Fonte: [SmartMap do Observatório de Segurança e Saúde no Trabalho](https://smartlab.mpt.mp.br/sst/smartmap).

Permite exploração por período, setor econômico, agente causador, natureza da lesão, localidade e fonte de dados. A versão consultada informa série de 2012 a 2024 e combina CAT/AEAT, benefícios previdenciários e SINAN em diferentes visualizações.

É excelente para explorar o recorte e comparar resultados, mas os números tratados pelo painel não substituem a documentação dos arquivos originais.

### Ministério do Trabalho e Emprego — análises técnicas

Foi localizada a avaliação [Acidentes do trabalho no Brasil — 2016 a 2025](https://www.gov.br/trabalho-e-emprego/pt-br/assuntos/inspecao-do-trabalho/seguranca-e-saude-no-trabalho/canpat-2/canpat-2025/acidentes-de-trabalho-2016-a-2025.pdf/).

O relatório usa CAT/eSocial e apresenta recortes por CNAE, ocupação, acidentes, óbitos e indicadores. Também pode orientar a busca posterior por relatórios de análise de acidentes graves e fatais, que tendem a explicar melhor a sequência causal do evento.

## 4. Limitações já identificadas

- CAT, AEAT, SINAN e SmartLab não representam exatamente a mesma população.
- Trabalhadores informais e acidentes não notificados podem estar sub-representados.
- A data de extração e a maturação dos registros podem alterar totais de anos recentes.
- “Construção civil” precisa ser operacionalizada por CNAE; a escolha entre CNAE 41, 42 e 43 altera a população estudada.
- Um acidente pode atingir vários trabalhadores, portanto é necessário distinguir registro do acidente e pessoa acidentada.
- A classificação de colapso será parcialmente construída pelos pesquisadores e deverá ter critérios explícitos e auditáveis.

## 5. Classificação provisória para leitura dos registros

| Código | Categoria exploratória |
|---|---|
| A | Colapso de estrutura permanente |
| B | Colapso de forma, cimbramento ou escoramento |
| C | Desabamento de parede ou alvenaria |
| D | Desmoronamento de escavação ou talude / soterramento |
| E | Colapso durante demolição ou reforma |
| F | Queda ou ruptura de elemento estrutural/pré-moldado |
| G | Outro evento relacionado à perda de estabilidade |
| H | Indeterminado / não classificável |

Esta classificação é provisória e somente será consolidada após a leitura do dicionário e de uma amostra dos registros.

## 6. Registro da decisão metodológica

Até aqui, a hipótese mais promissora é um estudo descritivo, retrospectivo e documental, com duas camadas:

1. caracterização dos acidentes na construção civil por CNAE, período, UF, lesão e óbito; e
2. classificação específica dos eventos potencialmente relacionados à perda de estabilidade/colapso.

O recorte temporal inicial recomendado para a primeira inspeção é **2016–2024**: há continuidade recente nos dados CAT, cobertura completa no AEAT 2024 e possibilidade de comparação com o SmartLab. O ano de 2025 poderá ser incorporado depois, se a maturação dos registros for considerada adequada.

## 7. Estado da arte

O grupo decidiu trabalhar com o estado da arte dos últimos cinco anos. Para evitar incluir seis anos-calendário, foi adotado provisoriamente o intervalo **2021–2025**, os cinco anos completos mais recentes na data desta pesquisa. A busca exploratória inicial e a estratégia de triagem estão registradas em [`estado-da-arte-2021-2025.md`](estado-da-arte-2021-2025.md).

Essa decisão se refere à revisão bibliográfica. Ela não obriga que a série estatística da CAT tenha exatamente o mesmo intervalo; o período dos dados será escolhido conforme disponibilidade, comparabilidade e maturação dos registros.

## 8. Incorporação da base estatística de colapso

Em 17/09/2026 foi incorporado ao diretório do projeto o arquivo [`base_estatistica_colapso_desabamento_construcao.xlsx`](../base_estatistica_colapso_desabamento_construcao.xlsx). A auditoria das abas, do hash e das limitações está em [`base-estatistica-colapso.md`](metodologia/base-estatistica-colapso.md).

A planilha melhora a exploração ao separar um marcador primário de situação geradora (`200020700`), candidatos por agente causador e falsos positivos esperados. Os códigos foram confrontados semanticamente com as tabelas oficiais do eSocial, mas ainda não foram ligados a uma variável existente no CSV público piloto da CAT. Os totais do AEAT presentes na planilha permanecem provisórios até recálculo na fonte original.

Em 17/09/2026 foi realizada a primeira triagem bibliográfica. Foram selecionados artigos sobre causalidade de acidentes, colapso de edificações, análise sistêmica, escavações, estruturas temporárias, colapso progressivo e uso de CAT no Brasil. A seleção, os links oficiais e os arquivos locais disponíveis estão em [`referencias-estado-arte.md`](referencias-estado-arte.md). Os PDFs de acesso aberto foram salvos em `data/referencias/artigos/`; nos casos em que a editora não disponibilizou o PDF por acesso direto, foi preservado o registro bibliográfico e o endereço oficial.
