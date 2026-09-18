# Validação dos dados AEAT, eSocial e MTE

**Data da verificação:** 18/09/2026
**Objetivo:** conferir os números da planilha diretamente nas fontes oficiais e testar a disponibilidade dos códigos de colapso.

## AEAT 2024 — tabela 1.1

Foi utilizada a [tabela oficial 1.1 do AEAT 2024](https://www.gov.br/previdencia/pt-br/assuntos/previdencia-social/arquivos/AEAT-2024/secao-i-estatisticas-de-acidentes-do-trabalho/subsecao-a-acidentes-do-trabalho/capitulo-1-brasil-e-grandes-regioes/1-1-quantidade-de-acidentes-do-trabalho-por-situacao-do-registro-e-motivo-segundo-a-classifi-cacao-nacional-de-atividades-economicas-cnae-no-brasil-2018-2019). Foram somadas as linhas CNAE 4110, 4120, 4211, 4212, 4213, 4221, 4222, 4223, 4291, 4292, 4299, 4311, 4312, 4313, 4319, 4321, 4322, 4329, 4330, 4391 e 4399.

| Indicador | 2022 | 2023 | 2024 | Resultado |
|---|---:|---:|---:|---|
| Total de acidentes | 43.452 | 46.672 | 50.789 | Confere com a planilha |
| Com CAT registrada | 37.905 | 40.292 | 44.091 | Confere com a planilha |
| Típicos com CAT registrada | 31.858 | 33.451 | 35.907 | Confere com a planilha |

| Indicador | Variação 2022→2024 | Situação |
|---|---:|---|
| Total de acidentes | 16,9% | Confirmada |
| Com CAT registrada | **16,3%** | Corrigida; a planilha apresentava 12,7% |
| Típicos com CAT registrada | 12,7% | Confirmada |

A diferença era de rotulagem: 12,7% corresponde aos acidentes típicos com CAT registrada, não a todos os acidentes com CAT registrada.

## eSocial — códigos

A documentação oficial do [eSocial, Tabelas 14 e 15](https://www.gov.br/esocial/pt-br/documentacao-tecnica/leiautes-esocial-versao-s-1-3-nt-07-2026/tabelas.html/view) confirma os códigos utilizados:

- 200020700: aprisionamento em, sob ou entre desabamento ou desmoronamento de edificação, barreira, etc.;
- 302050100, 302050500, 302050700 e 302050900: edifício, ponte/viaduto, andaime/plataforma e edifício/estrutura NIC;
- 302070100, 302070300, 302070700 e 302070900: escavação, canal/fosso, túnel e categoria ampla.

Essa validação confirma a descrição dos códigos, mas não demonstra que estejam no CSV público da CAT, que continua sem coluna explícita de situação geradora. O código 200020700 precisa ser testado em microdados eSocial ou outra base compatível.

## MTE — relatórios e casos

A página de [informações sobre acidentes do MTE](https://www.gov.br/trabalho-e-emprego/pt-br/assuntos/inspecao-do-trabalho/seguranca-e-saude-no-trabalho/acidentes-de-trabalho-informacoes) apresenta a categoria “Soterramento, Desabamento, Desmoronamento” e casos fatais e graves. Esses materiais servem para validação narrativa, não para uma contagem censitária comparável ao AEAT.

## Conclusão

1. Os totais da planilha foram reproduzidos no AEAT oficial.
2. As variações corretas são 16,9% para o total, 16,3% para acidentes com CAT registrada e 12,7% para típicos com CAT registrada.
3. Os códigos do eSocial foram confirmados semanticamente.
4. Ainda falta uma base de registros que contenha a situação geradora para estimar a quantidade de eventos 200020700.
