# Salvar e continuar progresso

## Objetivo
O progresso da campanha é salvo automaticamente ao vencer cada fase, e o jogador pode continuar de onde parou ao reabrir o jogo.

## Dependência
Depende da feature `campanha` (fases, pontuação acumulada e tela de campanha concluída).

## O que é salvo
- Número da próxima fase liberada (1 a 5).
- Pontuação acumulada das fases já vencidas.
- Versão do formato do save, para permitir mudanças futuras.

## Quando salva
- Automaticamente, no momento em que o jogador vence uma fase.
- Não há save durante a fase. Se o jogador fechar o jogo no meio de uma fase, ao continuar ele retoma do início dessa fase.
- Ao vencer a fase 5, o save é marcado como campanha concluída.

## Onde salva
- `localStorage`, em uma única chave, com um único slot. Sem contas nem sincronização entre dispositivos.

## Tela inicial
- Se existe um save válido, aparecem "Continuar" e "Nova campanha".
- "Continuar" abre a próxima fase liberada, com a pontuação acumulada restaurada.
- "Nova campanha" pede confirmação, apaga o save e começa na fase 1.
- Se não existe save válido, aparece apenas o botão de iniciar a campanha, como hoje.
- Com a campanha concluída, "Continuar" não aparece e o jogador pode iniciar uma nova campanha.

## Erros
- Save ausente, corrompido, com formato desconhecido ou com valores fora do intervalo (fase fora de 1 a 5, pontuação negativa) é ignorado, e o jogo começa do zero.
- Falha ao ler ou gravar `localStorage` não pode quebrar o jogo. Se a gravação falhar, a partida segue normalmente, sem save.

## Critérios de aceite
- Vencer a fase 2 e recarregar a página mostra "Continuar", que abre a fase 3 com a pontuação acumulada.
- Fechar o jogo no meio da fase 3 e continuar retoma o início da fase 3.
- "Nova campanha" apaga o save só depois da confirmação.
- Um valor salvo corrompido resulta em início do zero, sem erro.
- Com `localStorage` indisponível, o jogo funciona normalmente, sem "Continuar".

## Fora de escopo
Salvar no meio da fase, vários slots, exportar ou importar save, sincronização na nuvem, salvar a personalização da cabeça (já coberta pela feature `cabeca`).
