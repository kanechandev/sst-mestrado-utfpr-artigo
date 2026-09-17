# Dicionário preliminar validado — CAT/INSS

**Base:** `data/raw/cat/CAT-2024-12-INSS.zip`  
**Glossário:** `data/raw/glossario/Glossario-CAT-INSS.xlsx`  
**Data da validação:** 17/09/2026

## 1. Validação estrutural

O arquivo tabular do ZIP possui 27 colunas e separador `;`. O texto está em codificação compatível com ISO-8859-1/Windows-1252. A primeira linha contém o cabeçalho; cada linha seguinte representa um registro disponibilizado na base, sem identificador pessoal exposto.

O glossário oficial possui 24 entradas conceituais. A diferença para as 27 colunas decorre de campos que aparecem em pares no CSV — código e descrição de CBO, CID e CNAE — além da repetição de Data Acidente.

## 2. Campos do CSV

| Nº | Cabeçalho no CSV | Uso analítico preliminar |
|---:|---|---|
| 1 | Agente Causador Acidente | mecanismo/objeto associado ao acidente; principal campo candidato à classificação de colapso |
| 2 | Data Acidente | data do evento |
| 3 | CBO | código da ocupação |
| 4 | CBO | descrição da ocupação |
| 5 | CID-10 | código da lesão/doença |
| 6 | CID-10 | descrição da lesão/doença |
| 7 | CNAE2.0 Empregador | código da atividade econômica |
| 8 | CNAE2.0 Empregador | descrição da atividade econômica |
| 9 | Emitente CAT | origem/emissor da comunicação |
| 10 | Espécie do benefício | espécie do benefício quando informada |
| 11 | Filiação Segurado | vínculo/filiação previdenciária |
| 12 | Indica Óbito Acidente | desfecho fatal indicado na base |
| 13 | Munic Empr | município da sede do empregador |
| 14 | Natureza da Lesão | tipo de lesão |
| 15 | Origem de Cadastramento CAT | origem do cadastramento |
| 16 | Parte Corpo Atingida | parte do corpo |
| 17 | Sexo | sexo informado |
| 18 | Tipo do Acidente | típico, trajeto ou doença, conforme valores observados |
| 19 | UF Munic. Acidente | UF do local do acidente |
| 20 | UF Munic. Empregador | UF da sede do empregador |
| 21 | Data Afastamento | início do afastamento, quando informado |
| 22 | Data Despacho Benefício | data de despacho do benefício, quando informada |
| 23 | Data Acidente | repetição do campo de data no arquivo publicado |
| 24 | Data Nascimento | data de nascimento, quando informada |
| 25 | Data Emissão CAT | data de emissão da CAT |
| 26 | Tipo de Empregador | tipo cadastral do empregador |
| 27 | CNPJ/CEI Empregador | identificador do empregador, quando informado |

Os campos 3/4, 5/6 e 7/8 devem ser tratados como pares código-descrição, não como três variáveis independentes. A coluna 23 deve ser comparada com a coluna 2 antes de ser usada; neste momento ela será considerada redundante.

## 3. Valores observados na validação-piloto

Exemplos observados no CSV:

- CBO: `717020` / `Servente de Obras`;
- CID-10: `S626` / `S62.6 Fratura...`;
- CNAE: `7112` / `Serviços de Engenharia`;
- Tipo de acidente: `Típico`;
- indicação de óbito: `Não`;
- agente causador: `Máquina, NIC`, `Andaime, Plataforma`, `Escada Móvel ou Fixa`, entre outros.

Esses exemplos confirmam que os códigos e descrições vêm juntos em colunas pareadas. Ainda não constituem um catálogo completo de domínios.

## 4. Campos relevantes e campos ausentes

### Disponíveis e úteis

`Agente Causador Acidente`, `CNAE`, `CBO`, `CID-10`, `Natureza da Lesão`, `Parte Corpo Atingida`, `Tipo do Acidente`, `Indica Óbito Acidente`, `Data Acidente` e localização do acidente.

### Não identificados no cabeçalho

Não foi identificado campo narrativo de descrição do acidente, nem campo explícito denominado “situação geradora”, “fase da obra”, “atividade executada”, “estrutura permanente/provisória” ou “tipo de colapso”. Portanto, a CAT isoladamente não permite uma classificação causal completa.

## 5. Consequência metodológica

A pesquisa não deverá transformar automaticamente “andaime”, “escada”, “metal”, “piso” ou “superfície de sustentação” em acidente de colapso. Esses agentes serão tratados como **candidatos** e submetidos a critérios adicionais.

Para uma classificação mais confiável, a análise deve combinar:

1. atividade econômica/CNAE;
2. agente causador;
3. natureza da lesão e parte do corpo;
4. tipo de acidente e óbito; e
5. quando possível, confirmação por relatório de acidente, SINAN ou fonte documental institucional.

