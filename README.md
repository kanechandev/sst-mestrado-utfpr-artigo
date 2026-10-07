# Pesquisa e Artigo Científico em Segurança do Trabalho — UTFPR

Repositório de desenvolvimento do artigo científico para a disciplina de **Segurança do Trabalho** do programa de pós-graduação (Mestrado) da **Universidade Tecnológica Federal do Paraná (UTFPR)**.

---

## 1. Visão Geral e Objeto da Pesquisa

O projeto investiga os **acidentes de trabalho graves e fatais associados à perda de estabilidade, estruturas provisórias e desmoronamentos na indústria da construção civil brasileira**.

Inicialmente, o grupo buscou mensurar a frequência nacional direta de "desabamentos de estruturas". Contudo, a auditoria detalhada dos microdados públicos abertos revelou que os sistemas oficiais de registro de acidentes (especialmente a CAT aberta do INSS) **não dispõem de campo narrativo aberto nem disponibilizam publicamente a variável de situação geradora** (código eSocial `200020700` - *"Aprisionamento em/sob/entre desabamento ou desmoronamento"*).

Diante dessa constatação empírica, o projeto adota uma **abordagem científica mista (quali-quantitativa)**:
1. **Epidemiologia Macro (AEAT e CAT/INSS):** Mapeamento do perfil de acidentes, gravidade de lesões, mortalidade e letalidade na construção civil (CNAEs 41, 42 e 43), avaliando agentes causadores candidatos de alta severidade (andaimes, escavações, estruturas);
2. **Investigação Causal Qualitativa (MTE/SIT):** Análise aprofundada de relatórios oficiais de fiscalização de acidentes fatais por desabamento/soterramento, extraindo fatores técnicos, humanos e organizacionais à luz da NR-18 e NR-1;
3. **Crítica Metodológica aos Sistemas de SST:** Discussão sobre a "invisibilidade estatística" desses eventos catastróficos nos dados abertos governamentais, propondo melhorias para as políticas públicas e o gerenciamento de riscos ocupacionais (PGR/GRO).

A proposta detalhada para discussão com o grupo e orientador(a) está disponível em [`docs/proposta-artigo-mestrado.md`](docs/proposta-artigo-mestrado.md).

---

## 2. Dados e Fontes Utilizadas

| Fonte | Descrição e Recorte | Uso no Projeto |
|---|---|---|
| **AEAT 2024** | Anuário Estatístico da Previdência Social (2022–2024). Tabelas 1.1 e 59.2. | Totais setoriais, acidentes típicos, taxas de incidência, mortalidade e letalidade nos CNAEs 41, 42 e 43. |
| **CAT / INSS** | Microdados abertos mensais de Comunicação de Acidente de Trabalho. | Perfil individual: ocupação (CBO), lesão (CID-10), agentes causadores, dados demográficos e desfecho de óbito. |
| **MTE / SIT** | Relatórios de análise e fiscalização de acidentes graves e fatais (2016–2025). | Estudos de caso qualitativos, mecânica do acidente e falhas de engenharia/segurança. |
| **eSocial** | Tabelas 14 e 15 (versão S-1.3). | Referencial semântico normativo (código `200020700` e agentes correlatos). |

> Os arquivos brutos, metadados e hashes SHA-256 estão documentados em [`data/README.md`](data/README.md).

---

## 3. Síntese dos Dados Setoriais Consolidados (AEAT 2022–2024)

Auditoria realizada nas tabelas oficiais do Ministério da Previdência Social para a Construção Civil (CNAEs 41, 42 e 43):

| Indicador | 2022 | 2023 | 2024 | Variação (2022→2024) |
|---|---:|---:|---:|---:|
| **Total de Acidentes** | 43.452 | 46.672 | 50.789 | **+16,9%** |
| **Acidentes com CAT Registrada** | 37.905 | 40.292 | 44.091 | **+16,3%** |
| **Acidentes Típicos com CAT Registrada** | 31.858 | 33.451 | 35.907 | **+12,7%** |

*Detalhamento e fórmulas de cálculo auditados em [`docs/validacao-aeat-esocial-mte.md`](docs/validacao-aeat-esocial-mte.md).*

---

## 4. Estrutura do Repositório

```text
.
├── README.md                                    # Apresentação do projeto e visão executiva do artigo
├── base_estatistica_colapso_desabamento_construcao.xlsx # Planilha consolidada de trabalho (AEAT, filtros e fontes)
├── docs/
│   ├── proposta-artigo-mestrado.md             # Proposta de reenquadramento temático, metodológico e estrutura do artigo
│   ├── diario-exploratorio.md                  # Registro cronológico das decisões e auditorias da pesquisa
│   ├── validacao-aeat-esocial-mte.md           # Validação e recálculo dos dados estatísticos nas fontes primárias
│   ├── proxima-etapa-inspecao-cat.md           # Metodologia e resultados da inspeção dos microdados da CAT
│   ├── cenario-brasil-2021-2025.md             # Revisão de literatura sobre o cenário nacional de SST
│   ├── estado-da-arte-2021-2025.md             # Protocolo e estratégia de busca do estado da arte
│   ├── referencias-estado-arte.md              # Relação de artigos internacionais e nacionais selecionados
│   └── metodologia/
│       ├── classificacao-colapso.md            # Critérios operacionais de classificação e controle de falsos positivos
│       ├── base-estatistica-colapso.md         # Documentação e auditoria da planilha de trabalho
│       ├── dicionario-cat-validado.md          # Mapeamento do dicionário de dados da CAT
│       └── triagem-literatura-2021-2025.csv    # Planilha de triagem bibliográfica
└── data/
    ├── README.md                               # Documentação de dados brutos e integridade (hashes SHA-256)
    ├── raw/                                    # Dados brutos baixados (CAT e glossários)
    └── referencias/                            # Acervo de artigos e relatórios técnicos em PDF
```

---

## 5. Próximas Etapas

1. Alinhamento com a equipe sobre o foco temático a partir de [`docs/proposta-artigo-mestrado.md`](docs/proposta-artigo-mestrado.md);
2. Seleção de 3 a 5 estudos de caso do MTE de acidentes fatais por desabamento/soterramento para a matriz de análise causal;
3. Consolidação dos gráficos descritivos do AEAT e microdados piloto da CAT;
4. Redação preliminar das seções de Introdução, Metodologia e Resultados do artigo.
