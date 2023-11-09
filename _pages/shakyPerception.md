---
title: "Shaky Perception: How to improve robustness when robot under high dynamic locomotion"
permalink: shakyPerception/
author_profile: true
---

In the landscape of robotics and autonomous systems, the simultaneous localization and mapping (SLAM) technology plays a pivotal role in enabling robots to navigate and comprehend their surroundings. However, it faces a significant challenge when confronted with high dynamic robotic motion, leading to feature distortion and unstable measurements. 


To validate the effectiveness of our Lidar-Inertial SLAM framework and to demonstrate its superior performance, I conducted a series of comprehensive experiments in a simulated environment. To make robots dynamic, I use a robot with varied head pitching motion. The pitch changes from 1 to 2.5 Hz to distinguish the dynamics level. An IMU, lidar sensor and camera is used to simulate sensor information for my research study. I compare lidar and IMU fusion approach with the camera and IMU fusion. 

Our Lidar-Inertial SLAM framework leverages the combined power of Lidar and IMU sensors. This integration delivers a substantial leap in performance by addressing the key issues faced by camera SLAM systems. The Lidar-Inertial fusion offers superior accuracy in compared to camera and IMU fusion under high dynamic scenarios. Lidar sensors provide accurate and high-resolution 3D point cloud data of the surrounding environment. They are excellent at capturing detailed information about obstacles, landmarks, and the terrain. Inertial sensors can capture the motion of an object over time, making them less susceptible to drift that can accumulate in purely vision-based systems. The combination of Lidar's precise distance measurements and IMU's continuous motion tracking significantly reduces the margin of error. 

Based on current progress, I am utilizing the dynamics of the robot to assist feature extraction in the front end and ensure a tightly-coupled factor graph optimization between LiDAR and IMU. I expect an increase in trajectory robustness compared to many state-of-art LiDAR related SLAM algorithms, such as LOAM and LIO-SAM. I intend to submit the result of this work to IROS 2024.


<div style="display: flex; flex-direction: row;">
    <img src="images/hans_experiment_setup.gif" alt="GIF" style="width: 40%;height: 120px;" />
    <div style="flex: 1; padding-left: 20px;">
        <p style="font-size: 15px;">
            <a href="https://adrienzhh.github.io/honghao/shakyPerception/"><b>Shaky Perception</b></a><br>
            Improve robustness of LiDAR-inertial SLAM under high robot dynamic
        </p>
    </div>
</div>

<div style="text-align:center"><img src="/images/image-alignment-150x150.jpg"/></div>
