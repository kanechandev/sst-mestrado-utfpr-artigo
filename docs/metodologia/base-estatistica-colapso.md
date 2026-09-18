# Auditoria da base estatística de colapso/desabamento

**Arquivo:** [`base_estatistica_colapso_desabamento_construcao.xlsx`](../../base_estatistica_colapso_desabamento_construcao.xlsx)  
**Recebido no projeto:** 17/09/2026  
**SHA-256:** `91565928d82a86e28535f34b72b470ace39fdd56c0346d1c8ea241fffeb9aeff`

## Papel no projeto

Esta planilha é um instrumento de consolidação e exploração fornecido ao grupo. Ela reúne estatísticas setoriais, um filtro inicial de códigos relacionados a colapso, casos qualitativos do MTE e os endereços das fontes. Não deve ser citada como se fosse a fonte primária dos números: os valores do AEAT precisam ser conferidos na tabela oficial correspondente, e os casos do MTE precisam ser rastreados até o relatório original.

## Conteúdo auditado

| Aba | Função | Uso recomendado |
|---|---|---|
| `Resumo` | Totais de CNAE 41, 42 e 43 para 2022–2024 e síntese do filtro | Contextualização descritiva, após conferência no AEAT |
| `AEAT_CNAE_2022_2024` | Acidentes totais, com CAT e típicos por atividade | Denominador setorial e comparação entre atividades |
| `Filtros_Colapso` | Códigos de situação geradora e agente causador | Dicionário operacional inicial |
| `Casos_MTE` | Casos qualitativos de soterramento/desabamento/desmoronamento | Validação narrativa e discussão, não contagem automática |
| `Fontes` | URLs declaradas para as bases | Rastreabilidade |

## Resultado estatístico inicial

Na aba `Resumo`, o recorte CNAE 41–43 apresenta 43.452 acidentes em 2022, 46.672 em 2023 e 50.789 em 2024. A variação entre 2022 e 2024 é de aproximadamente 16,9%. Para registros com CAT, os valores são 37.905, 40.292 e 44.091. A conferência direta no AEAT mostrou que a variação correta desse indicador é 16,3%; a variação de 12,7% corresponde aos acidentes típicos com CAT registrada (31.858, 33.451 e 35.907) e estava rotulada incorretamente no resumo.

Esses valores são **provisórios**: a planilha contém os resultados, mas não documenta dentro de cada célula o procedimento de extração. Antes de publicar, conferir a soma e a definição de “total”, “com CAT” e “típicos” diretamente no [AEAT 2024](https://www.gov.br/previdencia/pt-br/assuntos/previdencia-social/arquivos/AEAT-2024), especialmente na tabela de quantidade por CNAE.

## Tabela operacional de códigos

O código `200020700` é o marcador primário porque sua descrição é específica para aprisionamento em/sob/entre desabamento ou desmoronamento de edificação, barreira e situação semelhante. Os códigos de agente causador abaixo são candidatos secundários: isoladamente, não provam que houve colapso.

| Tipo | Código | Descrição resumida | Regra |
|---|---:|---|---|
| Situação geradora | 200020700 | Aprisionamento em/sob/entre desabamento ou desmoronamento de edificação, barreira etc. | Incluir como marcador primário |
| Agente causador | 302050100 | Edifício ou estrutura | Candidato; validar narrativa |
| Agente causador | 302050500 | Ponte ou viaduto | Candidato; validar narrativa |
| Agente causador | 302050700 | Andaime ou plataforma | Candidato; excluir simples queda |
| Agente causador | 302050900 | Edifício ou estrutura, NIC | Candidato amplo |
| Agente causador | 302070100 | Escavação | Candidato; buscar desmoronamento/soterramento |
| Agente causador | 302070300 | Canal ou fosso | Candidato; validar narrativa |
| Agente causador | 302070700 | Túnel | Candidato; validar narrativa |
| Agente causador | 302070900 | Escavação, fosso, túnel, NIC | Candidato amplo |
| Situação geradora | 200012200 | Queda de pessoa de andaime/passagem/plataforma | Excluir por padrão; incluir só com colapso comprovado |
| Situação geradora | 200012700 | Queda em poço/escavação/abertura no piso | Excluir por padrão; não é desmoronamento por si só |

O eSocial mantém as tabelas oficiais de **Agente Causador do Acidente de Trabalho** e **Situação Geradora do Acidente de Trabalho**; portanto, a semântica dos códigos deve ser conferida na [documentação oficial de tabelas do eSocial](https://www.gov.br/esocial/pt-br/documentacao-tecnica/leiautes-esocial-versao-s-1-3-nt-07-2026/tabelas.html/view). A validação semântica do código não valida, por si só, os números estatísticos da planilha.

## Casos qualitativos

Os casos listados na aba `Casos_MTE` são úteis para elaborar a lógica de classificação e exemplificar mecanismos de acidente. Brumadinho e Mariana devem ficar fora da análise principal se o objeto permanecer restrito à fase de obras, pois são rompimentos de barragem em contexto distinto. Os casos de 2018–2019 também não pertencem ao corpus bibliográfico do estado da arte 2021–2025; podem ser usados como evidência documental complementar.

## Pendências de validação

1. ~~Recalcular os totais 2022–2024 a partir da tabela oficial do AEAT.~~ **Concluído em 18/09/2026; totais conferidos.**
2. Registrar, para cada total, tabela, linha, coluna e fórmula utilizada.
3. ~~Confirmar a versão das Tabelas 14/15 do eSocial usada na construção dos códigos.~~ **Concluído quanto à existência e descrição; ainda falta testar a presença nos microdados.**
4. Verificar se `200020700` está disponível na base de microdados que será analisada; o CSV público piloto da CAT não possuía esse campo no cabeçalho.
5. Fazer dupla revisão de uma amostra dos candidatos e medir falsos positivos, especialmente para andaimes, plataformas e escavações.
