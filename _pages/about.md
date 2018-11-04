---
permalink: /
title: "Summary"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% include base_path %} 

My research and interest areas are follows:
* Robotics Control and Perception
* Mechatronics
* Optimization
* Data Structure and Algorithm

Education
======
* B.S. in Shanghai, University of Shanghai for Sci and Tech, 2014
* M.S. in Ann Arbor, University of Michigan, 2019

Work experience
======
* Summer 2018: Summer Internship
  * Hongjing Drive
  * Duties included: lidar and cameara sensors fusion, autonomous vehicle localization

* Winter 2018: Research Assistant
  * University of Michigan, Ann Arbor
  * Duties included: analyse driving data, find driving primitives by applying machine learning
  * Supervisor: Professor Ding Zhao
  
* Fall 2014- Fall 2017: Advanced Driving Assistant System Enginner
  * Volkswagen, Shanghai
  * Duties included: refine operating modes of ADAS, CAN network of whole system, do trade off analysis
  
Publications
======
  <ul>{% for post in site.publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
 
Projects
======

| Description | Image |
| :--- | :---: |
|**Implemented 6-DOF rigid-body coordinate transforms by using homogeneous coordinate transforms.** `Acting` <br>Modeled the forward and inverse kinematics for manipulator.`Acting`<br> **Calibrated the workspace, RGB camera and depth camera.**`Perception`<br>Implemented robust object detection algorithm by fusion information from both sensors.`Perception`<br>**Conducted path planning for manipulator to get smooth and obstacle free trajectories.**`Reasoning`<br>| ![rexarm_150x150.png](/images/rexarm_150x150.png)  | 
|**Implemented dynamic control of DC motors to balance a wheeled pendulum.** `Acting` <br>Integrated IMU data with wheel encoders to perform a gyrodometric-based dead-reckoning navigation system.`Perception`<br> **Achieved potential field planning to navigate a set of waypoints as fast as possible by using <br>feedback from Optitrack motion capture system.**`Reasoning`| ![balancebot.png](/images/balanceBot.png)  |
|**A Raspberry Pi 3 performs SLAM calculations, path planning, and collects 2D Lidar<br>  Measurements.**`Hardware`<br> A Beaglebone Green with a Mobile Robotics Cape interfaces with the wheel encoders, IMU, <br> and motors and handles motor commands, velocity control,  and odometry. `Hardware` <br> **Created a simultaneous localization and mapping (SLAM) system using 2D lidar <br>by constrcting an occupancy grid and implementing Monte Carlo Localization in a known map.**`Perception`<br> A Star Planning and autonomous exploration in an unkonwn environment.`Perception`<br>| ![mobilerobot.png](/images/mobilerobot.png)  | 

Skills
======
* Robotics: Control, Perception and Reasoning
* Embeded System Programming
* Coding
  * C++
  * Python
  * Matlab
