# Definitions

## delta frequency
Use to detect patterns in graphs. I calculate differences between lows and highs (-9, +3, ...) a regular steps in the time serie.

We can calculate delta-x or delta-y (the derivative of the graph)

## Time Warping
A pattern can have slightly changes in the time serie.

## Euclidian distance
square root of the square of the differences between both time series, after filling the shortest time serie with 0.

## Dynamic time warping (DTW)
trying to align 2 signals in time to make them easily comparable.
We put the values of 1st serie on y and the values of 2nd serie on x.
We then try to match each value on each with the closest value on y.

We always try to minimize the error (keeping as close as possible to the diagonal)

Now we can calulate the euclidian distance.

## Sakoa Chiba bounds
some very different signals can be found with an unreasonable low Euclidian Distance with DTW. To mitigate this, we'll use Sakoa Chiba bounds.
Also, we can define different time warping allowed for each section of a signal.
http://wearables.cc.gatech.edu/paper_of_week/DTW_myths.pdf

## Hidden Markov Model (HMM)
AIMA: Chapter 15.1-15.3
Rabiner’s famous Tutorial on hidden Markov models and selected applications in speech recognition:http://www.cs.ubc.ca/~murphyk/Bayes/rabiner.pdf
Thad Starner's MS thesis: Visual Recognition of American Sign Language Using Hidden Markov Models: http://dspace.mit.edu/handle/1721.1/29089
The Hidden Markov Model Toolkit (HTK): http://htk.eng.cam.ac.uk/
http://www.ee.columbia.edu/ln/LabROSA/doc/HTKBook21/HTKBook.html


Useful tool to look at pattern recognition through time which have language-like structure.
We have states that represent a set of observed phenomena and transitions between these states. What we don't know (hidden) is which state leads to which transition.
First order MM consider the immediate state before a transition (and not a history of states).

HMM representation: We have states represented left to right with self transition loop (we don't change state) on each transition.
Now we have a box car distribution representing the possible values of each state (emission probabilities) + we represent the transition value to pass from one transition to the next one.
we then have to represent probability of escaping each state (ie 0.1 if we have 10 values in the time serie for a state). then the self transition will be 0.9 (the sum must be 1).

## Viterbi trellis
We create a Viterbi trellis to build the distribution of probabilities between states.
We then can calculate the Viterbi path.

## Baum-Welch re-estimation
Better estmation
