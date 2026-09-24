# Personalizar cor e formato da cabeça

## Objetivo
O jogador escolhe a cor e o formato da cabeça da cobra na tela inicial, antes de começar a partida.

## Regras
- A escolha acontece na tela inicial; fica fixa durante a partida.
- Cor: seleção em uma paleta fixa de cerca de 6-8 cores pré-definidas, todas com contraste suficiente contra o fundo e a comida.
- Formato: quadrado, círculo ou triângulo. O triângulo aponta na direção atual do movimento; quadrado e círculo não dependem da direção.
- A cabeça é desenhada dentro da célula da grade, sem alterar a lógica de movimento nem de colisão (a hitbox continua sendo a célula).
- O corpo da cobra não é afetado por esta spec.

## Persistência
- A última escolha é salva em `localStorage` e restaurada ao abrir o jogo.
- Na primeira vez (ou se o valor salvo for inválido/ausente), usa-se um padrão definido (ex.: primeira cor da paleta, quadrado).
- Falha ao ler/gravar `localStorage` não pode quebrar o jogo; cai no padrão.

## Critérios de aceite
- A tela inicial mostra a paleta e os três formatos, com a seleção atual destacada e uma pré-visualização.
- Ao iniciar a partida, a cabeça usa a cor e o formato escolhidos.
- O triângulo gira conforme a direção da cobra a cada virada.
- Recarregar a página mantém a última escolha.
- Valor salvo corrompido resulta no padrão, sem erro.

## Fora de escopo
Cor do corpo, seletor livre de cor, rostos/emojis/decorações, troca durante a partida, menu de configurações separado.
