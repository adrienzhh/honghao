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

To evaluate the drift, I conducted a trajectory experiment on LiDAR and IMU odometry separately. Per observation, the LiDAR odometry drift is mostly due to the sparse features when the robot kept facing the angle view where we don't have good geometric information (it's similar to the blank hallway scenario in the SLAM problem, in which the state estimation remains still because the lack of feature changes). Because of this reason, this will lead to most open-sourced LiDAR-Inertial frameworks fail because they usually place a larger belief weight on LiDAR odometry when constructing a covariance matrix for backend optimization. A sample factor graph is shown below, the LiDAR factor serves as a constraint for IMU integration. 

 As for the IMU, we can integrate IMU values to obtain IMU odometry. IMU odometry works well in a straight line however very sensitive if we experience sudden rotations or accelerations.  



My Lidar-Inertial SLAM framework leverages the combined power of Lidar and IMU sensors. This integration delivers a substantial leap in performance by addressing the key issues faced by camera SLAM systems. The Lidar-Inertial fusion offers superior accuracy in compared to camera and IMU fusion under high dynamic scenarios. Lidar sensors provide accurate and high-resolution 3D point cloud data of the surrounding environment. They are excellent at capturing detailed information about obstacles, landmarks, and the terrain. Inertial sensors can capture the motion of an object over time, making them less susceptible to drift that can accumulate in purely vision-based systems. The combination of Lidar's precise distance measurements and IMU's continuous motion tracking significantly reduces the margin of error. 

Based on current progress, I am utilizing the dynamics of the robot to assist feature extraction in the front end and ensure a tightly-coupled factor graph optimization between LiDAR and IMU. I expect an increase in trajectory robustness compared to many state-of-art LiDAR related SLAM algorithms, such as LOAM and LIO-SAM. I intend to submit the result of this work to IROS 2024.

<p align="center">
  <img src="https://adrienzhh.github.io/honghao/images/lio_sam.png" style="width: 60%;"><br>
  <em>Trajectory on rocky terrian using LIO-SAM</em>
</p>
