File: README.txt
Group Members: Niranjan Balachandar, Jay Lee, & Karan Singhal
-------------------------------------------------------------------------------
Key functions across files:
humanPlay: implements a human game run
aiPlay: implements an AI game run
initialize: initializes the game grid, called at the beginning of every game
isValidCoord: returns whether a coordinate is within the correct range
isValidMove: returns whether a pair of coordinates is a valid action
validMoveExists: returns whether the game grid has any valid move
cascade: takes game grid and deletes the appropriate candies, cascades in new
         candies, and deletes further combos if necessary. Updates score if
         necessary.
cascadeCoords: finds max number of candies that can be deleted from the game
               grid at a given moment
updateQ: updates Q value for the observed SARS' sample
makeSwitch: switches two candies
getFeatureVec: feature extractor
getQopt: In function approximation calculates Qopt for a state, action based on
         weights or parameters
updateWeights: In function approximation updates weights for observed SARS' 

Note: Before each iteration (game), random and numpy.random are seeded to the
iteration number to get same start game grids across algorithms.

The code directory contains the following files:
-------------------------------------------------------------------------------
1. baseline-or-human.py

To run, simply enter the command "python baseline-or-human.py" without the
quotes.
Implements the baseline algorithm and human playing console. To run baseline
algorithm set the global variable HUMAN to False. To play as human set HUMAN
to True. Runs the game 1000 times and calculates average score across runs. 

-------------------------------------------------------------------------------
2. greedy.py

To run, simply enter the command "python greedy.py" without the quotes.
Implements the greedy algorithm. Runs the game 1000 times and calculates 
average score across runs. 

-------------------------------------------------------------------------------
3. Q-regular.py

To run, simply enter the command "python Q-regular.py" without the quotes.
Implements the regular Q-learning algorithm (without function approximation). 
Runs the game 66 times and calculates average score across runs.

-------------------------------------------------------------------------------
4. Q-func-lin-train.py

To run, simply enter the command "python Q-func-lin-train.py" without the
quotes.
Implements training for Q-learning with linear function approximation to obtain
converged weights for testing. Uses epsilon-greedy exploration policy.

-------------------------------------------------------------------------------
5. Q-func-lin-test.py

To run, simply enter the command "python Q-func-lin-test.py" without the 
quotes.
Implements testing for Q-learning with linear function approximation using 
converged weights from running Q-func-lin-train.py. Runs the game 66 times and 
calculates average score across runs.

-------------------------------------------------------------------------------
6. Q-func-neural-train.py

To run, simply enter the command "python Q-func-neural-train.py" without the
quotes.
Implements training for Q-learning with neural network function approximation 
to obtain converged parameters for testing. Uses epsilon-greedy exploration 
policy. Uses MLPRegressor from sklearn.neural_network to train neural network.

-------------------------------------------------------------------------------
7. Q-func-neural-test.py

To run, simply enter the command "python Q-func-neural-test.py" without the 
quotes.
Implements testing for Q-learning with neural network function approximation 
using converged parameters from running Q-func-neural-train.py. Uses 
MLPRegressor from sklearn.neural_network to obtain Q_opt for a state, action
pair. Runs the game 66 times and calculates average score across runs.

-------------------------------------------------------------------------------

The data directory contains the following files:

*Human games were completed on the console, so have not been written to a file.

1. Q-func-lin.weights
Converged weights for linear function approximation (from running 
Q-func-lin-train.py until convergence).

2. Q-func-neural.params
Converged parameters for neural network function approximation (from running 
Q-func-neural-train.py until convergence).

3. baseline.out
Game results from running baseline.py for 1,000 seeded games.

4. greedy.out
Game results from running greedy.py for 1,000 seeded games.

5. Q-regular.out
Game results from running Q-regular.py for 66 seeded games.

6. Q-func-lin.out
Game results from running Q-func-lin-test.py for 66 seeded games.

7. Q-func-neural.out
Game results from running Q-func-neural-test.py for 66 seeded games.

8. data.png
Graph of results
