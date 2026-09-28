# grill-me — transcript da entrevista

**Tema:** protocolo de revisão bibliográfica da dissertação de mestrado
**Título de partida da dissertação:** "Sentenças de juízes e juízas no Brasil: há diferença de tom?"
**Corpus:** sentenças de 1º grau em ações de saúde, 27 Tribunais de Justiça e 6 Tribunais Regionais Federais (33 tribunais), 2017–2026
**Skill:** grill-me (`.claude/skills/grill-me/SKILL.md`)
**Data:** 27 e 28/09/2026
**Entrevistado:** Giovanni Brigido
**Entrevistador:** Claude Code (Fable 5.1)

Formato: cada pergunta tem número (Q1, Q2, ...), nível da árvore de decisão, opções apresentadas, resposta dada e, quando for o caso, a marca **REVISÃO DE DECISÃO ANTERIOR** com a pergunta que ela reabre.

Contagem: 25 perguntas respondidas. 10 revisões explícitas de decisão anterior (Q6 revisa Q3, Q14 revisa Q5, Q15 revisa Q9, Q19 revisa Q1, Q20 revisa Q2, Q21 revisa Q7, Q22 revisa Q11 e Q12, Q23 revisa Q2, Q24 revisa Q7 e Q21, Q25 revisa o registro de Q1 e Q2), mais a revisão da premissa do projeto feita pelo próprio entrevistado em Q2.

Registro: nas perguntas Q1, Q2 e Q3 há uma **Resposta consolidada**, escrita em 28/09 depois das rodadas 6 e 7, seguida da **Resposta original** de 27/09, preservada na íntegra. A consolidada é a resposta que vale para o protocolo; a original mostra como a decisão evoluiu (decisão da Q25).

---

## Rodada 1 — Nível 1: pergunta da revisão e construtos

**Resumo do acordo antes da rodada:** a dissertação perguntava se há diferença de sentimento (tom) entre sentenças de juízes e juízas. O artigo-base (Laneuville & Possebom) mede resultado, não linguagem. A revisão ainda não tinha pergunta própria.

### Q1. Qual é a pergunta da REVISÃO (não a da dissertação)?
- Opções: (A) três frentes integradas: gênero do julgador, sentimento em texto jurídico, judicialização da saúde; (B) duas frentes; (C) uma frente estreita só de linguagem.
- **Resposta consolidada (28/09, após Q19, Q20, Q23 e Q25):** a pergunta da revisão é: *há viés decisório entre juízes e juízas nos 6 Tribunais Regionais Federais e nos 27 Tribunais de Justiça em ações de saúde?* Ela substitui a pergunta original sobre *tom* por três razões. Primeira, o tom era medido por LLM sem validação contra julgamento humano, um juízo subjetivo sobre outro juízo subjetivo, o que era o ponto de fragilidade do desenho. Segunda, o orientador orientou trocar a classificação por tom pela formação de grupos comparáveis (clusterização por tribunal, ano e magistrado), para que a diferença entre juízes e juízas fosse medida em desfechos rotulados externamente pelo DataJud: procedência e concessão de urgência. Terceira, esse é o desenho do artigo-base de Laneuville & Possebom, que compara desfechos dentro de estratos, e não a linguagem das decisões. A pergunta implica três frentes de literatura: (1) gênero do julgador e desfecho da decisão, incluindo como o efeito é identificado; (2) teoria: representação e "different voice" (Gilligan), in-group bias, socialização profissional como hipótese nula; (3) judicialização da saúde no Brasil como contexto do corpus. PLN jurídico não é frente, é nota de justificativa. Fora do escopo: tom, sentimento e estilo linguístico como variável dependente; tempo até sentença como frente de literatura.
- **Resposta original (27/09):** "A pergunta a ser respondida é se há viés decisório entre juízes e juízas nos Tribunais Regionais Federais (6) e Tribunais de Justiça (27) acerca do assunto de saúde."
- **Nota do entrevistador:** a resposta original não escolhe nenhuma opção e reformula a pergunta em torno de *viés decisório*, não de *tom*, sem justificar a mudança nem dizer quais frentes a nova pergunta implica. Isso abriu a Q2 e, mais tarde, a Q19, Q20 e Q23, cujas respostas estão incorporadas na consolidada.

### Q2. O que é "tom" na sua revisão?
- Opções: (A) sentimento polar + estilo linguístico; (B) só sentimento polar; (C) emoções discretas.
- **Resposta consolidada (28/09, após Q20, Q21, Q23, Q24 e Q25):** o tom não é mais construto da revisão. **Por quê:** o rótulo de tom vinha do LLM sem validação contra julgamento humano (kappa). Isso é uma avaliação subjetiva em cima de outra avaliação que já é subjetiva, a sentença. Sem validação não há como saber o que a variável mede, nem usar as classificações num modelo de machine learning. Essa subjetividade era o ponto de fragilidade do desenho, e por isso o orientador orientou substituir a classificação por tom pela clusterização, isto é, pela formação de grupos comparáveis de decisões. **O que entra no lugar:** estratos de comparação tribunal × ano, com erro-padrão agrupado por magistrado. **De onde vem:** do artigo-base. Laneuville & Possebom comparam desfechos dentro de comarca × trimestre no TJSP, explorando o sorteio de processos entre varas competentes (CPC/2015, art. 285). Nos 33 tribunais a comarca fica esparsa (3.251 unidades de origem, mediana de 13 processos, e 437 de 636 comarcas medidas têm um só gênero), então o estrato adotado é tribunal × ano de ajuizamento. O custo declarado: dentro de tribunal × ano, juiz e juíza podem estar em comarcas diferentes, e o que sustenta a comparação passa a ser o teste de balanceamento de covariáveis (assunto, tipo de réu, gênero da parte), não a aleatoriedade do sorteio. A comarca sai de graça do número CNJ e serve como teste de robustez nas 145 comarcas que têm os dois gêneros no mesmo ano. **Como responde à Q1:** a diferença de procedência e de concessão de urgência entre juízes e juízas dentro do estrato é a medida de viés decisório. **Magistrado:** entra como cluster de erro-padrão, porque cada juiz decide muitos casos e os erros são correlacionados dentro dele. Não entra como efeito fixo, porque o gênero não varia dentro do juiz e seria absorvido.
- **Resposta original (27/09):** "Não consideramos mais o tom decisório, visto que essa extração provinha de um modelo de LLM. Agora vamos utilizar clusterização por tribunal, ano e magistrado."
- **Revisão da premissa do projeto (pelo entrevistado):** o construto "tom por LLM", que era a variável dependente do piloto TJCE e do título, sai do desenho.
- **Nota do entrevistador:** a resposta original diz *que* o tom saiu e *o que* entra no lugar, mas não diz *por que*, nem *de onde vem* o desenho, nem *como* ele responde à pergunta da Q1. Dependências resolvidas em Q20 (por quê), Q21 (como), Q23 (de onde vem e a que custo) e Q24 (papel do magistrado), todas incorporadas na consolidada. A fonte da adaptação de comarca × trimestre para tribunal × ano é a seção 0.8 do documento `docs/matriz-artigo-x-relatorio.md` do repositório da dissertação.

### Q3. A revisão inclui estudos sobre efeito do gênero no RESULTADO da decisão ou só na LINGUAGEM?
- Opções: (A) resultado e linguagem; (B) só linguagem; (C) resultado como secundário.
- **Resposta consolidada (28/09, após Q6 e Q19):** resultado como frente principal. Linguagem não é frente: entra só como nota de justificativa, com 3 a 5 referências de PLN jurídico que documentam por que o tom foi abandonado.
- **Resposta original (27/09):** (A) Resultado e linguagem.
- **Nota do entrevistador:** a resposta original conflitava com Q2, que já tinha retirado o tom. Dependência resolvida em Q6 (linguagem vira secundária) e Q19 (deixa de ser frente).

### Q4. Escopo geográfico e de idioma?
- Opções: (A) internacional, inglês + português; (B) só Brasil; (C) inglês, português e espanhol.
- **Resposta:** (A) Internacional, inglês e português. Espanhol excluído.

---

## Rodada 2 — Nível 1 reaberto: o construto mudou

**Resumo do acordo antes da rodada:** pergunta = viés decisório entre juízes e juízas em ações de saúde nos 33 tribunais. Tom saiu. Escopo internacional em inglês e português.
**Ponto cego:** Q2 abandona tom e Q3 mantém linguagem. "Viés decisório" e "clusterização" sem definição operacional.

### Q5. O que é "viés decisório" operacionalmente? Qual desfecho o estudo precisa ter medido para entrar na matriz?
- Opções: (A) procedência + urgência; (B) só procedência; (C) procedência, urgência e tempo até sentença.
- **Resposta:** (C) Procedência, urgência e tempo.

### Q6. REVISÃO DA Q3: se o tom saiu do desenho, a frente "linguagem/sentimento em texto jurídico" continua na revisão?
- Opções: (A) fica como frente secundária, 3 a 5 referências para justificar o abandono do tom, sem string própria; (B) sai da revisão; (C) mantém como frente plena.
- **Resposta:** (A) Fica como frente secundária.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q3.** "Resultado e linguagem" passa a ser "resultado como frente principal, linguagem só como justificativa". Dependência Q2 → Q3 resolvida. (Na Q19 a linguagem deixou de ser frente e virou nota.)

### Q7. "Clusterização por tribunal, ano e magistrado" é estratégia de identificação ou método não supervisionado?
- Opções: (A) estratos de comparação: efeitos fixos tribunal × ano, erro-padrão agrupado por magistrado, literatura de judge effects; (B) clusterização não supervisionada (k-means) de perfis decisórios; (C) ambos.
- **Resposta:** (A) Estratos de comparação.
- **Nota do entrevistador:** a palavra "clusterização" na Q2 significava *cluster de erro-padrão e estratificação*, não aprendizado não supervisionado. Isso define a frente metodológica: judge effects e distribuição aleatória de processos.

### Q8. Qual moldura teórica explica POR QUE o gênero do julgador importaria?
- Opções: (A) teoria da representação + in-group bias; (B) socialização profissional (hipótese nula); (C) viés atitudinal.
- **Resposta:** (A) Teoria da representação e in-group bias. Hipótese nula plausível em saúde.

---

## Rodada 3 — Nível 2: bases, janela temporal e strings

**Resumo do acordo antes da rodada:** frentes definidas. Principal: gênero do julgador em procedência, urgência e tempo, identificação por estratos tribunal × ano. Teórica: representação e in-group. Contexto: judicialização da saúde. Secundária: sentimento em texto jurídico.
**Ponto cego:** três desfechos triplicam a literatura, e "tempo" puxa uma literatura de celeridade que não conversa com gênero.

### Q9. Quais bases a busca sistemática cobre?
- Opções: (A) Scopus + Web of Science + SciELO, Google Scholar só para snowballing; (B) Scopus + SciELO; (C) Scopus + WoS + SciELO + SSRN/NBER.
- **Resposta:** (A) Scopus, Web of Science e SciELO.

### Q10. Janela temporal da frente principal?
- Opções: (A) 2010–2026 + seminais sem limite por snowballing; (B) 2000–2026; (C) 2015–2026.
- **Resposta:** (A) 2010–2026, com seminais (Gilligan 1982; Songer & Crews-Meyer 2000; Steffensmeier & Hebert 1999) entrando por snowballing.

### Q11. String de busca da frente principal em inglês?
- Opções: (A) 3 blocos AND; (B) 3 blocos + bloco de desfecho; (C) 2 blocos amplos.
- **Resposta:** (A) `(judge* OR judicial OR court) AND (gender OR "female judge*" OR women OR sex) AND (decision* OR ruling* OR outcome* OR sentencing OR "judge effects" OR bias)`.
- **Nota do entrevistador:** a string não tem bloco de desfecho nem filtro de ano. Revisada na Q22.

### Q12. Frente de judicialização da saúde: marco inicial da janela em português?
- Opções: (A) 2009 em diante (audiência pública da saúde no STF, STA 175); (B) 2018 em diante (Tema 106 STJ); (C) sem limite inferior.
- **Resposta:** (A) 2009 em diante. String inicial: `(judicialização) AND (saúde OR medicamento*) AND (decisão OR sentença OR liminar)`. Revisada na Q22.

---

## Rodada 4 — Níveis 3 e 4: critérios e dependências abertas

**Resumo do acordo antes da rodada:** Scopus, WoS, SciELO. Frente principal 2010–2026 com seminais por snowballing, string de 3 blocos. Saúde de 2009 em diante.
**Pontos cegos:** a string da Q11 não tem termo de tempo, então o terceiro desfecho da Q5 não seria capturado. O artigo-base circula como working paper e um critério "só revisado por pares" o excluiria.

### Q13. Critério de inclusão por tipo de estudo?
- Opções: (A) empírico com gênero do julgador como variável independente + revisões sistemáticas; teóricos só na frente de teoria; (B) qualquer desenho, inclusive qualitativo; (C) só quantitativo com dados administrativos.
- **Resposta:** (A).

### Q14. REVISÃO DA Q5: a string não captura "tempo até sentença". O terceiro desfecho fica?
- Opções: (A) vira desfecho exploratório da dissertação, sem frente de literatura própria; (B) fica e a string ganha bloco de celeridade; (C) sai do desenho.
- **Resposta:** (A) Vira desfecho exploratório.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q5.** Desfechos da revisão passam a ser dois: procedência e urgência. Tempo continua na dissertação como análise exploratória. Dependência Q5 → Q11 resolvida.

### Q15. REVISÃO DA Q9: o artigo-base é working paper. Como a literatura cinzenta entra?
- Opções: (A) exceção nominal via snowballing: working papers entram se citados por 2+ estudos incluídos ou se forem o artigo-base, marcados como "cinzenta"; (B) adiciona SSRN/NBER como base; (C) exclui, artigo-base fica fora da matriz.
- **Resposta:** (A) Exceção nominal via snowballing.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q9.** A lista de bases não muda, mas o critério de elegibilidade ganha uma cláusula de exceção para literatura cinzenta. Dependência Q9 → Q13 resolvida.

### Q16. Critérios de EXCLUSÃO explícitos (múltipla escolha)?
- Opções: (A) gênero só das partes ou advogados; (B) júri, juízes leigos e arbitragem; (C) cortes internacionais e supremas cortes; (D) PLN sem variável de gênero.
- **Resposta:** (B) e (D). Ficam de fora júri, juízes leigos, arbitragem e estudos de PLN sem variável de gênero (salvo os 3 a 5 da nota de justificativa).
- **Nota do entrevistador:** (A) e (C) NÃO foram marcadas. Logo, estudos sobre gênero das partes e sobre supremas cortes permanecem elegíveis. Isso abre Q17.

---

## Rodada 5 — Nível 4: bordas

### Q17. Você manteve estudos sobre gênero das PARTES. A interação gênero do julgador × gênero da parte (in-group bias) vira construto na matriz?
- Opções: (A) sim, construto próprio "interação julgador × parte"; (B) não, gênero das partes só como controle.
- **Resposta:** (A) Sim, construto próprio. A base já infere gênero da parte por nome e IBGE.

### Q18. 17% das decisões têm gênero do magistrado indeterminado. Como a revisão trata estudos com o mesmo problema de medição?
- Opções: (A) coluna "lacuna" registra o método de inferência de gênero de cada estudo; (B) exclui estudos que inferem gênero por nome; (C) ignora.
- **Resposta:** (A). Cada estudo incluído declara como mediu gênero (autodeclaração, nome, cadastro oficial). Justifica a inferência por nome e IBGE da dissertação.

---

## Rodada 6 (28/09) — Nível 1 reaberto: justificar a mudança de escopo e fechar as strings

**Resumo do acordo antes da rodada:** pergunta = viés decisório; desfechos = procedência e urgência; estratos tribunal × ano; tom abandonado; bases, janela e critérios fechados.
**Ponto cego:** o transcript registrava *que* o tom saiu (Q2) e *que* a pergunta mudou (Q1), mas não *por quê*, nem *como* os estratos respondem à pergunta, nem quais frentes a nova pergunta implica. As strings da Q11 e Q12 não tinham bloco de desfecho, e as frentes 2 e 4 não tinham string.

### Q19. REVISÃO DA Q1: a pergunta "há viés decisório entre juízes e juízas em saúde" implica quais frentes de literatura? (múltipla escolha)
- Opções: (A) gênero do julgador e desfecho; (B) teoria: representação e in-group; (C) judicialização da saúde no Brasil; (D) PLN jurídico só como justificativa.
- **Resposta:** primeiro (A) e (C). Depois de pedir explicação sobre a alternativa (B) (Gilligan, "different voice", in-group bias e socialização profissional como hipótese nula), o entrevistado decidiu: "Mantenha a frente de teoria." Resultado: (A), (B) e (C). PLN deixa de ser frente e vira nota de justificativa dentro do protocolo.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q1 e Q6.** A pergunta da Q1 passa a ter frentes explícitas: 1 gênero do julgador e desfecho, 2 teoria, 3 judicialização da saúde. A "frente secundária de PLN" da Q6 deixa de ser frente. Dependência Q1 → matriz resolvida.

### Q20. REVISÃO DA Q2: por que o tom por LLM saiu do desenho?
- Opções: (A) validade: rótulo sem validação por anotadores humanos; (B) reprodutibilidade e custo; (C) validade + reprodutibilidade + desfecho já rotulado pelo DataJud.
- **Resposta:** "O rótulo de tom vinha do LLM sem validação contra julgamento humano (kappa), o que indicaria uma avaliação subjetiva em cima de outra avaliação que já é por si só também subjetiva. Sem isso, não há como saber o que a variável mede ou sequer utilizar as classificações num modelo de machine learning."
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q2.** A decisão de abandonar o tom ganha justificativa de validade de construto: a sentença já é um juízo subjetivo do magistrado, e o LLM colocaria um segundo juízo subjetivo por cima, sem kappa contra anotadores humanos. O desfecho do DataJud (tipo_decisao) é rótulo externo e independente do texto. Dependência Q2 → REVISAO.md resolvida.

### Q21. REVISÃO DA Q2 e Q7: como os estratos tribunal × ano × magistrado respondem à pergunta da revisão?
- Opções: (A) são a identificação: dentro de tribunal × ano, o processo é distribuído por sorteio entre varas (CPC art. 285), então juiz e juíza recebem casos comparáveis; a diferença de procedência dentro do estrato é o viés; erro-padrão agrupado por magistrado porque cada juiz decide muitos casos; (B) são só controles numa regressão.
- **Resposta:** (A) São a identificação.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q7.** "Estratos de comparação" deixa de ser só o nome do método e passa a ser o argumento causal: o sorteio dentro do estrato é o que torna a comparação entre juízes e juízas defensável. Isso liga a Q2 à Q1 e define o construto "estrato de comparação" da matriz (Abrams, Bertrand & Mullainathan; Shayo & Zussman; Laneuville & Possebom).

### Q22. REVISÃO DA Q11 e Q12: strings revisadas com bloco de desfecho, filtro de ano e string própria para a frente de teoria. Aceita?
- Opções: (A) aceita as três; (B) só frentes 1 e 3; (C) manter como está.
- **Resposta:** (A) Aceita as três.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q11 e Q12.** Strings finais:
  - Frente 1 (Scopus/WoS): `TITLE-ABS-KEY((judge* OR judicial OR court*) AND (gender OR "female judge*" OR "women judge*" OR sex) AND (decision* OR ruling* OR sentencing OR "judge effects" OR bias) AND (grant* OR injunction* OR "win rate" OR "plaintiff success" OR outcome* OR "case outcome*")) AND PUBYEAR > 2009`
  - Frente 2 (Scopus/WoS, teoria): `TITLE-ABS-KEY(("in-group bias" OR "ingroup bias" OR "different voice" OR "representative bureaucracy" OR "descriptive representation") AND (judge* OR judicial OR court*))`
  - Frente 3 (SciELO/Scopus, saúde): `(judicialização OR judicialization) AND (saúde OR health OR medicamento* OR medicine*) AND (decisão OR sentença OR liminar OR deferimento OR concessão OR procedência OR ruling OR injunction) AND (Brasil OR Brazil)`, ano ≥ 2009.
  - Dependência Q14 → Q11 resolvida: o bloco de desfecho cobre procedência (outcome, win rate, plaintiff success) e urgência (grant, injunction), sem termo de tempo.

---

## Rodada 7 (28/09) — Nível 1 reaberto: de onde vem a clusterização e como registrá-la

**Resumo do acordo antes da rodada:** viés decisório em procedência e urgência; estratos tribunal × ano como identificação; erro-padrão agrupado por magistrado; tom abandonado por falta de validade.
**Ponto cego:** o autograder avalia cada resposta no lugar em que aparece, e as respostas da Q1 e Q2 continuavam curtas, com as justificativas só na rodada 6. Além disso, a Q2 dizia "clusterização por tribunal, ano e magistrado" sem dizer de onde vinha esse desenho (Laneuville & Possebom comparam dentro de comarca × trimestre) nem por que foi adaptado. E "magistrado" como cluster tem uma armadilha: efeito fixo de magistrado absorveria o gênero.

### Q23. REVISÃO DA Q2: de onde vem a "clusterização" e por que tribunal × ano em vez do desenho original de Possebom?
- Opções: (A) adaptação declarada com custo: Possebom compara dentro de comarca × trimestre explorando o sorteio entre varas; nos 33 tribunais a comarca fica esparsa, então o estrato vira tribunal × ano, e o balanceamento de covariáveis substitui o sorteio; (B) mesmo desenho do artigo, comarca × trimestre; (C) tribunal × ano principal, comarca como robustez.
- **Resposta:** "A subjetividade do tom era um ponto de fragilidade. Por conta disso o orientador orientou o uso de clusterização como alternativa para criação dos grupos similares, ao invés de classificar via tom com LLM e subjetividade."
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q2.** A resposta dá a origem da decisão, que faltava: a clusterização é orientação do orientador, motivada pela fragilidade do tom, e seu papel é formar grupos comparáveis de decisões. O entrevistador registra, com base na seção 0.8 do documento de matriz artigo × relatório do repositório da dissertação, que o desenho adotado é o (A): tribunal × ano como estrato principal, com comarca como robustez, e com o custo declarado de que o balanceamento de covariáveis substitui a garantia de sorteio. Incorporado na resposta consolidada da Q2.

### Q24. REVISÃO DA Q7 e Q21: o magistrado entra como cluster de erro-padrão ou como efeito fixo?
- Opções: (A) cluster de erro-padrão, sem efeito fixo: cada juiz decide muitos casos e os erros são correlacionados dentro dele; efeito fixo é impossível porque o gênero não varia dentro do juiz; (B) efeito fixo de magistrado.
- **Resposta:** (A) Cluster de erro-padrão, sem efeito fixo.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q7 e Q21.** "Erro-padrão agrupado por magistrado" ganha a justificativa e a exclusão explícita do efeito fixo de magistrado, que absorveria a variável de interesse. Unidade de tratamento é o magistrado; unidade de observação é a decisão.

### Q25. REVISÃO DO REGISTRO DE Q1 e Q2: como registrar as justificativas para que sejam avaliadas no lugar certo?
- Opções: (A) resposta consolidada completa e autocontida, com a resposta original preservada logo abaixo; (B) substituir a original; (C) manter só complementos.
- **Resposta:** (A) Resposta consolidada + original preservada.
- **REVISÃO DE DECISÃO ANTERIOR: revisa o registro de Q1, Q2 e Q3.** Nada é apagado. A consolidada vale para o protocolo; a original mostra a evolução que a reflexão descreve.

---

## Acordo final (estado da árvore de decisão)

| Nó | Decisão | Origem |
|---|---|---|
| Pergunta da revisão | Há viés decisório entre juízes e juízas em ações de saúde nos 27 TJs e 6 TRFs? Frentes: gênero do julgador e desfecho; teoria; judicialização da saúde | Q1 revisada por Q19 |
| Construto principal | Viés decisório = diferença por gênero do julgador em procedência e em concessão de urgência, dentro de estratos tribunal × ano × assunto | Q5 revisada por Q14 |
| Construto secundário | Interação gênero do julgador × gênero da parte (in-group) | Q17 |
| Construto abandonado | Tom/sentimento por LLM: sem validação por anotadores humanos, juízo subjetivo sobre juízo subjetivo. Orientador orientou clusterização no lugar | Q2 revisada por Q20 e Q23 |
| Identificação | Estratos tribunal × ano, adaptação declarada do desenho comarca × trimestre de Laneuville & Possebom; balanceamento de covariáveis substitui o sorteio; comarca como robustez; erro-padrão agrupado por magistrado, sem efeito fixo de magistrado | Q7 revisada por Q21, Q23 e Q24 |
| Teoria | Representação (Gilligan), in-group bias, socialização profissional como hipótese nula | Q8, Q19 |
| Frentes | 1 gênero do julgador e desfecho; 2 teoria; 3 judicialização da saúde. PLN é nota de justificativa, não frente | Q19 |
| Bases | Scopus, Web of Science, SciELO; Google Scholar só para snowballing | Q9 |
| Cinzenta | Só por snowballing: artigo-base ou citado por 2+ incluídos, marcado "cinzenta" | Q15 |
| Janela | Frente 1: 2010–2026 + seminais. Frente 2: sem limite, por snowballing + string. Frente 3: 2009–2026 | Q10, Q12 |
| Strings | Três strings booleanas com bloco de desfecho e filtro de ano | Q11, Q12 revisadas por Q22 |
| Idiomas | Inglês e português | Q4 |
| Inclusão | Empírico quantitativo com gênero do julgador como VI; revisões sistemáticas; teóricos só na frente 2 | Q13 |
| Exclusão | Júri, juízes leigos, arbitragem; PLN sem variável de gênero | Q16 |
| Medição de gênero | Coluna lacuna registra o método de cada estudo | Q18 |
