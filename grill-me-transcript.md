# grill-me — transcript da entrevista

**Tema:** protocolo de revisão bibliográfica da dissertação de mestrado
**Título de partida da dissertação:** "Sentenças de juízes e juízas no Brasil: há diferença de tom?"
**Corpus:** sentenças de 1º grau em ações de saúde, 27 Tribunais de Justiça e 6 Tribunais Regionais Federais (33 tribunais), 2017–2026
**Skill:** grill-me (`.claude/skills/grill-me/SKILL.md`)
**Data:** 27 e 28/09/2026
**Entrevistado:** Giovanni Brigido
**Entrevistador:** Claude Code (Fable 5.1)

Formato: cada pergunta tem número, nível da árvore de decisão, opções apresentadas, resposta dada e, quando for o caso, a marca **REVISÃO DE DECISÃO ANTERIOR** com a pergunta que ela reabre.

Contagem: 18 perguntas respondidas. 3 revisões explícitas de decisão anterior (P6 revisa P3, P14 revisa P5, P15 revisa P9), mais uma revisão da premissa do projeto feita pelo próprio entrevistado em P2.

---

## Rodada 1 — Nível 1: pergunta da revisão e construtos

**Resumo do acordo antes da rodada:** a dissertação perguntava se há diferença de sentimento (tom) entre sentenças de juízes e juízas. O artigo-base (Laneuville & Possebom) mede resultado, não linguagem. A revisão ainda não tinha pergunta própria.

### P1. Qual é a pergunta da REVISÃO (não a da dissertação)?
- Opções: (A) três frentes integradas: gênero do julgador, sentimento em texto jurídico, judicialização da saúde; (B) duas frentes; (C) uma frente estreita só de linguagem.
- **Resposta:** "A pergunta a ser respondida é se há viés decisório entre juízes e juízas nos Tribunais Regionais Federais (6) e Tribunais de Justiça (27) acerca do assunto de saúde."
- **Nota do entrevistador:** a resposta reformula a pergunta em torno de *viés decisório*, não de *tom*. Isso abre a P2.

### P2. O que é "tom" na sua revisão?
- Opções: (A) sentimento polar + estilo linguístico; (B) só sentimento polar; (C) emoções discretas.
- **Resposta:** "Não consideramos mais o tom decisório, visto que essa extração provinha de um modelo de LLM. Agora vamos utilizar clusterização por tribunal, ano e magistrado."
- **Revisão da premissa do projeto (pelo entrevistado):** o construto "tom por LLM", que era a variável dependente do piloto TJCE e do título, sai do desenho. Motivo declarado: dependência de um LLM para gerar a variável.

### P3. A revisão inclui estudos sobre efeito do gênero no RESULTADO da decisão ou só na LINGUAGEM?
- Opções: (A) resultado e linguagem; (B) só linguagem; (C) resultado como secundário.
- **Resposta:** (A) Resultado e linguagem.
- **Nota do entrevistador:** conflita com P2. Dependência pendente, resolvida em P6.

### P4. Escopo geográfico e de idioma?
- Opções: (A) internacional, inglês + português; (B) só Brasil; (C) inglês, português e espanhol.
- **Resposta:** (A) Internacional, inglês e português. Espanhol excluído.

---

## Rodada 2 — Nível 1 reaberto: o construto mudou

**Resumo do acordo antes da rodada:** pergunta = viés decisório entre juízes e juízas em ações de saúde nos 33 tribunais. Tom saiu. Escopo internacional em inglês e português.
**Ponto cego:** P2 abandona tom e P3 mantém linguagem. "Viés decisório" e "clusterização" sem definição operacional.

### P5. O que é "viés decisório" operacionalmente? Qual desfecho o estudo precisa ter medido para entrar na matriz?
- Opções: (A) procedência + urgência; (B) só procedência; (C) procedência, urgência e tempo até sentença.
- **Resposta:** (C) Procedência, urgência e tempo.

### P6. REVISÃO DA P3: se o tom saiu do desenho, a frente "linguagem/sentimento em texto jurídico" continua na revisão?
- Opções: (A) fica como frente secundária, 3 a 5 referências para justificar o abandono do tom, sem string própria; (B) sai da revisão; (C) mantém como frente plena.
- **Resposta:** (A) Fica como frente secundária.
- **REVISÃO DE DECISÃO ANTERIOR: revisa P3.** "Resultado e linguagem" passa a ser "resultado como frente principal, linguagem como frente secundária de justificativa". Dependência P2 → P3 resolvida.

### P7. "Clusterização por tribunal, ano e magistrado" é estratégia de identificação ou método não supervisionado?
- Opções: (A) estratos de comparação: efeitos fixos tribunal × ano, erro-padrão agrupado por magistrado, literatura de judge effects; (B) clusterização não supervisionada (k-means) de perfis decisórios; (C) ambos.
- **Resposta:** (A) Estratos de comparação.
- **Nota do entrevistador:** a palavra "clusterização" na P2 significava *cluster de erro-padrão e estratificação*, não aprendizado não supervisionado. Isso define a frente metodológica: judge effects e distribuição aleatória de processos.

### P8. Qual moldura teórica explica POR QUE o gênero do julgador importaria?
- Opções: (A) teoria da representação + in-group bias; (B) socialização profissional (hipótese nula); (C) viés atitudinal.
- **Resposta:** (A) Teoria da representação e in-group bias. Hipótese nula plausível em saúde.

---

## Rodada 3 — Nível 2: bases, janela temporal e strings

**Resumo do acordo antes da rodada:** quatro frentes. Principal: gênero do julgador em procedência, urgência e tempo, identificação por estratos tribunal × ano. Teórica: representação e in-group. Contexto: judicialização da saúde. Secundária: sentimento em texto jurídico.
**Ponto cego:** três desfechos triplicam a literatura, e "tempo" puxa uma literatura de celeridade que não conversa com gênero.

### P9. Quais bases a busca sistemática cobre?
- Opções: (A) Scopus + Web of Science + SciELO, Google Scholar só para snowballing; (B) Scopus + SciELO; (C) Scopus + WoS + SciELO + SSRN/NBER.
- **Resposta:** (A) Scopus, Web of Science e SciELO.

### P10. Janela temporal da frente principal?
- Opções: (A) 2010–2026 + seminais sem limite por snowballing; (B) 2000–2026; (C) 2015–2026.
- **Resposta:** (A) 2010–2026, com seminais (Gilligan 1982; Songer & Crews-Meyer 2000; Steffensmeier & Hebert 1999) entrando por snowballing.

### P11. String de busca da frente principal em inglês?
- Opções: (A) 3 blocos AND; (B) 3 blocos + bloco de desfecho; (C) 2 blocos amplos.
- **Resposta:** (A) `(judge* OR judicial OR court) AND (gender OR "female judge*" OR women OR sex) AND (decision* OR ruling* OR outcome* OR sentencing OR "judge effects" OR bias)`.

### P12. Frente de judicialização da saúde: marco inicial da janela em português?
- Opções: (A) 2009 em diante (audiência pública da saúde no STF, STA 175); (B) 2018 em diante (Tema 106 STJ); (C) sem limite inferior.
- **Resposta:** (A) 2009 em diante. String: `(judicialização) AND (saúde OR medicamento*) AND (decisão OR sentença OR liminar)`.

---

## Rodada 4 — Níveis 3 e 4: critérios e dependências abertas

**Resumo do acordo antes da rodada:** Scopus, WoS, SciELO. Frente principal 2010–2026 com seminais por snowballing, string de 3 blocos. Saúde de 2009 em diante.
**Pontos cegos:** a string da P11 não tem termo de tempo, então o terceiro desfecho da P5 não seria capturado. O artigo-base circula como working paper e um critério "só revisado por pares" o excluiria.

### P13. Critério de inclusão por tipo de estudo?
- Opções: (A) empírico com gênero do julgador como variável independente + revisões sistemáticas; teóricos só na frente de teoria; (B) qualquer desenho, inclusive qualitativo; (C) só quantitativo com dados administrativos.
- **Resposta:** (A).

### P14. REVISÃO DA P5: a string não captura "tempo até sentença". O terceiro desfecho fica?
- Opções: (A) vira desfecho exploratório da dissertação, sem frente de literatura própria; (B) fica e a string ganha bloco de celeridade; (C) sai do desenho.
- **Resposta:** (A) Vira desfecho exploratório.
- **REVISÃO DE DECISÃO ANTERIOR: revisa P5.** Desfechos da revisão passam a ser dois: procedência e urgência. Tempo continua na dissertação como análise exploratória. Dependência P5 → P11 resolvida.

### P15. REVISÃO DA P9: o artigo-base é working paper. Como a literatura cinzenta entra?
- Opções: (A) exceção nominal via snowballing: working papers entram se citados por 2+ estudos incluídos ou se forem o artigo-base, marcados como "cinzenta"; (B) adiciona SSRN/NBER como base; (C) exclui, artigo-base fica fora da matriz.
- **Resposta:** (A) Exceção nominal via snowballing.
- **REVISÃO DE DECISÃO ANTERIOR: revisa P9.** A lista de bases não muda, mas o critério de elegibilidade ganha uma cláusula de exceção para literatura cinzenta. Dependência P9 → P13 resolvida.

### P16. Critérios de EXCLUSÃO explícitos (múltipla escolha)?
- Opções: (A) gênero só das partes ou advogados; (B) júri, juízes leigos e arbitragem; (C) cortes internacionais e supremas cortes; (D) PLN sem variável de gênero.
- **Resposta:** (B) e (D). Ficam de fora júri, juízes leigos, arbitragem e estudos de PLN sem variável de gênero (salvo os 3 a 5 da frente secundária).
- **Nota do entrevistador:** (A) e (C) NÃO foram marcadas. Logo, estudos sobre gênero das partes e sobre supremas cortes permanecem elegíveis. Isso abre P17.

---

## Rodada 5 — Nível 4: bordas

### P17. Você manteve estudos sobre gênero das PARTES. A interação gênero do julgador × gênero da parte (in-group bias) vira construto na matriz?
- Opções: (A) sim, construto próprio "interação julgador × parte"; (B) não, gênero das partes só como controle.
- **Resposta:** (A) Sim, construto próprio. A base já infere gênero da parte por nome e IBGE.

### P18. 17% das decisões têm gênero do magistrado indeterminado. Como a revisão trata estudos com o mesmo problema de medição?
- Opções: (A) coluna "lacuna" registra o método de inferência de gênero de cada estudo; (B) exclui estudos que inferem gênero por nome; (C) ignora.
- **Resposta:** (A). Cada estudo incluído declara como mediu gênero (autodeclaração, nome, cadastro oficial). Justifica a inferência por nome e IBGE da dissertação.

---

## Acordo final (estado da árvore de decisão)

| Nó | Decisão | Origem |
|---|---|---|
| Pergunta da revisão | Há viés decisório entre juízes e juízas em ações de saúde nos 27 TJs e 6 TRFs? | P1 |
| Construto principal | Viés decisório = diferença por gênero do julgador em procedência e em concessão de urgência, condicionada a tribunal × ano × assunto | P5 revisada por P14 |
| Construto secundário | Interação gênero do julgador × gênero da parte (in-group) | P17 |
| Construto abandonado | Tom/sentimento por LLM | P2, P6 |
| Identificação | Estratos tribunal × ano, erro-padrão agrupado por magistrado, literatura de judge effects | P7 |
| Teoria | Representação e in-group bias; hipótese nula por socialização profissional como contraste | P8 |
| Frentes | 1 principal (gênero do julgador), 2 teórica, 3 contexto (judicialização da saúde), 4 secundária (PLN jurídico, 3 a 5 refs) | P1, P6 |
| Bases | Scopus, Web of Science, SciELO; Google Scholar só para snowballing | P9 |
| Cinzenta | Só por snowballing: artigo-base ou citado por 2+ incluídos, marcado "cinzenta" | P15 |
| Janela | Frente 1: 2010–2026 + seminais. Frente 3: 2009–2026. Frente 4: 2019–2026 | P10, P12 |
| Idiomas | Inglês e português | P4 |
| Inclusão | Empírico quantitativo com gênero do julgador como VI; revisões sistemáticas; teóricos só na frente 2 | P13 |
| Exclusão | Júri, juízes leigos, arbitragem; PLN sem variável de gênero | P16 |
| Medição de gênero | Coluna lacuna registra o método de cada estudo | P18 |
