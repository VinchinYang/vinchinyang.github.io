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
* M.S. in Ann Arbor, University of Michigan, 2017

Work experience
======
* Summer 2018: Summer Internship
  * Hongjing Drive
  * Duties included: lidar and cameara sensors fusion, autonomous vehicle localization
  * Supervisor: Professor Git

* Winter 2017: Research Assistant
  * University of Michigan, Ann Arbor
  * Duties included: analyse driving data, find driving primitives by applying machine learning
  * Supervisor: Professor Zhao
  
Skills
======
* Skill 1
* Skill 2
  * Sub-skill 2.1
  * Sub-skill 2.2
  * Sub-skill 2.3
* Skill 3

Publications
======
  <ul>{% for post in site.publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
 
Projects
======

[![mstile-150x150.png](/images/rexarm_150x150.png)]({{< relref "post/B.md" >}})

| Project | Description |
| :--- | :---: |
|[ **Implemented 6-DOF rigid-body coordinate transforms by using homogeneous coordinate transforms.** `Acting` <br>Modeled the forward and inverse kinematics for manipulator.`Acting`<br> **Calibrated the workspace, RGB camera and depth camera.**`Sensing`<br>Implemented robust object detection algorithm by fusion information from both sensors.`Sensing`<br>**Conducted path planing for manupilator to get smooth and obstacle free trajectories.**`Reasoning`<br>](http://google.com) | ![rexarm_150x150.png](/images/rexarm_150x150.png)  | 
|[ **Implemented 6-DOF rigid-body coordinate transforms by using homogeneous coordinate transforms.** `Acting` <br>Modeled the forward and inverse kinematics for manipulator.`Acting`<br> **Calibrated the workspace, RGB camera and depth camera.**`Sensing`<br>Implemented robust object detection algorithm by fusion information from both sensors.`Sensing`<br>**Conducted path planing for manupilator to get smooth and obstacle free trajectories.**`Reasoning`<br>](http://google.com)| ![balancebot.png](/images/balancebot.png)  |

Talks
======
  <ul>{% for post in site.talks %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Service and leadership
======
* Currently signed in to 43 different slack teams
