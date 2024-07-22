def print_board(board):
    print("---------")
    for row in board:
        print("|".join(row))
        print("---------")

def check_winner(board, player):
    win_conditions = [
        [board[0][0], board[0][1], board[0][2]], # Row 1
        [board[1][0], board[1][1], board[1][2]], # Row 2
        [board[2][0], board[2][1], board[2][2]], # Row 3
        [board[0][0], board[1][0], board[2][0]], # Column 1
        [board[0][1], board[1][1], board[2][1]], # Column 2
        [board[0][2], board[1][2], board[2][2]], # Column 3
        [board[0][0], board[1][1], board[2][2]], # Diagonal
        [board[2][0], board[1][1], board[0][2]], # Diagonal
    ]
    return [player, player, player] in win_conditions

def is_board_full(board):
    for row in board:
        if ' ' in row:
            return False
    return True

def get_move(player):
    while True:
        try:
            row = int(input(f"Player {player}, enter the row (0, 1, 2): "))
            col = int(input(f"Player {player}, enter the column (0, 1, 2): "))
            if row in [0, 1, 2] and col in [0, 1, 2]:
                return row, col
            else:
                print("Invalid input. Please enter numbers between 0 and 2.")
        except ValueError:
            print("Invalid input. Please enter numbers.")

def play_game():
    board = [[' ' for _ in range(3)] for _ in range(3)]
    current_player = 'X'

    while True:
        print_board(board)
        row, col = get_move(current_player)

        if board[row][col] == ' ':
            board[row][col] = current_player

            if check_winner(board, current_player):
                print_board(board)
                print(f"Player {current_player} wins!")
                break

            if is_board_full(board):
                print_board(board)
                print("The game is a draw!")
                break

            current_player = 'O' if current_player == 'X' else 'X'
        else:
            print("The cell is already taken. Choose a different move.")

if __name__ == "__main__":
    play_game()
