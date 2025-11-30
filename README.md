# 🧠 Minimax AI player

![Python](https://img.shields.io/badge/Python-3.11-blue)
![CS50 AI](https://img.shields.io/badge/CS50-AI_Project-orange)
![Logic](https://img.shields.io/badge/Minimax%20AI-✓-brightgreen)
![Status](https://img.shields.io/badge/Status-Complete-success)

---

## 📁 Project Structure

```
tictactoe/
│
├── tictactoe.py        # core game logic + minimax ai
├── runner.py           # pygame GUI for interactive play
├── test.py             # debugging tool used in development 
├── requirements.txt    # dependencies
├── OpenSans-Regular.ttf
└── __pycache__/        # python cache
```

---

## 📝 Overview

This is a full **Tic-Tac-Toe game with an unbeatable AI** based on the **Minimax algorithm**.

The project includes:

- A clean implementation of the game rules  
- A fully optimal AI that never loses  
- A `pygame` interface allowing the user to play as **X** or **O**  
- Modular code that separates *game logic* from *UI logic*  
- A fully deterministic game tree search  

---

## 🧩 How the AI Works

The AI uses the classic **Minimax algorithm** to evaluate all possible future game states and choose the optimal move.

### 🔍 high-level idea

```
current board
   |
   |-- possible move 1 --> evaluate with min_value()
   |
   |-- possible move 2 --> evaluate with min_value()
   |
   |-- possible move 3 --> evaluate with min_value()
        ...
pick the move with the best score (max for X, min for O)
```

Minimax uses two alternating evaluation functions:

- `max_value(board)` — chooses the **best possible** outcome for X  
- `min_value(board)` — chooses the **worst-case** outcome for O  

Both stop when:

```
terminal state reached (win / lose / tie)
        |
        v
return utility(board)  → +1 (X wins), -1 (O wins), 0 (draw)
```

### 🔢 scoring example

Consider the board:

```
X | X | .
O | . | .
. | . | O
```

Minimax evaluates all possible branches:

```
X to move:
    place X at (0,2) → X wins → score = +1
    place X at (1,1) → opponent can force a draw → score = 0
    place X at (1,2) → opponent can force a draw → score = 0
    ...
best move = the one yielding the highest score (+1)
```

### 🎯 result:  
The AI **always plays perfectly** — it will win when possible and force a draw otherwise.

---

## ▶️ Running the Project

### 1. install dependencies

```
pip install -r requirements.txt
```

### 2. run the pygame interface

```
python runner.py
```

You will be prompted to choose:

```
[ play as x ]   or   [ play as o ]
```

---

## 📘 Concepts Covered

This project demonstrates:

- **Minimax algorithm**  
- **Recursive search** and tree evaluation  
- **Game state immutability** (pure functional state transitions)  
- **Deterministic AI decision-making**  
- **Rule-based validation** of moves  
- **Pygame rendering & event handling**  
- **Separation of logic and interface**  
- **Error handling & board state copying**  

---

## 📄 License

This project is open-source and available under the MIT License.
