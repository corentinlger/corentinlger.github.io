---
date: 2024-10-15T11:00:59-04:00
tags: ['Robotics', 'Reinforcement Learning']
title: "Hackathon: LeRobot"
author: "Corentin"
categories: ['Hackathon']
---

### Introduction 

I participated in the LeRobot Hackathon in Toulouse, organized by the Hugging Face team 🤗 !  It was a great way to get my first steps into real-world reinforcement learning and robotics.

We went from having a very messy table (see below) with a lot of hardware parts to a fully assembled robot in a few hours. It was a robotic arm with a gripper, the Moss v1 and we tried to teach it how to manipulate a cube.

![install](/lerobot_install.png)

With friends, we then decided to chose the Reinforcement Learning track. To do so, we calibrated a first arm with another one we could controll manually, we set up a camera, and started creating a real world RL environment. It was a simple plate with a cube on it, and the goal was to push the cube to the other side of the plate. We recorded a dataset of 'expert' demonstrations (ours) with LeRobot library, and trained the arm with offline Reinforcement Learning using the TD-MPC algorithm. 

After this, we continued training the robot, but this time with online RL, whith the arm collecting trajectories itself in the real world ! 
We finally achieved an fun result, where our robot excelled in pushing the cube from right to left, but struggled to do a left-to-right motion.

![training](/lerobot_training.gif)

This hands-on experience has sparked my interest for real-world robotics, motivated me to explore this in new projects. There’s something mesmerizing about watching algorithms come to life in the real world. Thanks to all the collaborators on the project : Waris Radji, Anthony Kobanda, Mathieu Petitbois, Théo Michel and Mohamed Yassine Kabour, as well as all the LeRobot team for organizing this event ! Link to their project: [LeRobot](https://github.com/huggingface/lerobot)


