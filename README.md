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

## Game
A game can be formally defined as a kind of search problem with the following components:
- The initial state, which includes the board position and an indication of whose move it is.
- A set of operators, which define the legal moves that a player can make.
- A terminal test, which determines when the game is over. States where the game has ended are called terminal states.
- A utility function (also called a payoff function), which gives a numeric value for the outcome of a game. In chess, the outcome is a win, loss, or draw, which we can represent by the values +1, —1, or 0. Some games have a wider variety of possible outcomes; for example, the payoffs in backgammon range from +192 to —192.

## Minimax algorithm
In an opponent game, the minimax algorithm is designed to determine the optimal strategy for the AI player, and thus
to decide what the best first move is. The algorithm consists of five steps:
- Generate the whole game tree, all the way down to the terminal states.
- Apply the utility function to each terminal state to get its value.
- Use the utility of the terminal states to determine the utility of the nodes one level higher up in the search tree. 
- Continue backing up the values from the leaf nodes toward the root, one layer at a time.
- Eventually, the backed-up values reach the top of the tree; at that point, the AI player chooses the move that leads to the highest value. This is called the minimax decision, because it maximizes the utility under the assumption that the opponent will play perfectly to minimize it.

## Imperfect decisions
The minimax algorithm assumes that the program has time to search all the way to terminal states, which is usually not practical. Instead of going all the way to terminal states and using the utility function, we could *cut off the search* earlier and apply a *heuristic evaluation function* to the leaves of the tree.

## Heuristic evaluation functions
allow us to approximate the true utility of a state without doing a complete search.
How exactly do we measure quality?
- First, the evaluation function must agree with the utility function on terminal states. 
- Second, it must not take too long.  Hence, there is a trade-off between the accuracy of the evaluation function and its time cost. 
- Third, an evaluation function should accurately reflect the actual chances of winning.

## Cutting off search
The most straightforward approach to controlling the amount of search is to set a fixed depth limit, so that the cutoff test succeeds for all nodes at or below depth d. The depth is chosen so that the amount of time used will not exceed what the rules of the game allow. A slightly more robust approach is to apply *iterative deepening*. When time runs out, the program returns the move selected by the deepest completed search.

## Quiescent search
A more sophisticated cutoff test is needed. The evaluation function should only be applied to positions that are quiescent, that is, unlikely to exhibit wild swings in value in the near future. Nonquiescent positions can be expanded further until quiescent positions are reached. This extra search is called a *quiescence search*; sometimes it is restricted to consider only certain types of moves, such as capture moves, that will quickly resolve the uncertainties in the position.

## The horizon effect
The horizon problem is more difficult to eliminate. It arises when the program is facing a move by the opponent that causes serious damage and is ultimately unavoidable.

## Pruning
The process of eliminating a branch of the search tree from consideration without examining it is called pruning the search tree.

## Alpha-Beta pruning
When applied to a standard minimax tree, it returns the same move as minimax would, but prunes away branches that cannot possibly influence the final decision. The general principle is this. Consider a node n somewhere in the tree such that Player has a choice of moving to that node. If Player has a better choice ra either at the parent node of n, or at any choice point further up, then n will never be reached in actual play.
So once we have found out enough about n (by examining some of its descendants) to reach this conclusion, we can prune it.

The effectiveness of alpha-beta depends on the ordering in which the successors are examined.
If we assume that this can be done, then it turns out that alpha-beta only needs to examine O(b power d/2) nodes to pick the best move, instead of O(b power d) with minimax.

## The branching factor
