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

In this work, the proposed solution is to use learned inertial odometry without relying on auxiliary sensors like LiDAR or cameras. The model used here is AirIMU. AirIMU learns the correct gyroscope and accelerometer values with their corresponding covariances. The result is evaluated using absolute trajectory error from integrated trajectory with raw integration. The proposed method shows 26% better performance compared to the raw integration baseline.

<p align="center">
  <img src="https://adrienzhh.github.io/honghao/images/shaky_perception.jpg" style="width: 100%;"><br>
  <em>Add your caption here</em>
</p>

