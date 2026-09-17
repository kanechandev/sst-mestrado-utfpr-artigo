# Próxima etapa — inspeção exploratória da CAT

## Objetivo

Verificar empiricamente quais campos e categorias dos arquivos públicos da CAT podem ajudar a localizar acidentes associados a colapso, desabamento, soterramento, escoramento, formas, cimbramentos, demolição e ruptura de elementos estruturais.

## Fonte de trabalho

Portal oficial do INSS: [Comunicação de Acidente de Trabalho — CAT](https://dadosabertos.inss.gov.br/dataset/inss-comunicacao-de-acidente-de-trabalho-cat).

O portal possui arquivos históricos em formatos XLSX, CSV e ZIP, além de um [glossário/dicionário dos arquivos de CAT](https://dadosabertos.inss.gov.br/dataset/glossarios-dos-arquivos-de-beneficios-plano-de-dados-abertos-jun-2023-a-jun-2025).

### Arquivo-piloto selecionado

- Competência: dezembro de 2024
- Formato publicado: ZIP contendo arquivo tabular
- Recurso oficial: [download CAT dezembro de 2024](https://armazenamento-dadosabertos.s3.sa-east-1.amazonaws.com/PDA_2023_2025/Grupos_de_dados/Comunica%C3%A7%C3%B5es+de+Acidente+de+Trabalho+%E2%80%93+CAT/D.SDA.PDA.005.CAT.202412.ZIP)
- Página de metadados: [recurso no portal do INSS](https://dadosabertos.inss.gov.br/dataset/comunicacoes-de-acidente-de-trabalho-cat-plano-de-dados-abertos-jun-2023-a-jun-2025/resource/8e594e61-e4fc-4249-99fe-5419ca6ba617)

O catálogo informa que o arquivo contém, entre outros, agente causador, data do acidente, CBO, CID, CNAE, município/UF, natureza da lesão, parte do corpo atingida, sexo, tipo de acidente e indicação de óbito. A inspeção do conteúdo e do dicionário ainda é necessária para confirmar nomes, códigos, tipos e campos ausentes.

## Resultado da inspeção estrutural do arquivo-piloto

Os arquivos utilizados nesta etapa agora estão preservados no projeto em `data/raw/`. O ZIP original e o glossário não foram alterados; sua origem, data de download e SHA-256 estão registrados em [`data/README.md`](../data/README.md).

O ZIP foi baixado em 17/09/2026 e está preservado no diretório permanente `data/raw/cat/`. Ele contém:

- `D.SDA.PDA.005.CAT.202412.csv` — arquivo tabular;
- `D.SDA.PDA.005.CAT.202412.json` — metadados;
- `D.SDA.PDA.005.CAT.202412.xml` — representação XML.

O CSV apresenta:

- 27 colunas;
- separador `;`;
- cabeçalho e valores em codificação legada, aparentemente Windows-1252/Latin-1;
- 291.936 registros de pessoas/acidentes na competência de dezembro de 2024;
- nenhum campo narrativo evidente no cabeçalho inspecionado.

### Filtragem preliminar

Foi aplicada uma filtragem exploratória para CNAE iniciado em 41, 42 ou 43, ou nome de atividade contendo “Construção”. O resultado foi:

| Medida | Resultado preliminar |
|---|---:|
| Registros totais no arquivo | 291.936 |
| Registros associados aos CNAEs 41–43 | 575 |
| Indicações de óbito nesses registros | 6 |
| Registros de construção cujo agente continha termos como desabamento, colapso, escoramento, forma ou demolição | 12 |

Esses números são apenas uma inspeção de viabilidade. Não são resultados do artigo, porque ainda não houve conferência do dicionário, padronização dos códigos, verificação de duplicidades nem validação da classificação.

### Observação importante sobre o campo CNAE

No arquivo-piloto, o código aparece em formato resumido — por exemplo, `4120` — e o nome da atividade também aparece abreviado. Será necessário confirmar no dicionário se o primeiro campo é código, descrição, grupo ou classe de CNAE e como ele deve ser comparado com as tabelas do AEAT.

### Observação importante sobre a classificação

Os 12 registros encontrados por palavras no campo de agente causador incluem “Andaime, Plataforma”, entre outros. Isso demonstra que uma busca textual ampla produz falsos positivos: a presença de andaime ou forma não prova que houve colapso. A classificação deverá combinar agente causador, natureza da lesão, tipo de acidente, CNAE e, quando possível, fonte narrativa externa.

## Próximo passo técnico

O glossário foi obtido e lido. A validação dos campos e a primeira tabela de correspondência estão registradas em [`dicionario-cat-validado.md`](metodologia/dicionario-cat-validado.md) e [`classificacao-colapso.md`](metodologia/classificacao-colapso.md). Antes de processar toda a série, a classificação deverá ser testada em uma amostra revisada manualmente.

A base de trabalho recém-incorporada acrescenta o código de situação geradora `200020700` como marcador primário e códigos de agente causador como candidatos secundários. Como o CSV público da CAT piloto não possui a coluna de situação geradora, o próximo teste deve verificar se esses códigos aparecem em outra extração vinculada ao eSocial ou em relatórios de acidentes do MTE. Até essa confirmação, o código é um crosswalk metodológico, não uma variável observada no arquivo CAT piloto.

## Procedimento definido

1. Baixar o dicionário de dados antes dos arquivos massivos.
2. Selecionar uma competência piloto, preferencialmente dezembro de 2024 ou um trimestre de 2024.
3. Confirmar delimitador, codificação, nomes e tipos das colunas.
4. Medir o número de registros e valores ausentes.
5. Listar categorias de agente causador, CNAE, natureza da lesão, tipo de acidente e óbito.
6. Filtrar os CNAEs da construção civil e preservar também uma amostra nacional para comparação.
7. Procurar sinais indiretos de colapso: esmagamento, soterramento, queda de estrutura/objeto, ruptura de formas/escoramentos e eventos de demolição.
8. Registrar falsos positivos e casos que não podem ser classificados.
9. Só então definir o período final, as categorias e a pergunta de pesquisa.

## Campos mínimos a verificar

`data_acidente`, `CNAE`, `CBO`, `agente_causador`, `natureza_lesao`, `parte_corpo_atingida`, `tipo_acidente`, `indica_obito`, `UF/município do acidente` e qualquer campo de descrição, situação geradora ou observação.

## Critério de avanço

A etapa será considerada bem-sucedida se produzir:

- inventário dos campos disponíveis;
- tabela de códigos relevantes;
- estimativa inicial do tamanho da amostra da construção civil;
- lista de limitações da classificação;
- decisão entre estudo nacional, estadual ou estudo de acidentes graves/fatais.

## Cuidados

Os arquivos não devem ser alterados. Devem ser mantidos, quando baixados, com nome original, competência e endereço da fonte. Resultados derivados devem conter data de download e versão do dicionário utilizado.
