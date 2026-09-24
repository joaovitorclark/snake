# Ata

Append-only record of the decisions that shaped this feature.

## 2026-09-24 — elaboration

**Question.** Quando o jogador escolhe a cor e o formato da cabeça?
**Options.** Tela inicial; durante a partida via atalhos; menu de configurações separado.
**Decision.** Na tela inicial, antes de começar a partida; a escolha fica fixa durante a partida.
**Why.** Simples de especificar e testar, sem interferir no loop do jogo nem na entrada de direção.
**Decided by.** agent

## 2026-09-24 — elaboration

**Question.** Como o jogador escolhe a cor da cabeça?
**Options.** Paleta fixa; seletor livre (color picker).
**Decision.** Paleta fixa de cores pré-definidas (cerca de 6-8), escolhida por seleção.
**Why.** Garante contraste com o fundo e a comida; evita cor invisível que um seletor livre permitiria.
**Decided by.** agent

## 2026-09-24 — elaboration

**Question.** Quais formatos de cabeça estão disponíveis?
**Options.** Quadrado/círculo/triângulo; só quadrado e círculo; formas com rostos/emojis.
**Decision.** Três formas geométricas: quadrado, círculo e triângulo; o triângulo aponta na direção do movimento.
**Why.** Escopo pequeno e sem arte extra, mas com variedade real; rostos/emojis ficam para depois.
**Decided by.** agent
**Produced.** jogo/cabeca/personalizar-cabeca

## 2026-09-24 — elaboration

**Question.** A escolha de cor e formato deve ser lembrada entre sessões?
**Options.** Persistir em localStorage; não persistir.
**Decision.** Sim: salva em localStorage e restaurada ao reabrir, com padrão na primeira vez ou se o valor for inválido.
**Why.** Evita o jogador reescolher a cada partida; custo baixo e fácil de testar.
**Decided by.** agent
**Produced.** jogo/cabeca/personalizar-cabeca
