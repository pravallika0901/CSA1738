import math

def print_board(board):
    for row in board:
        print(" | ".join(row))
        print("-" * 5)

def is_moves_left(board):
    for row in board:
        if ' ' in row:
            return True
    return False

def evaluate(board):
    for row in board:
        if row[0] == arow[1] == row[2]:
            if row[0] == 'X':
                return 10
            elif row[0] == 'O':
                return -10
    for col in range(3):
        if board[0][col] == board[1][col] == board[2][col]:
            if board[0][col] == 'X':
                return 10
            elif board[0][col] == 'O':
                return -10
    if board[0][0] == board[1][1] == board[2][2]:
        if board[0][0] == 'X':
            return 10
        elif board[0][0] == 'O':
            return -10
    if board[0][2] == board[1][1] == board[2][0]:
        if board[0][2] == 'X':
            return 10
        elif board[0][2] == 'O':
            return -10
    return 0

def alphabeta(board, depth, alpha, beta, is_max):
    score = evaluate(board)
    
    if score == 10 or score == -10:
        return score
    
    if not is_moves_left(board):
        return 0
    
    if is_max:
        best = -math.inf
        for i in range(3):
            for j in range(3):
                if board[i][j] == ' ':
                    board[i][j] = 'X'
                    best = max(best, alphabeta(board, depth + 1, alpha, beta, False))
                    board[i][j] = ' '
                    alpha = max(alpha, best)
                    if beta <= alpha:
                        return best
        return best
    else:
        best = math.inf
        for i in range(3):
            for j in range(3):
                if board[i][j] == ' ':
                    board[i][j] = 'O'
                    best = min(best, alphabeta(board, depth + 1, alpha, beta, True))
                    board[i][j] = ' '
                    beta = min(beta, best)
                    if beta <= alpha:
                        return best
        return best

def find_best_move(board):
    best_val = -math.inf
    best_move = (-1, -1)
    
    for i in range(3):
        for j in range(3):
            if board[i][j] == ' ':
                board[i][j] = 'X'
                move_val = alphabeta(board, 0, -math.inf, math.inf, False)
                board[i][j] = ' '
                if move_val > best_val:
                    best_move = (i, j)
                    best_val = move_val
    return best_move

def tic_tac_toe():
    board = [[' ' for _ in range(3)] for _ in range(3)]
    current_player = 'X'

    while True:
        print_board(board)
        if current_player == 'X':
            move = find_best_move(board)
            board[move[0]][move[1]] = 'X'
        else:
            row = int(input("Enter the row (0, 1, 2): "))
            col = int(input("Enter the column (0, 1, 2): "))
            if board[row][col] != ' ':
                print("Cell already taken, try again.")
                continue
            board[row][col] = 'O'

        if evaluate(board) == 10:
            print_board(board)
            print("X wins!")
            break
        elif evaluate(board) == -10:
            print_board(board)
            print("O wins!")
            break
        elif not is_moves_left(board):
            print_board(board)
            print("It's a tie!")
            break

        current_player = 'O' if current_player == 'X' else 'X'

if _name_ == "_main_":
    tic_tac_toe()
