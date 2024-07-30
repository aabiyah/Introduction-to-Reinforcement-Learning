# Machine Learning Refresher

## Machine Learning (ML): A subset of artificial intelligence (AI) focused on building algorithms that learn from and make decisions based on data.
Objective: Simulate human intelligence and decision-making by teaching algorithms to learn from data.
## Supervised Learning:
Description: Training data includes labels that inform the algorithm about each sample.
Example: Training an algorithm to identify flowers with labeled images specifying the type of flower.
Outcome: The algorithm learns to predict labels for new, unseen data.
## Unsupervised Learning:
Description: Training data does not include labels.
Objective: The algorithm identifies patterns or distributions within the data.
Example: Analyzing a dataset of images without labels to find inherent patterns.
Benefit: Useful for large datasets where labels are not available.
## Reinforcement Learning (RL):
Description: The algorithm learns through trial and error by interacting with its environment.
Example: Training a dog with commands and rewards. The dog learns to follow commands to receive treats.
Process: The algorithm receives feedback and adjusts its actions to maximize rewards over time.

# Introduction to Reinforcement Learning

## Reinforcement Learning Key Concepts:
1. Agent: The entity being trained (e.g., a dog).
2. Environment: The "world" where the agent interacts (e.g., a park).
3. Actions: Movements or behaviors by the agent (e.g., running, sitting).
4. Rewards: Feedback given to the agent for good actions.

## Example Applications:
1. Playing Games:
Game: Breakout.
Agent: The paddle.
Environment: The game scene with bricks and boundaries.
Actions: Moving the paddle.
Rewards: Hitting bricks with the ball.

2. Traffic Signal Control:
Agent: Traffic light control system.
Environment: Road network.
Actions: Changing traffic light signals (red-yellow-green).
Rewards: Based on traffic flow and throughput.

3. Self-Driving Cars:
Agent: The car (self-driving software).
Environment: Roads and surroundings.
Actions: Steering angle and speed adjustments.
Rewards: Staying on the road, avoiding collisions, and reaching the destination efficiently.

# Reinforcement Learning with a Mechanical Computer
Hexapawn is a simplified version of chess played on a 3x3 grid with pawns. The mechanical computer used for this example is constructed from 24 matchboxes, each representing a different game state with beads inside representing possible moves from each state.

### How It Works:
Matchboxes and Beads: Each matchbox corresponds to a specific game state, and inside each matchbox are beads, each representing a different move that can be made from that state.
Making a Move: When it's the computer's turn to move, it shakes the matchbox corresponding to the current game state and randomly picks a bead. The color of the bead determines the move.
Learning through Punishment: If the computer makes a poor move that results in a loss, the bead representing that move is removed from the matchbox. This means that the computer cannot make that same move in the future.
Optimization through Feedback: Over many games, the computer learns which moves lead to winning by reinforcing successful moves and eliminating unsuccessful ones. This feedback loop allows the computer to optimize its strategy.

### Result:
Through repeated play and feedback, the mechanical computer improves its game. It learns to avoid poor moves and favor those that increase its chances of winning. This process mirrors how reinforcement learning algorithms work in more complex AI systems. 
> This way of playing the game punishes the computer for losing by taking away the last bead that was thrown out in the game the computer lost. Another way of doing this is by rewarding the computer for every win by adding another bead of the same color that was last thrown out of the matchbox of the winning game, thus increasing the probability of it being thrown out again in the next game.

To learn more about Hexapawn, you can find the original article written by AI researcher Martin Gardner here: “How to build a game-learning machine and then teach it to play and win” by Martin Gardner, Scientific American: http://cs.williams.edu/~freund/cs136-073/GardnerHexapawn.pdf .
