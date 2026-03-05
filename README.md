# TicTacToe
Tic Tac Toe game

**(Descrição em Português)**

Existem dois arquivos principais neste projeto: runner.py e tictactoe.py. O tictactoe.py contém toda a lógica para jogar o jogo e para fazer os melhores movimentos. O runner.py contém todo o código para executar a interface gráfica do jogo.

No tictactoe.py há três variáveis: X, O e EMPTY, para representar os possíveis movimentos no tabuleiro.

A função initial_state retorna o estado inicial do tabuleiro. Para este projeto, representamos o tabuleiro como uma lista de três listas (representando as três linhas do tabuleiro), onde cada lista contém três valores que são X, O ou EMPTY.

A função player recebe um estado do tabuleiro como entrada e retorna de quem é a vez de jogar (ou X ou O). No estado inicial do jogo, X faz o primeiro movimento. Subsequentemente, o jogador alterna a cada movimento adicional.

A função actions retorna um conjunto de todas as ações possíveis que podem ser realizadas em um determinado tabuleiro. Cada ação é representada como uma tupla (i, j), onde i corresponde à linha do movimento (0, 1 ou 2) e j corresponde a qual célula na linha corresponde ao movimento (também 0, 1 ou 2). Movimentos possíveis são quaisquer células no tabuleiro que ainda não tenham um X ou um O nelas. 

A função result recebe um tabuleiro e uma ação como entrada, e retorna um novo estado do tabuleiro, sem modificar o tabuleiro original (usando deepcopy). O estado de tabuleiro retornado é o tabuleiro que resultaria de pegar o tabuleiro de entrada original e permitir que o jogador que está na vez faça seu movimento na célula indicada pela ação de entrada. 

A função winner aceita um tabuleiro como entrada e retorna o vencedor do tabuleiro, se houver. Se o jogador X ganhou o jogo, a função retorna X. Se o jogador O ganhou o jogo, a função retorna O. Um jogador pode ganhar o jogo com três de seus movimentos em linha horizontal, vertical ou diagonalmente. Se não houver vencedor no jogo (ou porque o jogo está em andamento ou porque terminou em empate), a função retorna None.

A função terminal aceita um tabuleiro como entrada e retorna um valor booleano indicando se o jogo acabou. Se o jogo acabou, seja porque alguém venceu o jogo ou porque todas as células foram preenchidas sem que ninguém tenha vencido, a função retorna True. Caso contrário, a função retorna False se o jogo ainda estiver em andamento. 

A função utility aceita um tabuleiro terminal como entrada e retorna a utilidade do tabuleiro. Se X venceu o jogo, a utilidade é 1. Se O venceu o jogo, a utilidade é -1. Se o jogo terminou empatado, a utilidade é 0. A função utility será chamada apenas em um tabuleiro se terminal(board) for True. 

A função minimax recebe um tabuleiro como entrada e retorna o melhor movimento para o jogador que deve jogar naquele tabuleiro. O movimento retornado é a melhor ação (i, j) que é uma das ações permitidas no tabuleiro. Se múltiplos movimentos forem igualmente ótimos, qualquer um desses movimentos é aceitável. Se o tabuleiro for terminal, a função minimax retorna None. 

**Para jogar o jogo, você precisa executar pip3 install -r requirements.txt no seu terminal dentro do diretório onde os arquivos estão salvos para instalar o pacote Python necessário (pygame) para este projeto. E então execute runner.py para jogar contra a IA. E, como o Jogo da Velha sempre termina em empate com ambos os lados jogando bem, você nunca vai conseguir vencer a IA (embora, se você não jogar bem, ela pode vencer você!)**


**(English Description)**

There are two main files in this project: runner.py and tictactoe.py. tictactoe.py contains all of the logic for playing the game, and for making optimal moves. runner.py contains all of the code to run the graphical interface for the game.

In tictactoe.py there are three variables: X, O, and EMPTY, to represent possible moves of the board.

The function initial_state returns the starting state of the board. For this problem, we represent the board as a list of three lists (representing the three rows of the board), where each internal list contains three values that are either X, O, or EMPTY. 

The player function takes a board state as input, and return which player’s turn it is (either X or O).
In the initial game state, X gets the first move. Subsequently, the player alternates with each additional move.

The actions function returns a set of all of the possible actions that can be taken on a given board.
Each action is represented as a tuple (i, j) where i corresponds to the row of the move (0, 1, or 2) and j corresponds to which cell in the row corresponds to the move (also 0, 1, or 2).
Possible moves are any cells on the board that do not already have an X or an O in them.

The result function takes a board and an action as input, and returns a new board state, without modifying the original board(using deepcopy).

The returned board state is the board that would result from taking the original input board, and letting the player whose turn it is make their move at the cell indicated by the input action.

The winner function accepts a board as input, and return the winner of the board if there is one.
If the X player has won the game, the function returns X. If the O player has won the game, the function returns O.
One can win the game with three of their moves in a row horizontally, vertically, or diagonally.
If there is no winner of the game (either because the game is in progress, or because it ended in a tie), the function return None.

The terminal function accepts a board as input, and return a boolean value indicating whether the game is over.
If the game is over, either because someone has won the game or because all cells have been filled without anyone winning, the function returns True.
Otherwise, the function should return False if the game is still in progress.

The utility function accepts a terminal board as input and output the utility of the board.
If X has won the game, the utility is 1. If O has won the game, the utility is -1. If the game has ended in a tie, the utility is 0.
Utility will only be called on a board if terminal(board) is True.

The minimax function takes a board as input, and return the optimal move for the player to move on that board.
The move returned is the optimal action (i, j) that is one of the allowable actions on the board. If multiple moves are equally optimal, any of those moves is acceptable.
If the board is a terminal board, the minimax function returns None.

**To play the game, you have to run pip3 install -r requirements.txt in your terminal inside the directory where the files are saved to install the required Python package (pygame) for this project. And then run runner.py to play against the AI. And, since Tic-Tac-Toe is a tie given optimal play by both sides, you should never be able to beat the AI (though if you don’t play optimally as well, it may beat you!)**
