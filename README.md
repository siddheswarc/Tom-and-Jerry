# Tom-and-Jerry-in-Reinforcement-Learning

This project combines Reinforcement Learning and Deep Learning. The task is to teach the agent to navigate in the grid-world environment.
<br>
We have modeled Tom and Jerry cartoon, where Tom, a cat, is chasing Jerry, a mouse. In our modeled game the task for Tom (an agent) is to find the shortest path to Jerry (a goal), given that the initial positions of Tom and Jerry are changing on every reset of the game.

To solve the problem, we  apply Deep Reinforcement Learning algorithm - DQN (Deep Q-Network), that was one of the first breakthrough successes in applying Deep Learning to Reinforcement Learning.

![Neural Network Structure](http://drive.google.com/uc?export=view&id=14Hpr_DC32QaJ3mDh-15PJbvEODDTdqtJ)


## Neural Network structure for our task

Our DQN takes a stack of four-tuple as an input. It is passed through two hidden networks, and output a vector of Q-values for each action possible in the given state.

![Neural Network Structure](http://drive.google.com/uc?export=view&id=1eFRQhnhwS8hIliBBMVnAiChOtitoU3_n)

## Algorithm

At the beginning of each episode, we reset the environment, and pass it's return value, the initial state, to the agent's act method. This returns an action, which is then passed to the environment's step method. This returns the next state, the reward, and the boolean indicating if the episode is over. We then save the observation tuple to the agent's memory via the agent's observe method, then run a round of training by calling the agent's replay method. We can then render the environment. If an episode is over, we break from this loop, otherwise we continue with the next state being passed to the agent as the (now) current state.

| Epsilon Graph | Reward Graph |
|---|---|
| ![Epsilon graph](http://drive.google.com/uc?export=view&id=1zFpAUuWMhaS3_XqVpanXFAn_IrBQ9H3s)  | ![Reward graph](http://drive.google.com/uc?export=view&id=1hbwvpDKpTmJJ7ks1JlxcHRWWXn0Ba8pU)  |
