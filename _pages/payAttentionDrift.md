---
layout: archive
title: "Pay Attention to How You Drive: Safe and Adaptive Model-Based Reinforcement Learning for Off-Road Driving"
permalink: payAttentionDrift/
author_profile: true
---

In this project, we present a novel model-based reinforcement learning approach that combines transformer and LSTM techniques. This allows a robot to adapt to different environments while maintaining safety through Sim2Real transfer. Our approach results in an approximate 41% improvement in lap time compared to the non-adaptive baseline. The general framework consists of three main modules. The first, a transformer module, enables the robot to learn and process historical information, outputting a context vector that feeds into an LSTM module. In combination with the previous 10 state-action observations, we predict future trajectories. The trajectory is then optimized to ensure risk-awareness using MPPI, a stochastic sampling-based model predictive control (MPC).

<p align="center">
  <img src="https://adrienzhh.github.io/honghao/images/pay_drift_framework.png" style="width: 60%;"><br>
  <em>Framework</em>
</p>

Within the project, I took on the responsibility of transferring and adding new functionalities to our code from simulation to the Robot Operating System (ROS) to help out our real-world experiments using Python. As we increased our experiment repetitions, this became a significant and stressful challenge since many problems arose from robot wear and tear to pipeline issues that lead to data collection failures. Yet I successfully managed to handle the situation and maintain iterative code implementations to meet our rapid experimental requirements and keep up team morale. 

<p align="center">
  <img src="https://adrienzhh.github.io/honghao/images/icra_2024_for_website.gif" alt="GIF" style="width: 60%;"><br>
  <em>Sim2Real</em>
</p>

<p align="center">
  <video width="640" height="480" controls>
    <source src="https://adrienzhh.github.io/honghao/images/ICRA24_3555.mp4" type="video/mp4">
  </video>
</p>





