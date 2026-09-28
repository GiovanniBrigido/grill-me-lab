# grill-me — transcript da entrevista

**Tema:** protocolo de revisão bibliográfica da dissertação de mestrado
**Título de partida da dissertação:** "Sentenças de juízes e juízas no Brasil: há diferença de tom?"
**Corpus:** sentenças de 1º grau em ações de saúde, 27 Tribunais de Justiça e 6 Tribunais Regionais Federais (33 tribunais), 2017–2026
**Skill:** grill-me (`.claude/skills/grill-me/SKILL.md`)
**Data:** 27 e 28/09/2026
**Entrevistado:** Giovanni Brigido
**Entrevistador:** Claude Code (Fable 5.1)

Formato: cada pergunta tem número (Q1, Q2, ...), nível da árvore de decisão, opções apresentadas e uma única linha **Resposta do aluno**, seguida, quando for o caso, de nota do entrevistador e da marca **REVISÃO DE DECISÃO ANTERIOR** com a pergunta que ela reabre. As respostas de Q1, Q2 e Q3 são as consolidadas em 28/09; as originais de 27/09 estão no apêndice ao fim do arquivo (decisão da Q27).

Contagem: 28 perguntas respondidas. 11 revisões explícitas de decisão anterior (Q6 revisa Q3, Q14 revisa Q5, Q15 revisa Q9, Q19 revisa Q1, Q20 revisa Q2, Q21 revisa Q7, Q22 revisa Q11 e Q12, Q23 revisa Q2, Q24 revisa Q7 e Q21, Q25 revisa o registro de Q1 a Q3, Q27 revisa Q25).

---

## Rodada 1 — Nível 1: pergunta da revisão e construtos

**Resumo do acordo antes da rodada:** a dissertação perguntava se há diferença de sentimento (tom) entre sentenças de juízes e juízas. O artigo-base (Laneuville & Possebom) mede resultado, não linguagem. A revisão ainda não tinha pergunta própria.

### Q1. Qual é a pergunta da REVISÃO (não a da dissertação)?
- Opções: (A) três frentes integradas: gênero do julgador, sentimento em texto jurídico, judicialização da saúde; (B) duas frentes; (C) uma frente estreita só de linguagem.
- **Resposta do aluno:** A pergunta da revisão é: há viés decisório entre juízes e juízas nos 6 Tribunais Regionais Federais e nos 27 Tribunais de Justiça em ações de saúde? Ela substitui a pergunta original sobre tom por três razões. Primeira, o tom era medido por LLM sem validação contra julgamento humano, um juízo subjetivo sobre outro juízo subjetivo, e esse era o ponto de fragilidade do desenho. Segunda, o orientador orientou trocar a classificação por tom pela formação de grupos comparáveis (clusterização por tribunal, ano e magistrado), para medir a diferença entre juízes e juízas em desfechos rotulados externamente pelo DataJud: procedência e concessão de urgência. Terceira, esse é o desenho do artigo-base de Laneuville & Possebom, que compara desfechos dentro de estratos, não a linguagem das decisões. A pergunta implica três frentes de literatura: (1) gênero do julgador e desfecho da decisão, incluindo como o efeito é identificado; (2) teoria: representação e "different voice" (Gilligan), in-group bias, socialização profissional como hipótese nula; (3) judicialização da saúde no Brasil como contexto do corpus. PLN jurídico não é frente, é nota de justificativa. Fora do escopo: tom, sentimento e estilo linguístico como variável dependente; tempo até sentença como frente de literatura.
- **Nota do entrevistador:** a resposta original de 27/09 (apêndice) reformulava a pergunta sem justificar a mudança nem listar frentes. As justificativas vieram em Q19, Q20 e Q23 e foram consolidadas aqui.

### Q2. O que é "tom" na sua revisão?
- Opções: (A) sentimento polar + estilo linguístico; (B) só sentimento polar; (C) emoções discretas.
- **Resposta do aluno:** O tom não é mais construto da revisão. Por quê: o rótulo de tom vinha do LLM sem validação contra julgamento humano (kappa). Isso é uma avaliação subjetiva em cima de outra avaliação que já é subjetiva, a sentença. Sem validação não há como saber o que a variável mede, nem usar as classificações num modelo de machine learning. Essa subjetividade era o ponto de fragilidade, e por isso o orientador orientou substituir a classificação por tom pela clusterização, isto é, pela formação de grupos comparáveis de decisões. O que entra no lugar: estratos de comparação tribunal × ano, com erro-padrão agrupado por magistrado. De onde vem: do artigo-base. Laneuville & Possebom comparam desfechos dentro de comarca × trimestre no TJSP, explorando o sorteio de processos entre varas competentes (CPC/2015, art. 285). Nos 33 tribunais a comarca fica esparsa (3.251 unidades de origem, mediana de 13 processos, e 437 de 636 comarcas medidas têm um só gênero), então o estrato adotado é tribunal × ano de ajuizamento. O custo: dentro de tribunal × ano, juiz e juíza podem estar em comarcas diferentes, e o que sustenta a comparação passa a ser o teste de balanceamento de covariáveis (assunto, tipo de réu, gênero da parte), não a aleatoriedade do sorteio. A comarca sai de graça do número CNJ e serve como teste de robustez nas 145 comarcas com os dois gêneros no mesmo ano. Como responde à Q1: a diferença de procedência e de concessão de urgência entre juízes e juízas dentro do estrato é a medida de viés decisório. Magistrado: entra como cluster de erro-padrão, porque cada juiz decide muitos casos e os erros são correlacionados dentro dele. Não entra como efeito fixo, porque o gênero não varia dentro do juiz e seria absorvido.
- **Revisão da premissa do projeto (pelo aluno):** o construto "tom por LLM", variável dependente do piloto TJCE e do título, sai do desenho.
- **Nota do entrevistador:** a resposta original de 27/09 (apêndice) dizia só que o tom saía e que entrava clusterização. As dependências (por quê, de onde vem, a que custo, como responde à Q1, papel do magistrado) foram resolvidas em Q20, Q21, Q23 e Q24. A fonte da adaptação de comarca × trimestre para tribunal × ano é a seção 0.8 do documento `docs/matriz-artigo-x-relatorio.md` do repositório da dissertação.

### Q3. A revisão inclui estudos sobre efeito do gênero no RESULTADO da decisão ou só na LINGUAGEM?
- Opções: (A) resultado e linguagem; (B) só linguagem; (C) resultado como secundário.
- **Resposta do aluno:** Resultado é a frente principal. Linguagem não é frente: entra só como nota de justificativa, com 3 a 5 referências de PLN jurídico que documentam por que o tom foi abandonado. Escolhi originalmente "resultado e linguagem", o que conflitava com a Q2; a Q6 e a Q19 resolveram o conflito nesta direção.
- **Nota do entrevistador:** resposta original no apêndice.

### Q4. Escopo geográfico e de idioma?
- Opções: (A) internacional, inglês + português; (B) só Brasil; (C) inglês, português e espanhol.
- **Resposta do aluno:** Escopo internacional, em inglês e português. A literatura sobre gênero do julgador é majoritariamente norte-americana e a de judicialização da saúde é brasileira, então preciso das duas línguas. Espanhol fica fora: adicionaria triagem da América Latina com ganho incerto para o meu desfecho.

---

## Rodada 2 — Nível 1 reaberto: o construto mudou

**Resumo do acordo antes da rodada:** pergunta = viés decisório entre juízes e juízas em ações de saúde nos 33 tribunais. Tom saiu. Escopo internacional em inglês e português.
**Ponto cego:** Q2 abandona tom e Q3 mantém linguagem. "Viés decisório" e "clusterização" sem definição operacional.

### Q5. O que é "viés decisório" operacionalmente? Qual desfecho o estudo precisa ter medido para entrar na matriz?
- Opções: (A) procedência + urgência; (B) só procedência; (C) procedência, urgência e tempo até sentença.
- **Resposta do aluno:** Três desfechos: procedência (tipo_decisao do DataJud: procedente, parcial, improcedente), concessão de tutela de urgência (resultado_urgencia_1a via TPU do CNJ) e tempo até sentença (dias_ate_sentenca). Os três já existem na minha base para os 33 tribunais.

### Q6. REVISÃO DA Q3: se o tom saiu do desenho, a frente "linguagem/sentimento em texto jurídico" continua na revisão?
- Opções: (A) fica como frente secundária, 3 a 5 referências para justificar o abandono do tom, sem string própria; (B) sai da revisão; (C) mantém como frente plena.
- **Resposta do aluno:** Fica como frente secundária, com 3 a 5 referências e sem string de busca própria. A função dela é justificar por que o piloto do TJCE media tom e a dissertação não: validade, reprodutibilidade e custo. Tirar a frente inteira deixaria a banca sem resposta para essa pergunta.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q3.** "Resultado e linguagem" passa a ser "resultado como frente principal, linguagem só como justificativa". Dependência Q2 → Q3 resolvida. (Na Q19 a linguagem deixou de ser frente e virou nota.)

### Q7. "Clusterização por tribunal, ano e magistrado" é estratégia de identificação ou método não supervisionado?
- Opções: (A) estratos de comparação: efeitos fixos tribunal × ano, erro-padrão agrupado por magistrado, literatura de judge effects; (B) clusterização não supervisionada (k-means) de perfis decisórios; (C) ambos.
- **Resposta do aluno:** É estratégia de identificação, não k-means. Estratos de comparação tribunal × ano, com erro-padrão agrupado por magistrado. A literatura que preciso buscar é a de judge effects e distribuição aleatória de processos (Boyd, Epstein & Martin; Abrams, Bertrand & Mullainathan; Laneuville & Possebom), não a de aprendizado não supervisionado.
- **Nota do entrevistador:** a palavra "clusterização" na Q2 significava estratificação com cluster de erro-padrão. Isso define a frente metodológica.

### Q8. Qual moldura teórica explica POR QUE o gênero do julgador importaria?
- Opções: (A) teoria da representação + in-group bias; (B) socialização profissional (hipótese nula); (C) viés atitudinal.
- **Resposta do aluno:** Teoria da representação e in-group bias: juízas decidiriam diferente por experiência compartilhada com autoras (Gilligan), e a evidência empírica de Boyd, Epstein & Martin acha efeito só em discriminação sexual. Em ações de saúde, onde os parâmetros vêm de precedentes vinculantes do STF e STJ, a hipótese nula por socialização profissional é plausível e entra como contraste.

---

## Rodada 3 — Nível 2: bases, janela temporal e strings

**Resumo do acordo antes da rodada:** frentes definidas. Principal: gênero do julgador em procedência, urgência e tempo, identificação por estratos tribunal × ano. Teórica: representação e in-group. Contexto: judicialização da saúde. Secundária: sentimento em texto jurídico.
**Ponto cego:** três desfechos triplicam a literatura, e "tempo" puxa uma literatura de celeridade que não conversa com gênero.

### Q9. Quais bases a busca sistemática cobre?
- Opções: (A) Scopus + Web of Science + SciELO, Google Scholar só para snowballing; (B) Scopus + SciELO; (C) Scopus + WoS + SciELO + SSRN/NBER.
- **Resposta do aluno:** Scopus, Web of Science e SciELO. Duas bases internacionais para a literatura em inglês (ciência política e economia) e uma para a produção brasileira em português. Google Scholar entra só para snowballing das referências citadas, sem contar como base, porque não é curado. SSRN e NBER ficam fora da busca sistemática.

### Q10. Janela temporal da frente principal?
- Opções: (A) 2010–2026 + seminais sem limite por snowballing; (B) 2000–2026; (C) 2015–2026.
- **Resposta do aluno:** De 2010 a 2026. Boyd, Epstein & Martin (2010) é o divisor: antes dele a literatura de gênero do julgador não usava identificação causal. Os seminais anteriores (Gilligan 1982; Steffensmeier & Hebert 1999; Songer & Crews-Meyer 2000) entram por snowballing, sem limite de ano.

### Q11. String de busca da frente principal em inglês?
- Opções: (A) 3 blocos AND; (B) 3 blocos + bloco de desfecho; (C) 2 blocos amplos.
- **Resposta do aluno:** Três blocos AND: `(judge* OR judicial OR court) AND (gender OR "female judge*" OR women OR sex) AND (decision* OR ruling* OR outcome* OR sentencing OR "judge effects" OR bias)`. Escolhi não colocar bloco de desfecho para não derrubar o recall em ciência política.
- **Nota do entrevistador:** a string não tinha bloco de desfecho nem filtro de ano. Revisada na Q22.

### Q12. Frente de judicialização da saúde: marco inicial da janela em português?
- Opções: (A) 2009 em diante (audiência pública da saúde no STF, STA 175); (B) 2018 em diante (Tema 106 STJ); (C) sem limite inferior.
- **Resposta do aluno:** De 2009 em diante. A audiência pública da saúde no STF (2009) e a STA 175 (2010) fixaram os parâmetros que os juízes de 1º grau aplicam até hoje. Começar em 2018 (Tema 106 do STJ) coincidiria com o corpus, mas perderia a literatura que explica o fenômeno. String inicial: `(judicialização) AND (saúde OR medicamento*) AND (decisão OR sentença OR liminar)`.
- **Nota do entrevistador:** string revisada na Q22.

---

## Rodada 4 — Níveis 3 e 4: critérios e dependências abertas

**Resumo do acordo antes da rodada:** Scopus, WoS, SciELO. Frente principal 2010–2026 com seminais por snowballing, string de 3 blocos. Saúde de 2009 em diante.
**Pontos cegos:** a string da Q11 não tem termo de tempo, então o terceiro desfecho da Q5 não seria capturado. O artigo-base circula como working paper e um critério "só revisado por pares" o excluiria.

### Q13. Critério de inclusão por tipo de estudo?
- Opções: (A) empírico com gênero do julgador como variável independente + revisões sistemáticas; teóricos só na frente de teoria; (B) qualquer desenho, inclusive qualitativo; (C) só quantitativo com dados administrativos.
- **Resposta do aluno:** Entram estudos empíricos quantitativos em que o gênero do magistrado é variável independente, e revisões sistemáticas ou meta-análises sobre gênero e decisão judicial. Textos teóricos entram só na frente de teoria. Não restrinjo a dados administrativos porque parte da literatura de in-group bias usa experimentos de vinheta.

### Q14. REVISÃO DA Q5: a string não captura "tempo até sentença". O terceiro desfecho fica?
- Opções: (A) vira desfecho exploratório da dissertação, sem frente de literatura própria; (B) fica e a string ganha bloco de celeridade; (C) sai do desenho.
- **Resposta do aluno:** Tempo até sentença vira análise exploratória da dissertação, sem frente de literatura. Os desfechos da revisão ficam dois: procedência e urgência. Adicionar bloco de celeridade à string traria literatura de gestão judiciária que não conversa com gênero.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q5.** Desfechos passam de três para dois. Dependência Q5 → Q11 resolvida.

### Q15. REVISÃO DA Q9: o artigo-base é working paper. Como a literatura cinzenta entra?
- Opções: (A) exceção nominal via snowballing: working papers entram se citados por 2+ estudos incluídos ou se forem o artigo-base, marcados como "cinzenta"; (B) adiciona SSRN/NBER como base; (C) exclui, artigo-base fica fora da matriz.
- **Resposta do aluno:** Exceção nominal via snowballing. A busca sistemática continua só em revisados por pares, mas working papers entram se forem o artigo-base (Laneuville & Possebom) ou se forem citados por dois ou mais estudos incluídos, marcados como "cinzenta" na coluna base. Deixar o artigo-base fora da matriz seria estranho para a banca.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q9.** A lista de bases não muda, mas o critério de elegibilidade ganha uma cláusula de exceção. Dependência Q9 → Q13 resolvida.

### Q16. Critérios de EXCLUSÃO explícitos (múltipla escolha)?
- Opções: (A) gênero só das partes ou advogados; (B) júri, juízes leigos e arbitragem; (C) cortes internacionais e supremas cortes; (D) PLN sem variável de gênero.
- **Resposta do aluno:** Excluo júri, juízes leigos e arbitragem, porque o mecanismo de socialização desses decisores é outro, e excluo estudos de PLN sem variável de gênero, salvo os 3 a 5 da nota de justificativa. Não excluo estudos sobre gênero das partes nem sobre supremas cortes: os primeiros alimentam a interação julgador × parte e os segundos incluem parte da literatura seminal.
- **Nota do entrevistador:** (A) e (C) não foram marcadas, o que abre Q17.

---

## Rodada 5 — Nível 4: bordas

### Q17. Você manteve estudos sobre gênero das PARTES. A interação gênero do julgador × gênero da parte (in-group bias) vira construto na matriz?
- Opções: (A) sim, construto próprio "interação julgador × parte"; (B) não, gênero das partes só como controle.
- **Resposta do aluno:** Sim, vira construto próprio. Minha base já infere o gênero da parte autora por nome e IBGE, então estudos de in-group bias entram com o construto "interação julgador × parte". É coerente com a moldura teórica da Q8.

### Q18. 17% das decisões têm gênero do magistrado indeterminado. Como a revisão trata estudos com o mesmo problema de medição?
- Opções: (A) coluna "lacuna" registra o método de inferência de gênero de cada estudo; (B) exclui estudos que inferem gênero por nome; (C) ignora.
- **Resposta do aluno:** A coluna "lacuna" da matriz registra como cada estudo mediu o gênero do julgador: autodeclaração, cadastro oficial, nome ou não informado. Estudos sem descrição entram com a lacuna marcada. Isso justifica minha própria inferência por nome e IBGE e explicita os 17% indeterminados. Excluir estudos que inferem por nome excluiria o meu próprio método.

---

## Rodada 6 (28/09) — Nível 1 reaberto: justificar a mudança de escopo e fechar as strings

**Resumo do acordo antes da rodada:** pergunta = viés decisório; desfechos = procedência e urgência; estratos tribunal × ano; tom abandonado; bases, janela e critérios fechados.
**Ponto cego:** o transcript registrava que o tom saiu (Q2) e que a pergunta mudou (Q1), mas não por quê, nem como os estratos respondem à pergunta, nem quais frentes a nova pergunta implica. As strings da Q11 e Q12 não tinham bloco de desfecho, e as frentes 2 e 4 não tinham string.

### Q19. REVISÃO DA Q1: a pergunta "há viés decisório entre juízes e juízas em saúde" implica quais frentes de literatura? (múltipla escolha)
- Opções: (A) gênero do julgador e desfecho; (B) teoria: representação e in-group; (C) judicialização da saúde no Brasil; (D) PLN jurídico só como justificativa.
- **Resposta do aluno:** Marquei primeiro gênero do julgador e desfecho, e judicialização da saúde. Depois pedi que o entrevistador explicasse a alternativa de Gilligan (representação, "different voice", in-group bias e socialização profissional como hipótese nula) e decidi: "Mantenha a frente de teoria." Resultado: três frentes, (A), (B) e (C). Sem ela, eu testaria uma diferença sem dizer que mecanismo esperaria encontrar. PLN deixa de ser frente e vira nota de justificativa.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q1 e Q6.** A pergunta da Q1 passa a ter frentes explícitas. A "frente secundária de PLN" da Q6 deixa de ser frente. Dependência Q1 → matriz resolvida.

### Q20. REVISÃO DA Q2: por que o tom por LLM saiu do desenho?
- Opções: (A) validade: rótulo sem validação por anotadores humanos; (B) reprodutibilidade e custo; (C) validade + reprodutibilidade + desfecho já rotulado pelo DataJud.
- **Resposta do aluno:** "O rótulo de tom vinha do LLM sem validação contra julgamento humano (kappa), o que indicaria uma avaliação subjetiva em cima de outra avaliação que já é por si só também subjetiva. Sem isso, não há como saber o que a variável mede ou sequer utilizar as classificações num modelo de machine learning."
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q2.** A decisão de abandonar o tom ganha justificativa de validade de construto. O desfecho do DataJud (tipo_decisao) é rótulo externo e independente do texto. Dependência Q2 → REVISAO.md resolvida.

### Q21. REVISÃO DA Q2 e Q7: como os estratos tribunal × ano × magistrado respondem à pergunta da revisão?
- Opções: (A) são a identificação: dentro de tribunal × ano, o processo é distribuído por sorteio entre varas (CPC art. 285), então juiz e juíza recebem casos comparáveis; a diferença de procedência dentro do estrato é o viés; (B) são só controles numa regressão.
- **Resposta do aluno:** São a identificação, não meros controles. Dentro de tribunal × ano o processo é distribuído por sorteio entre as varas competentes (CPC/2015, art. 285), então juiz e juíza recebem casos comparáveis, e a diferença de procedência e de urgência dentro do estrato é a medida de viés decisório. O erro-padrão é agrupado por magistrado porque cada juiz decide muitos casos.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q7.** "Estratos de comparação" deixa de ser só o nome do método e passa a ser o argumento causal que liga a Q2 à Q1. Define o construto "estrato de comparação" da matriz.

### Q22. REVISÃO DA Q11 e Q12: strings revisadas com bloco de desfecho, filtro de ano e string própria para a frente de teoria. Aceita?
- Opções: (A) aceita as três; (B) só frentes 1 e 3; (C) manter como está.
- **Resposta do aluno:** Aceito as três. A frente 1 ganha o quarto bloco de desfecho e o filtro de ano; a frente 2 ganha string própria; a frente 3 ganha os termos de resultado. Strings finais:
  - Frente 1 (Scopus/WoS): `TITLE-ABS-KEY((judge* OR judicial OR court*) AND (gender OR "female judge*" OR "women judge*" OR sex) AND (decision* OR ruling* OR sentencing OR "judge effects" OR bias) AND (grant* OR injunction* OR "win rate" OR "plaintiff success" OR outcome* OR "case outcome*")) AND PUBYEAR > 2009`
  - Frente 2 (Scopus/WoS, teoria): `TITLE-ABS-KEY(("in-group bias" OR "ingroup bias" OR "different voice" OR "representative bureaucracy" OR "descriptive representation") AND (judge* OR judicial OR court*))`
  - Frente 3 (SciELO/Scopus, saúde): `(judicialização OR judicialization) AND (saúde OR health OR medicamento* OR medicine*) AND (decisão OR sentença OR liminar OR deferimento OR concessão OR procedência OR ruling OR injunction) AND (Brasil OR Brazil)`, ano ≥ 2009.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q11 e Q12.** O bloco de desfecho cobre procedência (outcome, win rate, plaintiff success) e urgência (grant, injunction), sem termo de tempo. Dependência Q14 → Q11 resolvida.

---

## Rodada 7 (28/09) — Nível 1 reaberto: de onde vem a clusterização e como registrá-la

**Resumo do acordo antes da rodada:** viés decisório em procedência e urgência; estratos tribunal × ano como identificação; erro-padrão agrupado por magistrado; tom abandonado por falta de validade.
**Ponto cego:** a Q2 dizia "clusterização por tribunal, ano e magistrado" sem dizer de onde vinha esse desenho (Laneuville & Possebom comparam dentro de comarca × trimestre) nem por que foi adaptado. E "magistrado" como cluster tem uma armadilha: efeito fixo de magistrado absorveria o gênero.

### Q23. REVISÃO DA Q2: de onde vem a "clusterização" e por que tribunal × ano em vez do desenho original de Possebom?
- Opções: (A) adaptação declarada com custo: Possebom compara dentro de comarca × trimestre explorando o sorteio entre varas; nos 33 tribunais a comarca fica esparsa, então o estrato vira tribunal × ano, e o balanceamento de covariáveis substitui o sorteio; (B) mesmo desenho do artigo; (C) tribunal × ano principal, comarca como robustez.
- **Resposta do aluno:** "A subjetividade do tom era um ponto de fragilidade. Por conta disso o orientador orientou o uso de clusterização como alternativa para criação dos grupos similares, ao invés de classificar via tom com LLM e subjetividade." A adaptação do estrato é a da opção (A) com a robustez da (C): tribunal × ano como estrato principal, porque a comarca fica esparsa nos 33 tribunais, e comarca × ano como teste de robustez nas comarcas que têm os dois gêneros.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q2.** A resposta dá a origem da decisão, que faltava: a clusterização é orientação do orientador, motivada pela fragilidade do tom, e seu papel é formar grupos comparáveis. A adaptação está documentada na seção 0.8 do documento de matriz artigo × relatório do repositório da dissertação. Incorporado na Q2.

### Q24. REVISÃO DA Q7 e Q21: o magistrado entra como cluster de erro-padrão ou como efeito fixo?
- Opções: (A) cluster de erro-padrão, sem efeito fixo; (B) efeito fixo de magistrado.
- **Resposta do aluno:** Cluster de erro-padrão, sem efeito fixo. Cada juiz decide muitos casos, então os erros são correlacionados dentro do juiz. Efeito fixo de magistrado é impossível para a minha pergunta: o gênero não varia dentro do juiz e seria absorvido. A unidade de tratamento é o magistrado; a unidade de observação é a decisão.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q7 e Q21.** "Erro-padrão agrupado por magistrado" ganha justificativa e a exclusão explícita do efeito fixo.

### Q25. REVISÃO DO REGISTRO DE Q1 e Q2: como registrar as justificativas para que sejam avaliadas no lugar certo?
- Opções: (A) resposta consolidada completa, com a original preservada logo abaixo; (B) substituir a original; (C) manter só complementos.
- **Resposta do aluno:** Resposta consolidada completa e autocontida em Q1 e Q2, com a resposta original preservada logo abaixo. Nada é apagado, porque a evolução da decisão é o que o REVISAO.md descreve.
- **REVISÃO DE DECISÃO ANTERIOR: revisa o registro de Q1, Q2 e Q3.** (Revisada de novo na Q27.)

---

## Rodada 8 (28/09) — Nível 3: formato do registro

**Resumo do acordo antes da rodada:** conteúdo fechado em 25 perguntas e 10 revisões.
**Ponto cego:** o formato. Das 25 respostas, 14 eram só a letra da opção escolhida, e três perguntas tinham duas respostas (consolidada e original), o que um leitor externo lê como conflito.

### Q26. REVISÃO DO FORMATO: as respostas que são só "(A)" viram frases completas na sua voz, com o conteúdo da opção escolhida?
- Opções: (A) sim, expandir todas; (B) manter as letras.
- **Resposta do aluno:** Sim, expandir todas. Cada resposta vira uma ou duas frases em primeira pessoa restabelecendo o que escolhi e por quê, com o conteúdo da opção que marquei. Nada novo é inventado.

### Q27. REVISÃO DA Q25: o que fazer com as respostas originais vagas de Q1, Q2 e Q3?
- Opções: (A) mover para apêndice no fim; (B) remover as originais; (C) manter inline.
- **Resposta do aluno:** Mover para um apêndice no fim do arquivo, com a data. Abaixo de cada pergunta fica só a resposta consolidada. O histórico continua no arquivo, mas ninguém lê duas respostas na mesma pergunta.
- **REVISÃO DE DECISÃO ANTERIOR: revisa Q25.** "Original preservada logo abaixo" vira "original preservada em apêndice".

### Q28. Padronizar o rótulo: toda pergunta terá exatamente uma linha "Resposta do aluno"?
- Opções: (A) sim, rótulo único; (B) manter rótulos variados.
- **Resposta do aluno:** Sim, rótulo único. Uma linha "Resposta do aluno" por pergunta, sempre logo abaixo das opções. Notas do entrevistador e marcas de revisão vêm depois.

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
| Registro | Uma "Resposta do aluno" por pergunta, em primeira pessoa; originais de Q1 a Q3 em apêndice | Q25 revisada por Q27, Q26, Q28 |

---

## Apêndice: respostas originais de 27/09 (substituídas pelas consolidadas em 28/09)

Preservadas para mostrar como as decisões evoluíram. Não valem para o protocolo.

- **Q1, original:** "A pergunta a ser respondida é se há viés decisório entre juízes e juízas nos Tribunais Regionais Federais (6) e Tribunais de Justiça (27) acerca do assunto de saúde." Faltava justificar a troca de tom por viés decisório e listar as frentes; resolvido em Q19, Q20 e Q23.
- **Q2, original:** "Não consideramos mais o tom decisório, visto que essa extração provinha de um modelo de LLM. Agora vamos utilizar clusterização por tribunal, ano e magistrado." Faltava dizer por quê, de onde vinha o desenho, a que custo e como respondia à Q1; resolvido em Q20, Q21, Q23 e Q24.
- **Q3, original:** opção (A), "resultado e linguagem". Conflitava com a Q2; resolvido em Q6 e Q19.
