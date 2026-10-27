# Acidentes graves na construção civil — artigo UTFPR

Repositório de pesquisa e redação do artigo da disciplina de Segurança do Trabalho do programa de mestrado da Universidade Tecnológica Federal do Paraná (UTFPR).

## Objeto da pesquisa

O projeto investiga acidentes de trabalho graves e fatais associados à perda de estabilidade, estruturas provisórias, desabamentos, desmoronamentos e soterramentos na construção civil brasileira.

O estudo não estima uma incidência nacional de colapsos a partir de agentes causadores da CAT. A auditoria dos dados públicos mostrou que a base-piloto da CAT/INSS não possui narrativa nem variável pública de situação geradora capaz de confirmar isoladamente esse mecanismo. Por isso, o artigo combina:

1. análise epidemiológica agregada do AEAT para os CNAEs 41, 42 e 43;
2. triagem exploratória de registros individuais da CAT/INSS;
3. análise causal de relatórios oficiais do Ministério do Trabalho e Emprego (MTE/SIT); e
4. discussão das limitações e dos requisitos de melhoria dos sistemas abertos de SST.

## Estado atual

O artigo está estruturado em [`docs/rascunho-artigo-opcao-1.md`](docs/rascunho-artigo-opcao-1.md), com citações autor-data no corpo e a lista completa de referências ao final do próprio documento.

### Resultados quantitativos consolidados

| Indicador | 2022 | 2023 | 2024 | Variação 2022–2024 |
|---|---:|---:|---:|---:|
| Total de acidentes nos CNAEs 41–43 | 43.452 | 46.672 | 50.789 | +16,9% |
| Acidentes com CAT registrada | 37.905 | 40.292 | 44.091 | +16,3% |
| Acidentes típicos com CAT registrada | 31.858 | 33.451 | 35.907 | +12,7% |

Os valores foram conferidos na tabela 1.1 do AEAT 2024. O detalhamento da auditoria está em [`docs/validacao-aeat-esocial-mte.md`](docs/validacao-aeat-esocial-mte.md).

### CAT-piloto

Foi analisado o arquivo público de dezembro de 2024. Ele contém 9.731 registros e 27 colunas. O filtro por código CNAE iniciado em 41, 42 ou 43 encontrou 563 registros, dos quais 6 tinham indicação de óbito. A busca exploratória por agentes causadores encontrou 24 candidatos relacionados principalmente a andaimes, plataformas e escavações.

Esses 24 registros são candidatos de triagem, não acidentes confirmados por colapso. O arquivo não apresenta campo narrativo nem situação geradora observável.

### Corpus qualitativo do MTE

O corpus contém quatro relatórios oficiais:

- **Center Pav:** caso central de desmoronamento de vala e soterramento;
- **Cirlene:** caso central de ruptura de parede de moega e soterramento;
- **Yeshua:** caso de contraste envolvendo ruptura de telha e queda em altura;
- **Borges:** caso de contraste envolvendo queda de andaime suspenso.

Os arquivos, links oficiais e hashes estão documentados em [`data/referencias/mte/README.md`](data/referencias/mte/README.md).

## Dados e proveniência

Os dados brutos preservados no projeto são cópias locais de fontes públicas. Não devem ser alterados, renomeados ou substituídos sem registrar a nova versão, a origem e o hash correspondente.

| Fonte | Uso no projeto | Documentação |
|---|---|---|
| AEAT 2024 | Totais e evolução dos acidentes nos CNAEs 41–43 | [`docs/validacao-aeat-esocial-mte.md`](docs/validacao-aeat-esocial-mte.md) |
| CAT/INSS | Perfil individual e triagem de agentes candidatos | [`docs/metodologia/triagem-cat-piloto-2024-12.md`](docs/metodologia/triagem-cat-piloto-2024-12.md) |
| Glossário da CAT | Interpretação dos campos e códigos | [`docs/metodologia/dicionario-cat-validado.md`](docs/metodologia/dicionario-cat-validado.md) |
| eSocial | Referencial semântico para situação geradora e agentes | [`docs/validacao-aeat-esocial-mte.md`](docs/validacao-aeat-esocial-mte.md) |
| MTE/SIT | Narrativas, mecanismos e fatores causais | [`docs/metodologia/corpus-mte-selecionado.md`](docs/metodologia/corpus-mte-selecionado.md) |
| Literatura científica | Referencial teórico e estado da arte | [`docs/referencias-estado-arte.md`](docs/referencias-estado-arte.md) |

Os arquivos brutos, fontes, datas de acesso e hashes estão descritos em [`data/README.md`](data/README.md). A planilha consolidada de trabalho é [`base_estatistica_colapso_desabamento_construcao.xlsx`](base_estatistica_colapso_desabamento_construcao.xlsx).

## Organização do repositório

```text
.
├── README.md
├── base_estatistica_colapso_desabamento_construcao.xlsx
├── data/
│   ├── README.md
│   ├── raw/                         # CAT/INSS e glossário preservados
│   └── referencias/
│       ├── artigos/                 # Artigos e materiais bibliográficos
│       └── mte/                     # Relatórios técnicos e hashes
└── docs/
    ├── rascunho-artigo-opcao-1.md   # Artigo em desenvolvimento
    ├── referencias-bibliograficas.md # Cópia de apoio da bibliografia
    ├── proposta-artigo-mestrado.md
    ├── cruzamento-opcao-1.md
    ├── diario-exploratorio.md
    ├── cenario-brasil-2021-2025.md
    ├── estado-da-arte-2021-2025.md
    ├── referencias-estado-arte.md
    ├── validacao-aeat-esocial-mte.md
    ├── proxima-etapa-inspecao-cat.md
    └── metodologia/
        ├── base-estatistica-colapso.md
        ├── classificacao-colapso.md
        ├── corpus-mte-selecionado.md
        ├── dicionario-cat-validado.md
        └── triagem-cat-piloto-2024-12.md
```

## Documentos principais

- [Artigo completo](docs/rascunho-artigo-opcao-1.md): texto, resultados, discussão, conclusões e referências.
- [Proposta do artigo](docs/proposta-artigo-mestrado.md): problema, objetivos e alternativas de enquadramento.
- [Cruzamento da opção 1](docs/cruzamento-opcao-1.md): consolidação da estratégia escolhida.
- [Diário exploratório](docs/diario-exploratorio.md): decisões, auditorias e mudanças metodológicas.
- [Validação das fontes](docs/validacao-aeat-esocial-mte.md): conferência do AEAT, eSocial e MTE.
- [Classificação dos eventos](docs/metodologia/classificacao-colapso.md): categorias, evidências e controle de falsos positivos.
- [Corpus do MTE](docs/metodologia/corpus-mte-selecionado.md): casos centrais e casos de contraste.
- [Triagem da CAT](docs/metodologia/triagem-cat-piloto-2024-12.md): procedimento e resultados da competência piloto.

## Limitações que devem permanecer explícitas

- A CAT foi analisada em uma única competência mensal.
- Os registros da CAT são comunicações individuais e não equivalem necessariamente a acidentes independentes.
- A ausência de confirmação entre os 24 candidatos não demonstra ausência de colapsos; demonstra insuficiência dos campos disponíveis para confirmá-los.
- O corpus do MTE é intencional e não permite estimar frequência nacional.
- O código eSocial `200020700` é um marcador metodológico; não foi observado no CSV público piloto da CAT.
- AEAT, CAT, SINAN e eSocial possuem populações, fluxos e unidades de análise diferentes.

## Próximas ações

1. Revisar o artigo com o orientador e adequá-lo ao periódico ou modelo de submissão escolhido.
2. Conferir a formatação final das referências conforme a norma exigida.
3. Produzir os gráficos e tabelas finais a partir da planilha auditada.
4. Fazer uma revisão final de citações, números, links, hashes e arquivos preservados.
5. Registrar no diário qualquer alteração posterior à versão preparada para commit.

## Preparação para commit

Antes do commit, conferir:

- [ ] o artigo abre corretamente e contém a lista completa de referências ao final;
- [ ] os dados brutos e relatórios do MTE estão preservados com proveniência;
- [ ] os hashes registrados correspondem aos arquivos locais;
- [ ] os números do artigo coincidem com a documentação metodológica;
- [ ] não há arquivos temporários ou resultados não documentados;
- [ ] alterações pendentes de outros documentos foram revisadas pelo grupo.

Este repositório é de pesquisa e redação. A classificação de acidentes e as conclusões devem ser interpretadas dentro das limitações documentadas, sem apresentar candidatos exploratórios como contagem nacional validada de colapsos.
