import math

# Constants for the players
HUMAN = -1
COMP = +1

# The board cells
board = [
    [0, 0, 0],
    [0, 0, 0],
    [0, 0, 0],
]

# This function prints the board
def print_board(board):
    chars = {0: ' ', HUMAN: 'X', COMP: 'O'}
    for row in board:
        for cell in row:
            print(f"{chars[cell]}", end="|")
        print()
        print("-----")

# This function checks for empty cells
def empty_cells(board):
    cells = []
    for x, row in enumerate(board):
        for y, cell in enumerate(row):
            if cell == 0:
                cells.append([x, y])
    return cells

# This function checks if the board is full
def is_full(board):
    return not any(0 in row for row in board)

# This function checks if a player has won
def evaluate(state):
    if wins(state, COMP):
        score = +1
    elif wins(state, HUMAN):
        score = -1
    else:
        score = 0
    return score

# This function checks if a move is valid
def valid_move(x, y):
    if [x, y] in empty_cells(board):
        return True
    else:
        return False

# This function makes a move
def set_move(x, y, player):
    if valid_move(x, y):
        board[x][y] = player
        return True
    return False

# This function checks for winning condition
def wins(state, player):
    win_state = [
        [state[0][0], state[0][1], state[0][2]],
        [state[1][0], state[1][1], state[1][2]],
        [state[2][0], state[2][1], state[2][2]],
        [state[0][0], state[1][0], state[2][0]],
        [state[0][1], state[1][1], state[2][1]],
        [state[0][2], state[1][2], state[2][2]],
        [state[0][0], state[1][1], state[2][2]],
        [state[2][0], state[1][1], state[0][2]],
    ]
    if [player, player, player] in win_state:
        return True
    else:
        return False

# The Minimax algorithm
def minimax(state, depth, player):
    if player == COMP:
        best = [-1, -1, -math.inf]
    else:
        best = [-1, -1, +math.inf]

    if depth == 0 or is_full(state):
        score = evaluate(state)
        return [-1, -1, score]

    for cell in empty_cells(state):
        x, y = cell
        state[x][y] = player
        score = minimax(state, depth - 1, -player)
        state[x][y] = 0
        score[0], score[1] = x, y

        if player == COMP:
            if score[2] > best[2]:
                best = score
        else:
            if score[2] < best[2]:
                best = score

    return best

# This function makes the best move for the AI
def ai_turn():
    depth = len(empty_cells(board))
    if depth == 0 or wins(board, HUMAN) or wins(board, COMP):
        return

    move = minimax(board, depth, COMP)
    set_move(move[0], move[1], COMP)

# This function starts the game
def play():
    while len(empty_cells(board)) > 0 and not wins(board, HUMAN) and not wins(board, COMP):
        print_board(board)
        x = int(input("Enter the row (0, 1, 2): "))
        y = int(input("Enter the column (0, 1, 2): "))
        if not valid_move(x, y):
            print("Invalid move. Try again.")
            continue
        set_move(x, y, HUMAN)
        ai_turn()

    print_board(board)

    if wins(board, HUMAN):
        print("HUMAN wins!")
    elif wins(board, COMP):
        print("COMP wins!")
    else:
        print("It's a draw!")

if __name__ == "__main__":
    play()
