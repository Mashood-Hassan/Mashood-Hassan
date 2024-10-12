def print_board(board):
    print(f"{board[0]} | {board[1]} | {board[2]}")
    print("--|---|--")
    print(f"{board[3]} | {board[4]} | {board[5]}")
    print("--|---|--")
    print(f"{board[6]} | {board[7]} | {board[8]}")


def check_winner(board, player):
    # Winning combinations for the Tic Tac Toe board
    win_conditions = [(0, 1, 2), (3, 4, 5), (6, 7, 8),  # Horizontal
                      (0, 3, 6), (1, 4, 7), (2, 5, 8),  # Vertical
                      (0, 4, 8), (2, 4, 6)]  # Diagonal

    for condition in win_conditions:
        if board[condition[0]] == board[condition[1]] == board[condition[2]] == player:
            return True
    return False


def is_draw(board):
    return all(cell != ' ' for cell in board)


def tic_tac_toe():
    board = [' '] * 9
    current_player = 'X'
    print("Welcome to Tic Tac Toe")

    while True:
        print_board(board)
        try:
            move = int(input(f"Player {current_player}, enter your move (1-9): ")) - 1
        except ValueError:
            print("Invalid input! Please enter a number between 1 and 9.")
            continue

        if move < 0 or move > 8 or board[move] != ' ':
            print("Invalid move! The cell is either occupied or out of range. Try again.")
            continue

        board[move] = current_player

        if check_winner(board, current_player):
            print_board(board)
            print(f"Congratulations! Player {current_player} wins!")
            break

        if is_draw(board):
            print_board(board)
            print("It's a draw!")
            break

        # Switch players
        current_player = 'O' if current_player == 'X' else 'X'


if _name_ == "_main_":
    tic_tac_toe()
- 👋 Hi, I’m @Mashood-Hassan
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Mashood-Hassan/Mashood-Hassan is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
