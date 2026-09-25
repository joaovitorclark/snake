# Contar e exibir a pontuação

## Objetivo
Somar 1 ponto a cada comida consumida e mostrar ao jogador a pontuação da partida atual, zerando ao reiniciar.

## Regras
- A pontuação é um inteiro que começa em 0 no início de cada partida.
- Cada evento "comida consumida" soma exatamente 1 ponto.
- O evento "comida consumida" é o contrato de entrada desta spec. Quem o emite é uma futura spec de comida; esta spec não inclui comida nem crescimento da cobra.
- Reiniciar a partida zera a pontuação.
- Não há recorde nem persistência entre partidas.

## Exibição
- O placar mostra o valor atual da pontuação e se atualiza no mesmo tick em que a comida é consumida.
- No fim de jogo, o placar continua mostrando a pontuação final até o jogador reiniciar.
- A posição do placar na tela não é definida aqui: depende da decisão do time de design (q-1).

## Critérios de aceite
- Uma partida nova mostra 0.
- Três eventos "comida consumida" fazem o placar mostrar 3.
- Reiniciar depois de pontuar volta a mostrar 0.
- No fim de jogo, o placar mantém o valor final visível.

## Fora de escopo
Comida e crescimento da cobra, recorde e persistência, pontuação variável (por velocidade ou nível), posição do placar na tela (q-1), tela de fim de jogo.
