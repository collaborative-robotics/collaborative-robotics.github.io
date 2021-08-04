---
layout: default
---

# 2021 Raven/dVRK Surgical Robotics Challenge (online)

Automating surgical subtasks is an oft-mentioned research target for robot-assisted surgery. Certain subtasks, such as
suturing and resection, have been automated on test bench setups. Yet current works are often limited in scope
(i.e., based on very simplistic setups) and lack a standardized setup to reproduce results. In this challenge, we provide
a simulation platform for participants to develop algorithms to address various questions in surgical subtask
automation. The simulator contains two seven degrees-of-freedom (DOF) instrument arms based on the da Vinci Surgical
System large needle driver, a controllable camera based on the da Vinci Endoscopic Camera Manipulator (ECM), a suturing
phantom, and a needle with suture.

![Sample Surgical Scene](/surgical-robotics-challenge/surgical_scene_ambf.gif)

**Please check back for details of the challenge.**

## System Setup

The challenge is based on the [Asynchronous Multi-Body Framework (AMBF)](https://github.com/WPI-AIM/ambf)
simulator, Version TBD. We will provide a Docker container with Ubuntu 18.04, ROS Melodic, AMBF and sample
Python scripts.

However, for better graphics performance, we recommend installing AMBF directly on Linux, rather than
using it within Docker. In this scenario, the Python scripts in the Docker container will use ROS to
communicate with AMBF running outside the Docker container.

## Challenge Tasks

The challenge is partitioned into three tasks. While these tasks naturally build on each other, it is possible to perform any subset of the tasks. All tasks will use the suture phantom shown in the above image, where the scene contains the phantom, a needle with suture, and up to two da Vinci large needle drivers.

### Challenge 1: Finding the needle

*Task:* Develop algorithms to identify the pose (position and orientation) of the metallic suture needle in the scene,
        under various lighting conditions and backgrounds.

*Provided Data:* None. Competitors must generate their own training data.

*Evaluation:* Entries will be evaluated on the time to find the pose estimate and the DICE score between the estimated placement of the needle and the ground truth. Each algorithm will be tested multiple times, with the needle in a different location, and with different lighting conditions and backgrounds.

*Variations:* Algorithms may move the camera to better identify the needle pose. Note, however, that the simulator will add a realistic amount of error to the measurement of camera motion.

### Challenge 2: Grasp needle and bring to target

*Task:* Given pose of needle and position of first target on phantom, move large needle driver to grasp the needle and then move the needle tip to the target. The accuracy of the simulated robot will be comparable to that of a real robot and thus visual feedback would be required to ensure accurate placement.

*Provided Data:*
1. Ground-truth pose of needle
2. Ground-truth position of first target on phantom
3. Illustrations of good needle grasps

*Evaluation:* Entries will be judged based on the time their algorithm took to place the needle and the distance between the needle tip and ground-truth target position.

### Challenge 3: Drive needle through tissue

*Task:* Develop algorithms to drive the needle through the phantom from the first entry point to the corresponding exit point. The left instrument should pull the needle through the phantom and hand back the needle to the right instrument. This completes one suture. The algorithm should repeat the entry and exit for each pair of points.

*Provided Data:*
1. The positions of all entry and exit points on the phantom
2. Additional points to define the desired circular path between each entry and exit point
3. The starting pose between the needle and the (right) instrument

*Initial conditions:* The right instrument is holding the needle in a correct grasp

*Evaluation:* Entries will be judged by how long it took to complete the suture and how accurate the entry and exit point placements were.
