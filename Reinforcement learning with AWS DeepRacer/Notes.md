# AWS DeepRacer and Reinforcement Learning

### Overview
AWS DeepRacer is a 1/18th scale autonomous racing car designed to help developers learn reinforcement learning (RL) through a hands-on approach. The goal is for the car to drive around a track as fast as possible using RL techniques.

### Key Components:
1. Agent: The AWS DeepRacer car, or more specifically, the software running on the car.
2. Environment: The racing track on which the DeepRacer car drives.

### How It Works:
1. State:
The agent understands its environment through the state. For AWS DeepRacer, the state is represented by the images captured by the car's camera.
2. Actions:
Based on the state, the agent can take several actions. For DeepRacer, these actions include accelerating, braking, turning left, turning right, or going straight.
3. Rewards:
After performing an action, the agent receives feedback in the form of rewards. Rewards indicate how well the action helped achieve the goal of completing the lap quickly.
Positive rewards are given for actions that help the car stay on the track and move quickly, while negative rewards (or penalties) are given for actions that slow down the car or cause it to go off track.
4. Episode:
An episode consists of the agent observing its state, taking an action, and receiving a reward. This cycle repeats, with the agent continually learning from the rewards it receives to improve its performance.
Learning Process:

The agent learns to optimize its actions over multiple episodes by maximizing the cumulative reward. This involves exploring different actions, learning from the rewards, and gradually improving its strategy to complete laps faster.
By iterating through this process, the AWS DeepRacer car continuously improves its ability to navigate the track efficiently, providing a practical example of how reinforcement learning can be applied to real-world problems.

Video explanation: https://www.youtube.com/watch?v=lPo9n_LzYAI&t=188s

# Training an AWS DeepRacer Model

### Overview
Creating a model in AWS DeepRacer Student involves six key steps. This guide will walk you through each step, providing tips and best practices to ensure successful model training.

### Steps
1. Name Your Model
Importance: Naming your model clearly and descriptively helps in organizing and tracking your models.
Suggestion: Use the track or race name along with a version number (e.g., SummitSpeedway-V1). Increment the version number with each clone or iteration.

3. Choose Track
Selection: Choose the track where you will train your model.
Tip: For competitive scenarios, select the track used in the Student League competition. Note that more challenging tracks may require more training time and a more complex reward function.

3. Choose Algorithm Type
Options: You can select from different reinforcement learning training algorithms.
Recommendation: For beginners, choose either Proximal Policy Optimization (PPO) or Soft Actor-Critic (SAC). A deeper understanding of these algorithms will be covered in subsequent lessons.

4. Customize Reward Function
Function: The reward function determines how the agent is rewarded for its actions.
Starting Point: Select the “Follow the centerline” reward function to start. This function rewards the agent for staying close to the centerline of the track. You can build upon this later.

5. Choose Duration
Training Time: Configure the training duration.
Initial Suggestion: Start with 60 minutes of training. Provide a description for your model (e.g., a summary of the chosen algorithm and reward function).
Participation: Tick the box to submit to the leaderboard for the Student League. This allows you to participate and see how your model performs.

6. Train Your Model
Simulation: Once training starts, a simulated video stream will show the training process.
Process: The model may go off-track or perform unexpected actions initially. This is normal as the agent explores the environment (exploration) and learns to maximize rewards (exploitation).

7. Post-Training
Model List: After training, you can view your model in the “Models” section of the AWS DeepRacer Student console.
Cloning: You can clone your model for further training or to modify the reward function. Future chapters will cover cloning and improving existing models.

By following these steps, you'll set a solid foundation for training and improving your AWS DeepRacer models, enabling you to participate effectively in competitions and refine your machine learning skills.

Video explanation: https://www.youtube.com/watch?time_continue=54&v=pnc0z76bKzA
