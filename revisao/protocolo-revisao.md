# Protocolo de revisão bibliográfica

**Dissertação:** viés decisório entre juízes e juízas em ações de saúde no Brasil (27 TJs e 6 TRFs)
**Origem:** fechado na entrevista grill-me de 27–28/09/2026 (ver `../grill-me-transcript.md`, 18 perguntas, 3 revisões de decisão)
**Versão:** 1.0

## 1. Pergunta da revisão

Há viés decisório entre juízes e juízas nos Tribunais Regionais Federais e Tribunais de Justiça brasileiros em ações de saúde? O que a literatura empírica internacional e brasileira sabe sobre o efeito do gênero do julgador em decisões de 1º grau, e por quais mecanismos?

Sub-perguntas por frente:

| Frente | Sub-pergunta | Papel |
|---|---|---|
| 1. Gênero do julgador | O gênero do magistrado altera a probabilidade de procedência e de concessão de urgência? Em que tipo de causa? | Principal |
| 2. Teoria | Por que o gênero importaria: representação, in-group bias, socialização profissional? | Moldura |
| 3. Judicialização da saúde | O que caracteriza o litígio de saúde no Brasil que o corpus captura (taxa de deferimento, perfil do autor, papel da liminar)? | Contexto |
| 4. PLN jurídico | Por que o tom/sentimento por LLM foi abandonado como variável dependente? | Secundária, 3 a 5 refs |

## 2. Construtos

| Construto | Definição operacional | Variável na base |
|---|---|---|
| Gênero do julgador (VI) | Sexo do magistrado que assina a sentença | `genero_juiz`, inferido por nome e IBGE; 17% indeterminado |
| Procedência (VD1) | Procedente / parcial / improcedente | `tipo_decisao` do DataJud, 100% cobertura |
| Urgência (VD2) | Concessão ou não de tutela de urgência / liminar | `resultado_urgencia_1a`, via TPU do CNJ |
| Tempo até sentença | Dias entre ajuizamento de referência e sentença | `dias_ate_sentenca`; **exploratório, sem frente de literatura** (P14) |
| Interação julgador × parte | Efeito do gênero do julgador condicional ao gênero da parte autora (in-group) | gênero da parte inferido por nome e IBGE (P17) |
| Estrato de comparação | Tribunal × ano de ajuizamento, erro-padrão agrupado por magistrado | `tribunal`, `ano`, `nome_mag` (P7) |
| Tom / sentimento | **Abandonado** (P2). Entra só como justificativa na frente 4 | — |

## 3. Bases e estratégia de busca

- **Bases sistemáticas:** Scopus, Web of Science, SciELO (P9).
- **Snowballing:** Google Scholar e listas de referência dos incluídos, para seminais anteriores à janela e para literatura cinzenta (P10, P15).
- **Literatura cinzenta:** entra somente se for o artigo-base (Laneuville & Possebom) ou se for citada por dois ou mais estudos incluídos. Marcada como `cinzenta` na coluna `base` da matriz (P15).
- **Idiomas:** inglês e português (P4).

## 4. Strings de busca

**Frente 1 (Scopus / WoS, título-resumo-palavras-chave):**

```
(judge* OR judicial OR court) AND (gender OR "female judge*" OR women OR sex)
AND (decision* OR ruling* OR outcome* OR sentencing OR "judge effects" OR bias)
```

**Frente 1 (SciELO, português):**

```
(juiz* OR magistrad* OR judicial) AND (gênero OR mulher* OR juíza*)
AND (decisão OR sentença OR julgamento OR viés)
```

**Frente 3 (SciELO / Scopus):**

```
(judicialização OR judicialization) AND (saúde OR health OR medicamento* OR medicine*)
AND (decisão OR sentença OR liminar OR ruling OR injunction) AND (Brasil OR Brazil)
```

**Frente 2 e 4:** sem string própria. Frente 2 vem por snowballing a partir dos incluídos da frente 1. Frente 4 é seleção dirigida de 3 a 5 referências que documentem validade e reprodutibilidade de sentimento em texto jurídico.

## 5. Janela temporal

| Frente | Janela | Marco |
|---|---|---|
| 1 | 2010–2026 | Boyd, Epstein & Martin (2010) como divisor. Seminais anteriores só por snowballing |
| 2 | Sem limite | Só por snowballing |
| 3 | 2009–2026 | Audiência pública da saúde no STF (2009) e STA 175 (2010) |
| 4 | 2019–2026 | Transformers aplicados a texto jurídico |

## 6. Critérios de inclusão

1. Estudo empírico quantitativo em que o gênero do magistrado é variável independente (frente 1).
2. Revisões sistemáticas e meta-análises sobre gênero e decisão judicial (frente 1).
3. Textos teóricos apenas na frente 2, por snowballing.
4. Estudos sobre litígio de saúde no Brasil com dados de decisões (frente 3).
5. Estudos de PLN jurídico que discutam validade da medida de sentimento (frente 4, no máximo 5).
6. Revisado por pares, com exceção do item Cinzenta da seção 3.
7. Inglês ou português.

## 7. Critérios de exclusão

1. Decisores sem carreira judicial: júri, juízes leigos, árbitros.
2. Estudos de PLN sem variável de gênero fora da cota da frente 4.
3. Estudos onde "gênero" não é do julgador nem da parte (por exemplo, gênero do advogado apenas).
4. Espanhol e outros idiomas.
5. Não excluídos por decisão explícita (P16): supremas cortes e cortes internacionais; estudos sobre gênero das partes, que alimentam o construto de interação (P17).

## 8. Extração e matriz

Cada estudo incluído gera uma linha em `matriz-literatura.csv` com o esquema:

`autor;ano;titulo;base;tipo_estudo;construto;achado;lacuna;relacao_com_pergunta`

Regras de preenchimento:

- `base`: Scopus, WoS, SciELO, snowballing ou cinzenta.
- `construto`: um dos construtos da seção 2, ou "teoria" / "contexto" / "PLN".
- `lacuna`: obrigatoriamente registra o **método de medição do gênero** do julgador quando o estudo é da frente 1 (autodeclaração, cadastro oficial, nome, não informado), conforme P18.
- `relacao_com_pergunta`: como o achado sustenta, contradiz ou qualifica a hipótese de viés decisório em saúde.

## 9. Triagem

1. Deduplicação entre bases.
2. Triagem por título e resumo contra os critérios das seções 6 e 7.
3. Leitura integral e extração para a matriz.
4. Snowballing para trás nos incluídos da frente 1 (seminais e cinzenta).
5. Registro do fluxo em números (identificados, deduplicados, triados, incluídos) para o capítulo de método.

## 10. Estado da matriz-semente

A matriz entregue junto a este protocolo é uma **semente construída por snowballing a partir do artigo-base e das referências já listadas no repositório da dissertação**. As linhas precisam ser confirmadas nas três bases (existência, ano, indexação) antes de contarem como resultado da busca sistemática. Os campos `achado` e `lacuna` foram preenchidos a partir do conhecimento do entrevistador e do assistente e devem ser conferidos na leitura integral.
