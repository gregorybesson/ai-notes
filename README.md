Artificial Intelligence - A Modern Approach (AIMA): Chapter 5.1-5.2

Artificial Intelligence - A Modern Approach (AIMA): Chapter 5.3-5.4

http://www.cc.gatech.edu/~thad/6601-gradAI-fall2015/Korf_Multi-player-Alpha-beta-Pruning.pdf

# Definitions
## Heuristic function
Currently, heuristic is most often used as an adjective, referring to any technique
that improves the average-case performance on a problem-solving task, but does
not necessarily improve the worst-case performance. In the specific area of search
algorithms, it refers to a function that provides an estimate of solution cost.

## contingency problem

## Pruning 
allows us to ignore portions of the search tree that make no difference to the final choice

## heuristic evaluation functions
allow us to approximate the true utility of a state without doing a complete search

## Game
A game can be formally defined as a kind of search problem with the following components:
- The initial state, which includes the board position and an indication of whose move it is.
- A set of operators, which define the legal moves that a player can make.
- A terminal test, which determines when the game is over. States where the game has ended are called terminal states.
- A utility function (also called a payoff function), which gives a numeric value for the outcome of a game. In chess, the outcome is a win, loss, or draw, which we can represent by the values +1, —1, or 0. Some games have a wider variety of possible outcomes; for example, the payoffs in backgammon range from +192 to —192.

# Building a game tree

# minimax function

# The branching factor

# Depth-Limited search

# Evaluation function

# Quiescent search

# Iterative deepening

# Horizon effect

# Alpha-Beta pruning

# Expectimax
