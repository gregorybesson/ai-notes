# Problem decomposition

# Problem nearly decomposable
The planner can work on subgoals independently, but might need to do some additional work to combine the resulting subplans.

# Representation of states
We decompose the world into logical conditions and represent a state as conjunction of positive literals.
We will also use first-order literals; for example, At(Plane1, Melbourne) ∧ At(Plane2, Sydney) might represent a state in the package delivery problem. Literals in first-order state descriptions
must be ground and function-free. Literals such as At(x, y) or At(Father(Fred), Sydney) are not allowed.

The closed-world assumption is used, meaning that any conditions that are not mentioned in a state are assumed false.

# Representation of goals
A goal is a partially specified state, represented as a conjunction of positive ground literals, such as Rich ∧ Famous or At(P2, Tahiti).

# Representation of actions
An action is specified in terms of the preconditions that must hold before it can be executed and the effects that ensue when it is executed. For example, an action for flying a plane from one location to another is:
```
Action(Fly(p, from,to),
PRECOND:At(p, from) ∧ Plane(p) ∧ Airport(from) ∧ Airport(to)
EFFECT:¬At(p, from) ∧ At(p,to))
```

This is more properly called an action schema, meaning that it represents a number of different actions that can be derived by instantiating the variables p, from, and to to different constants. In general, an action schema consists of three parts:
- The action name and parameter list—for example, Fly(p, from, to)—serves to identify the action.
- The precondition is a conjunction of function-free positive literals stating what must be true in a state before the action can be executed. Any variables in the precondition must also appear in the action’s parameter list.
- The effect is a conjunction of function-free literals describing how the state changes when the action is executed. A positive literal P in the effect is asserted to be true in the state resulting from the action, whereas a negative literal ¬P is asserted to be false.
Variables in the effect must also appear in the action’s parameter list.

# STRIPS
In artificial intelligence, STRIPS (Stanford Research Institute Problem Solver) is an automated planner developed by Richard Fikes and Nils Nilsson in 1971 at SRI International.
The same name was later used to refer to the formal language of the inputs to this planner. 
This language is the base for most of the languages for expressing automated planning problem instances in use today; such languages are commonly known as action languages.






