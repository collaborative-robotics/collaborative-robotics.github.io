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

![Sample Surgical Scene](/surgical-robotics-challenge/figure_eight.gif)

**Please check back for details of the challenge. Tentative details below -- subject to change.**

## System Setup

The challenge is based on the [Asynchronous Multi-Body Framework (AMBF)](https://github.com/WPI-AIM/ambf)
simulator, Version TBD. We will provide the following two Docker containers, so that competitors can choose
the most convenient configuration:
1. Ubuntu 18.04, ROS Melodic, and sample Python scripts.
2. Ubuntu 20.04, ROS Noetic, and sample Python scripts.

AMBF should be installed directly on Linux, rather than using it within Docker.
The Python scripts in the Docker container use ROS to communicate with AMBF running outside the Docker container.

## Challenge Tasks

The challenge is partitioned into three tasks. While these tasks naturally build on each other, it is possible to perform any subset of the tasks. All tasks will use the suture phantom shown in the above image, where the scene contains the phantom, a needle with suture, and up to two da Vinci large needle drivers. The view of the scene is provided by a simulated stereo endoscope, with a camera baseline as in a real da Vinci.

The only requirement is that the developed algorithms perform the tasks autonomously. There is no requirement to use a particular type of machine learning, or even to use machine learning at all.

### Challenge 1: Finding the needle

**Task:** Develop algorithms to identify the pose (position and orientation) of the metallic suture needle, with respect to the current endoscope pose, under various lighting conditions and backgrounds.

**Provided Data:**
1. 3D model of needle (part of AMBF scene)
2. Camera calibration
3. Competitors must generate their own training data (if needed)

**Evaluation:** Entries will be evaluated on the time to find the pose estimate and the difference between the estimated pose and the ground truth. The pose difference will be determined by the distance between three fixed points on the needle: tip, middle and end. Each algorithm will be tested multiple times, with the needle in a different location, and with different lighting conditions and backgrounds.

**Variations:** Algorithms may move the camera to better identify the needle pose. Note, however, that the simulator will add a realistic amount of error to the measurement of camera pose. Also, moving the camera will increase the time required to find the needle.

### Challenge 2: Grasp needle and drive through tissue

**Task:** Move large needle driver to grasp the needle and then move the needle tip to the target and drive the needle through the tissue until the tip exits. The accuracy of the simulated robot will be comparable to that of a real robot and thus visual feedback would be required to ensure accurate performance.

**Provided Data:**
1. Ground-truth pose of needle
2. Ground-truth position of first target entry and exit on phantom
3. Target pose for grasping needle (i.e., relative pose between PSM gripper and needle)

**Evaluation:** Entries will be judged based on the time their algorithm took to perform the task, the distance between the needle tip and how closely it passes through the ground-truth target entry and exit positions, and whether the needle tip exits the phantom. Grasp quality (pass/fail) will be assessed based on a threshold between the specified target pose and actual target pose.

### Challenge 3: Suture the phantom

**Task:** Develop algorithms to drive the needle through the phantom from the first entry point to the corresponding exit point. The left instrument should pull the needle through the phantom and hand back the needle to the right instrument. This completes one suture. The algorithm should repeat the entry and exit for each pair of points.
As in the previous challenges, the accuracy of the simulated robot will be comparable to that of a real robot.

**Provided Data:**
1. The positions of all entry and exit points on the phantom
2. Additional points to define the desired circular path between each entry and exit point
3. The starting pose between the needle and the (right) instrument

**Initial conditions:** The right instrument is holding the needle in a correct grasp

**Evaluation:** Entries will be judged by how long it took to complete the suture and how accurate the entry and exit point placements were.
