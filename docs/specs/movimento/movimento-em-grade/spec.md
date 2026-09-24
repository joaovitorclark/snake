# Movimento em grade com tick fixo

## Objetivo
A cobra se move numa grade, avançando uma célula por tick, em velocidade constante.

## Regras
- O tabuleiro é uma grade de células; a cobra ocupa uma sequência de células contíguas.
- A cada tick a cabeça avança uma célula na direção atual e a cauda libera a última célula (sem crescimento nesta spec).
- O intervalo do tick é constante durante toda a partida.
- Bater na borda do tabuleiro termina o jogo (sem wrap-around).
- Bater no próprio corpo termina o jogo.

## Entrada de direção
- Setas (e opcionalmente WASD) definem a próxima direção.
- Entradas ficam numa fila de até 2 viradas; uma é consumida por tick.
- Virada de 180° (oposta à direção efetiva atual, considerando a fila) é ignorada.
- Entradas além do limite da fila são descartadas.

## Critérios de aceite
- Sem entrada, a cobra segue reta a 1 célula por tick.
- Duas viradas rápidas (ex.: cima e depois esquerda) dentro de um tick são aplicadas em ticks consecutivos.
- Pressionar a direção oposta à atual não altera o movimento nem mata a cobra.
- Sair do tabuleiro ou colidir com o corpo emite o estado "fim de jogo".

## Fora de escopo
Crescimento, comida, pontuação, aceleração, wrap-around, tela de fim de jogo.
