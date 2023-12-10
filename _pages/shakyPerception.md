---
layout: archive
title: "Shaky Perception: How to improve robustness when robot under high dynamic locomotion"
permalink: shakyPerception/
author_profile: true
---

In the landscape of robotics and autonomous systems, the simultaneous localization and mapping (SLAM) technology plays a pivotal role in enabling robots to navigate and comprehend their surroundings. However, it faces a significant challenge when confronted with high dynamic robotic motion, leading to feature distortion and unstable measurements. Below, we have a video showing stereo SLAM failed due to high dynamic motion on a Minitaur robot. 
<p align="center">
  <video width="640" height="480" controls>
    <source src="https://adrienzhh.github.io/honghao/images/shakeyPerception.MP4" type="video/mp4">
  </video>
</p>

Given the superior field of view and rich geometric information capture capabilities of LiDAR, I opted for a Lidar-Inertial SLAM approach to address the challenge. To validate the effectiveness of my Lidar-Inertial SLAM framework and to demonstrate its superior performance, I conducted a series of comprehensive experiments in a simulated environment. To make robots dynamic, I use a robot with varied head pitching motion. The pitch changes from 1 to 2.5 Hz to distinguish the dynamics level. Here, I tested state-of-art [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM) under different pitch frequency. We can see the large state estimation difference between 0 Hz (no pitching) and 2.5 Hz. 

<p align="center">
  <img src="https://adrienzhh.github.io/honghao/images/hans_experiment_setup.gif" alt="GIF" style="width: 60%;"><br>
  <em>Simulation Environment</em>
</p>

To evaluate the drift, I conducted a trajectory experiment on LiDAR and IMU odometry separately. Per observation, the LiDAR odometry drift is mostly due to the sparse features when the robot kept facing the angle view where we don't have good geometric information (it's similar to the blank hallway scenario in the SLAM problem, in which the state estimation remains still because the lack of feature changes). Because of this reason, this will lead to most open-sourced LiDAR-Inertial frameworks fail because they usually place a larger belief weight on LiDAR odometry when constructing a covariance matrix for backend optimization if we assume robust LiDAR odometry. A sample factor graph is shown below, the LiDAR factor serves as a constraint for IMU integration. 

<p align="center">
  <img src="https://adrienzhh.github.io/honghao/images/imu_factor_graph.png" style="width: 60%;"><br>
  <em>IMU factor graph</em>
</p>

As for the IMU, we can integrate IMU values to obtain IMU odometry. IMU odometry works well in a straight line however very sensitive if we experience sudden rotations or accelerations.  


A naive solution to this problem is to tune the covariance matrix between LiDAR and IMU odometry. However, this won't solve the problem generically. Consequently, the proposed approach involves relying solely on IMU odometry and developing a learning framework that employs the robot's gait as a constraint for propagating IMU covariance. In this scenario, we prioritize trust in the IMU's state estimation before our LiDAR odometry recovered. As a result, the proposed idea is to use IMU odometry exclusively and train alearning framework that uses robot gait as a constraint to propagate IMUcovariance. In this case, we will be trusting IMU state estimation before our LiDAR odometry is recovered. More specifically, we want to properly learn accelerator and gyroscope covariance $\Sigma_\eta^{a d}$ and $\Sigma_\eta^{g d}$ in relation to gait and being able to propagate IMU covariance kinematically. 
$$
\begin{equation}
\Sigma_{k+1}=A_k \Sigma_k A_k^T+B_k \Sigma_\eta^{a d} B_k^T+C_k \Sigma_\eta^{g d} C_k^T
\end{equation}
$$

More details to come as we proceed Shaky Perception!
