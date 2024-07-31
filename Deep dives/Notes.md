# Training Algorithms

## Overview

Reinforcement learning involves training algorithms to make decisions based on feedback from the environment. AWS DeepRacer offers two main reinforcement learning algorithms: Proximal Policy Optimization (PPO) and Soft Actor-Critic (SAC). Here’s a detailed comparison of these algorithms and key concepts in reinforcement learning.

### Key Concepts

1. Policy
Definition: A policy determines the action an agent should take given a particular state.
Deterministic Policy: Direct relationship between state and action (e.g., always playing rock in rock-paper-scissors). Not ideal in dynamic situations where adaptability is needed.
Stochastic Policy: Provides a range of possible actions for a state, each with a probability. Better for dynamic environments as it introduces variability.

2. Value Function
Purpose: Estimates the value of being in a state and the expected future rewards from that state.
Usage: Helps critique the policy by determining if the chosen action (and resulting state) is beneficial in the long run.

3. Policy Update
Process: Regularly adjusts the policy based on feedback from the value function. This can be triggered after a set number of episodes.

## Algorithms in AWS DeepRacer

1. **Proximal Policy Optimization (PPO)**
Type: On-policy learning.
Data Usage: Learns from observations made by the current policy only.
Analogy: Reviewing videos of recent driving lessons to improve based on the most current feedback.
Benefits:
Generally produces a more stable model in the short term.
Directly uses recent, relevant data for training.
Drawbacks:
Requires more new data for each policy update.
Limited by the data available from the most recent experiences.

2. **Soft Actor-Critic (SAC)**
Type: Off-policy learning.
Data Usage: Can use observations from previous policies and historical data.
Analogy: Reviewing older driving lesson videos and those of other drivers to improve.
Benefits:
Can use less new data due to the use of historical observations.
Potentially more data-efficient by incorporating past experiences.
Drawbacks:
Might produce a less stable model in the short term due to the use of older data.
Historical data may include less relevant or outdated information.

### Choosing Between PPO and SAC

PPO: Suitable if stability and the use of the most recent data are priorities.
SAC: Useful when leveraging historical data for potentially more data-efficient learning.

### Conclusion

Both PPO and SAC have their strengths and weaknesses. The choice of algorithm depends on specific needs and circumstances. Experimentation and tuning are key to finding the most effective approach for your particular scenario in AWS DeepRacer or other reinforcement learning applications.

Reference videos: 
1. https://www.youtube.com/watch?v=wtRYcwFeUks
2. https://www.youtube.com/watch?v=GtGXORN7Ju8
3. https://www.youtube.com/watch?v=YjSD1el5AQ0
4. https://www.youtube.com/watch?v=gKRtfO-r8NI

# Reward Functions

**Introduction:**
- The reward function is a key component in reinforcement learning, particularly for AWS DeepRacer. Its purpose is to issue rewards based on the effectiveness of the agent's actions in achieving the ultimate goal—navigating the track as quickly as possible.

**How Rewards are Calculated:**
- The reward function is controlled by the user and is implemented as a piece of code.
- It determines the reward value based on input parameters that describe the state of the agent and the environment.

**Input Parameters:**
- AWS DeepRacer provides over 20 input parameters that describe various aspects of the agent and its environment.
- These parameters are passed to the reward function as a single parameter, which is a Python dictionary containing all the input parameters.

**Writing the Reward Function:**
- The reward function is written in Python and must be named `reward_function`.
- It takes one parameter (the dictionary of input parameters) and returns a number (the reward).

**Adjusting the Reward Function:**
- The reward function can be modified even after training a model. This allows for tweaking and optimizing the agent's behavior.
- For example, if the model zig-zags along the track, you can add code to penalize this behavior.

**Examples and Experimentation:**
- Experimentation is key to finding a reward function that works well.
- Examples of reward functions and a list of available input parameters can be found in the AWS DeepRacer Developer Guide.

**Complexity of the Reward Function:**
- The complexity of the reward function can vary. However, a more complex reward function does not necessarily yield better results.

**Validation:**
- Always validate your reward function using the "Validate" button in AWS DeepRacer.
- Validation checks for syntax errors but does not assess the practical effectiveness of the reward function.

**Conclusion:**
- Understanding and customizing the reward function is crucial for training an effective AWS DeepRacer model.
- Through experimentation and iteration, you can craft a reward function that optimally guides your agent to achieve its goals on the track.

### Reference Videos
1. https://www.youtube.com/watch?v=ANIRYsZZ4XI
2. https://www.youtube.com/watch?v=pov0afxAvlo
3. https://www.youtube.com/watch?v=IVZlh_PPHw0
4. https://www.youtube.com/watch?v=CDUvW0YVqCc

# How the AWS DeepRacer device works

### How AWS DeepRacer Works

**Introduction:**
- AWS DeepRacer is a 1/18th scale race car equipped with an onboard computer, cameras, and optionally, a LiDAR sensor.
- It uses machine learning models to make real-time decisions and navigate the track.

**Machine Learning Inference:**
- After training a model in the AWS DeepRacer console, it is loaded onto the AWS DeepRacer device.
- The onboard computer uses this model to make decisions through a process called machine learning inference.
- Inference involves running input data through the model to output predictions, guiding the car on the track.

**Performance Metrics:**
- Inference Rate: Number of inferences per second.
- Inference Time (Latency): Time taken to run a single inference.
- Performance depends on factors like CPU speed, GPU acceleration, and system RAM.

**Challenges of Edge Computing:**
- AWS DeepRacer performs inference locally due to latency constraints.
- Edge devices, like the AWS DeepRacer, have limited compute power compared to cloud servers.

**Optimizing for Edge Devices:**
- Models need to be optimized for efficient performance on the device's hardware.
- OpenVINO toolkit is used to optimize models for Intel hardware.

**OpenVINO Toolkit:**
- Stands for Open Visual Inferencing and Neural Network Optimization.
- Includes the Deep Learning Deployment Toolkit, inference engine, and pre-trained models.
- Helps optimize models for different hardware, including CPUs and GPUs.

**Optimization Process:**
1. **Convert and Optimize:**
   - Use the model optimizer to prepare the pre-trained model for inferencing.
   - Generates Intermediate Representation (IR) files for the inference engine.
   
2. **Further Tuning (Optional):**
   - Use additional tools for advanced performance tuning.
   - The Post-Training Optimization Toolkit (POT) can reduce model precision for better performance.
   - Benchmarking and accuracy checker tools provide performance and accuracy data.

3. **Deploy the Model:**
   - Upload the optimized model to the AWS DeepRacer device.
   - Perform real-time inference using the OpenVINO toolkit inference engine.

**Conclusion:**
- Understanding the AWS DeepRacer device's decision-making process and optimization techniques is crucial for effective performance.
- Utilizing tools like the OpenVINO toolkit can help achieve efficient and real-time inference on edge devices.


### Reference Videos
1. https://www.youtube.com/watch?v=jdIIzeNK5ak
2. https://www.youtube.com/watch?v=hJNe6BM2p64
3. https://www.youtube.com/watch?v=qdOnF5rVOZ0
4. https://www.youtube.com/watch?v=ZiS6ERox0UI
5. https://www.youtube.com/watch?v=wwgm3eA-vx8
6. https://www.youtube.com/watch?v=06PUFbmrDpE

### Pro Tips
https://www.youtube.com/watch?v=KiPVdKESroU
