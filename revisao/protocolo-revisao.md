# Protocolo de revisão bibliográfica

**Dissertação:** viés decisório entre juízes e juízas em ações de saúde no Brasil (27 TJs e 6 TRFs)
**Origem:** fechado na entrevista grill-me de 27–28/09/2026 (ver `../grill-me-transcript.md`, 22 perguntas, 7 revisões de decisão)
**Versão:** 1.1 (strings e frentes revisadas em 28/09, Q19 a Q22)

## 1. Pergunta da revisão

Há viés decisório entre juízes e juízas nos Tribunais Regionais Federais e Tribunais de Justiça brasileiros em ações de saúde? O que a literatura empírica internacional e brasileira sabe sobre o efeito do gênero do julgador em decisões de 1º grau, por quais mecanismos, e como esse efeito é identificado de forma defensável?

Por que "viés decisório" e não "tom" (Q2, Q20): o tom por LLM era um juízo subjetivo aplicado sobre outro juízo subjetivo (a sentença), sem validação por anotadores humanos (kappa). Sem isso não se sabe o que a variável mede. O desfecho da decisão, em contraste, é rotulado externamente pelo DataJud (`tipo_decisao`, 100% de cobertura) e pela TPU do CNJ (resultado da urgência).

Sub-perguntas por frente (Q19):

| Frente | Sub-pergunta | Papel |
|---|---|---|
| 1. Gênero do julgador e desfecho | O gênero do magistrado altera a probabilidade de procedência e de concessão de urgência? Em que tipo de causa? Como o efeito é identificado (sorteio, judge effects)? | Principal |
| 2. Teoria | Por que o gênero importaria: representação e "different voice" (Gilligan), in-group bias, ou socialização profissional como hipótese nula? | Moldura |
| 3. Judicialização da saúde | O que caracteriza o litígio de saúde no Brasil que o corpus captura (taxa de deferimento, perfil do autor, papel da liminar)? | Contexto |

**Nota de justificativa (não é frente):** de 3 a 5 referências de PLN jurídico (Grimmer & Stewart; Ash, Chen & Ornaghi; LEGAL-BERT; Silva; Rajapaksha) entram apenas para documentar por que o tom por LLM foi abandonado. Sem string, sem triagem.

## 2. Construtos

| Construto | Definição operacional | Variável na base | Origem |
|---|---|---|---|
| Gênero do julgador (VI) | Sexo do magistrado que assina a sentença | `genero_juiz`, inferido por nome e IBGE; 17% indeterminado | Q1 |
| Procedência (VD1) | Procedente / parcial / improcedente | `tipo_decisao` do DataJud, 100% cobertura | Q5, Q14 |
| Urgência (VD2) | Concessão ou não de tutela de urgência / liminar | `resultado_urgencia_1a`, via TPU do CNJ | Q5, Q14 |
| Tempo até sentença | Dias entre ajuizamento de referência e sentença | `dias_ate_sentenca`; **exploratório, sem frente de literatura** | Q14 |
| Interação julgador × parte | Efeito do gênero do julgador condicional ao gênero da parte autora (in-group) | gênero da parte inferido por nome e IBGE | Q17 |
| Estrato de comparação (identificação) | Tribunal × ano de ajuizamento. Dentro do estrato o processo é distribuído por sorteio entre varas (CPC/2015, art. 285), logo juiz e juíza recebem casos comparáveis. Erro-padrão agrupado por magistrado | `tribunal`, `ano`, `nome_mag` | Q7, Q21 |
| Tom / sentimento | **Abandonado** por falta de validade de construto. Só na nota de justificativa | — | Q2, Q20 |

## 3. Bases e estratégia de busca

- **Bases sistemáticas:** Scopus, Web of Science, SciELO (Q9).
- **Snowballing:** Google Scholar e listas de referência dos incluídos, para seminais anteriores à janela e para literatura cinzenta (Q10, Q15).
- **Literatura cinzenta:** entra somente se for o artigo-base (Laneuville & Possebom) ou se for citada por dois ou mais estudos incluídos. Marcada como `cinzenta` na coluna `base` da matriz (Q15).
- **Idiomas:** inglês e português (Q4).

## 4. Strings de busca (Q22)

**Frente 1, Scopus (sintaxe Scopus; em WoS trocar por TS= e o filtro de ano por PY=2010-2026):**

```
TITLE-ABS-KEY(
  (judge* OR judicial OR court*)
  AND (gender OR "female judge*" OR "women judge*" OR sex)
  AND (decision* OR ruling* OR sentencing OR "judge effects" OR bias)
  AND (grant* OR injunction* OR "win rate" OR "plaintiff success" OR outcome* OR "case outcome*")
) AND PUBYEAR > 2009
```

O quarto bloco cobre os dois desfechos: procedência (outcome, win rate, plaintiff success) e urgência (grant, injunction). Não há termo de tempo, por decisão da Q14.

**Frente 1, SciELO (português):**

```
(juiz* OR magistrad* OR judicial) AND (gênero OR mulher* OR juíza*)
AND (decisão OR sentença OR julgamento OR viés) AND (procedência OR deferimento OR liminar OR resultado)
```

**Frente 2, Scopus/WoS (teoria):**

```
TITLE-ABS-KEY(
  ("in-group bias" OR "ingroup bias" OR "different voice" OR "representative bureaucracy" OR "descriptive representation")
  AND (judge* OR judicial OR court*)
)
```

Sem filtro de ano. Complementada por snowballing para trás a partir de Boyd, Epstein & Martin (2010) e Harris & Sen (2019).

**Frente 3, SciELO e Scopus (judicialização da saúde):**

```
(judicialização OR judicialization)
AND (saúde OR health OR medicamento* OR medicine*)
AND (decisão OR sentença OR liminar OR deferimento OR concessão OR procedência OR ruling OR injunction)
AND (Brasil OR Brazil)
```

Ano ≥ 2009.

## 5. Janela temporal

| Frente | Janela | Marco |
|---|---|---|
| 1 | 2010–2026 | Boyd, Epstein & Martin (2010) como divisor. Seminais anteriores só por snowballing (Q10) |
| 2 | Sem limite | String própria + snowballing (Q22) |
| 3 | 2009–2026 | Audiência pública da saúde no STF (2009) e STA 175 (2010) (Q12) |
| Nota PLN | 2013–2026 | Grimmer & Stewart (2013) como referência de validação |

## 6. Critérios de inclusão (Q13)

1. Estudo empírico quantitativo em que o gênero do magistrado é variável independente (frente 1).
2. Revisões sistemáticas e meta-análises sobre gênero e decisão judicial (frente 1).
3. Textos teóricos apenas na frente 2.
4. Estudos sobre litígio de saúde no Brasil com dados de decisões (frente 3).
5. Revisado por pares, com exceção do item Cinzenta da seção 3.
6. Inglês ou português.

## 7. Critérios de exclusão (Q16)

1. Decisores sem carreira judicial: júri, juízes leigos, árbitros.
2. Estudos de PLN sem variável de gênero, fora da cota da nota de justificativa.
3. Estudos onde "gênero" não é do julgador nem da parte (por exemplo, gênero do advogado apenas).
4. Espanhol e outros idiomas.
5. Não excluídos por decisão explícita: supremas cortes e cortes internacionais; estudos sobre gênero das partes, que alimentam o construto de interação (Q17).

## 8. Extração e matriz

Cada estudo incluído gera uma linha em `matriz-literatura.csv` com o esquema:

`autor;ano;titulo;base;tipo_estudo;construto;achado;lacuna;relacao_com_pergunta`

Regras de preenchimento:

- `base`: Scopus, WoS, SciELO, snowballing ou cinzenta.
- `construto`: um dos construtos da seção 2, ou "teoria" / "contexto" / "PLN (nota)".
- `lacuna`: obrigatoriamente registra o **método de medição do gênero** do julgador quando o estudo é da frente 1 (autodeclaração, cadastro oficial, nome, não informado), conforme Q18.
- `relacao_com_pergunta`: como o achado sustenta, contradiz ou qualifica a hipótese de viés decisório em saúde.

## 9. Triagem

1. Deduplicação entre bases.
2. Triagem por título e resumo contra os critérios das seções 6 e 7.
3. Leitura integral e extração para a matriz.
4. Snowballing para trás nos incluídos das frentes 1 e 2 (seminais e cinzenta).
5. Registro do fluxo em números (identificados, deduplicados, triados, incluídos) para o capítulo de método.

## 10. Estado da matriz-semente

A matriz entregue junto a este protocolo é uma **semente construída por snowballing a partir do artigo-base e das referências já listadas no repositório da dissertação**. As linhas precisam ser confirmadas nas três bases (existência, ano, indexação) antes de contarem como resultado da busca sistemática. Os campos `achado` e `lacuna` foram preenchidos a partir do conhecimento do entrevistador e do assistente e devem ser conferidos na leitura integral.
