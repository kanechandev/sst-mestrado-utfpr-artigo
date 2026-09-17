# Classificação exploratória de eventos relacionados a colapso

**Versão:** 0.1 — 17/09/2026  
**Status:** instrumento de triagem; ainda não é uma classificação definitiva do artigo

## Cruzamento com a base de trabalho e o eSocial

A planilha [`base-estatistica-colapso.md`](base-estatistica-colapso.md) acrescentou um marcador mais específico: a situação geradora `200020700`, descrita como aprisionamento em/sob/entre desabamento ou desmoronamento de edificação, barreira etc. Esse código deve ser o filtro primário quando estiver disponível.

Os códigos `302050100`, `302050500`, `302050700`, `302050900`, `302070100`, `302070300`, `302070700` e `302070900` são apenas candidatos por agente causador. Eles exigem validação com narrativa, relatório ou combinação de campos. Quedas de andaime e quedas em poços/escavações (`200012200` e `200012700`) ficam excluídas por padrão, salvo evidência adicional de colapso.

Essa possibilidade não contradiz a inspeção anterior da CAT: o arquivo público piloto da CAT não apresentava a coluna de situação geradora. O cruzamento eSocial é uma fonte metodológica separada e ainda precisa ser ligado a uma base de registros que contenha esses códigos.

## Unidade de classificação

Classificar o registro da CAT, e não afirmar automaticamente que ele representa um acidente coletivo. Um mesmo evento pode gerar mais de um registro de trabalhador. Quando houver evidência de evento coletivo, isso deverá ser documentado separadamente.

## Regra de evidência

- **Confirmado:** descrição documental externa ou narrativa inequívoca de colapso/desabamento.
- **Provável:** combinação de agente causador e lesão compatível, sem confirmação narrativa.
- **Candidato:** agente ou contexto compatível, mas insuficiente para inferir colapso.
- **Não classificado:** informação insuficiente ou incompatível.

## Tabela de classificação

| Código | Categoria | Indicadores/candidatos na CAT | Regra inicial |
|---|---|---|---|
| A | Colapso de estrutura permanente | parede, laje, piso, telhado, elemento estrutural, estrutura de concreto/madeira | Confirmar perda de estabilidade e queda/ruptura da estrutura |
| B | Colapso de estrutura provisória | andaime, plataforma, forma, cimbramento, escoramento, torre | Não classificar apenas pela presença do agente; exigir ruptura/queda/colapso |
| C | Desabamento de parede ou alvenaria | parede, alvenaria, bloco, elemento de vedação | Exigir desabamento/queda do elemento, não apenas contato ou impacto |
| D | Desmoronamento de escavação/talude ou soterramento | escavação, fosso, túnel, talude, terra | Exigir desmoronamento ou soterramento; escavação isolada é apenas candidata |
| E | Colapso em demolição/reforma | demolição, reforma, edifício existente, estrutura parcialmente removida | Exigir relação entre atividade e perda de estabilidade |
| F | Ruptura/queda de elemento estrutural ou pré-moldado | pré-moldado, viga, pilar, laje, peça, carga suspensa | Diferenciar queda de objeto isolado de ruptura/queda estrutural |
| G | Outro evento de perda de estabilidade | agente não contemplado, mas com evidência documental | Usar somente quando a evidência não couber em A–F |
| H | Indeterminado | dados insuficientes, agente genérico ou lesão sem mecanismo | Manter no denominador da triagem, fora do grupo confirmado |

## Variáveis derivadas recomendadas

| Variável | Valores iniciais |
|---|---|
| `classe_colapso` | A–H |
| `nivel_evidencia` | confirmado, provável, candidato, não classificado |
| `envolve_estrutura` | sim, não, indeterminado |
| `envolve_estrutura_provisoria` | sim, não, indeterminado |
| `envolve_soterramento` | sim, não, indeterminado |
| `fase_obra` | execução, reforma, demolição, indeterminada |
| `vitima_fatal` | sim, não, ignorado |
| `fonte_confirmacao` | CAT, SINAN, relatório MTE, documento institucional, inexistente |
| `observacao_classificacao` | justificativa curta e auditável |

## Termos para a primeira triagem

Normalizar acentos e caixa antes da busca. Usar como candidatos: `andaime`, `plataforma`, `forma`, `cimbramento`, `escoramento`, `escavação`, `fosso`, `túnel`, `talude`, `terra`, `soterramento`, `parede`, `alvenaria`, `laje`, `pilar`, `viga`, `telhado`, `piso`, `estrutura`, `pré-moldado`, `demolição`, `ruptura`, `desabamento`, `desmoronamento` e `colapso`.

Uma ocorrência do termo deve gerar revisão, não classificação automática. A lista será ampliada ou reduzida após a inspeção de todo o período escolhido.
