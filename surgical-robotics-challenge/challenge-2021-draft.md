---
layout: default
---

# 2021 Raven/dVRK Surgical Robotics Challenge (online)

Automating surgical subtasks is an oft-mentioned research target for robot-assisted surgery. Certain
subtasks, such as suturing and resection, have been automated on test bench setups. Yet current
works are often limited in scope (i.e., based on very simplistic setups) and lack a standardized
setup to reproduce results. In this challenge, we provide a simulation platform for participants to
develop algorithms to address various questions in surgical subtask automation. The simulator
contains two seven degrees-of-freedom (DOF) instrument arms based on the da Vinci Surgical System
large needle driver, a controllable camera based on the da Vinci Endoscopic Camera Manipulator
(ECM), a suturing phantom, and a needle with suture.

## Timeline

**September 15, 2021:**  Challenge opens

**February 1, 2022:**  Challenge closes (all Docker containers must be submitted)

**March 1, 2022:**  Challenge results announced

## Awards

Awards will be given for the winning entries in each challenge. Details to be announced.

## System Setup

The challenge is based on the [Asynchronous Multi-Body Framework (AMBF)](https://github.com/WPI-AIM/ambf)
simulator. Participants will be required to install AMBF on a Linux system and download a Docker
container. Algorithms must be implemented within a Docker container and submitted for testing.
Additional details are provided [here](/surgical-robotics-challenge/system-setup.md).


## Challenge Tasks

The challenge is partitioned into three tasks summarized below. While these tasks naturally build on each other, it
is possible to perform any subset of the tasks. All tasks will use a suturing phantom,
a needle with suture, and up to two da Vinci
large needle drivers. The view of the scene is provided by a simulated stereo endoscope, with a
camera baseline as in a real da Vinci. By default, there is one light attached to the endoscope, but
lighting can vary up to twice this amount (i.e., equivalent to two lights attached to the
endoscope).

The only requirement is that the developed algorithms perform the tasks autonomously. There is no
requirement to use a particular type of machine learning, or even to use machine learning at all.

All entries will be tested under the same set of test conditions. Descriptions of the test
conditions for each challenge are provided below.

### [Challenge 1: Finding the needle](/surgical-robotics-challenge/challenge-1.md)

**Task:** Develop algorithms to identify the pose (position and orientation) of the metallic suture
needle, with respect to the current endoscope pose.

### [Challenge 2: Grasp needle and drive through tissue](/surgical-robotics-challenge/challenge-2.md)

**Task:** Move large needle driver to grasp the needle and then move the needle tip to the target
and drive the needle through the tissue until the tip exits. The accuracy of the simulated robot
will be comparable to that of a real robot and thus visual feedback would be required to ensure
accurate performance.

<video width="480" height="270" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge/task2_clip.mp4">
Your browser does not support the video tag.
</video>

### [Challenge 3: Suture the phantom](/surgical-robotics-challenge/challenge-3.md)

**Task:** Develop algorithms to drive the needle through the phantom from the first entry point to
the corresponding exit point. The left instrument should pull the needle through the phantom and
hand back the needle to the right instrument. This completes one suture. The algorithm should repeat
the entry and exit for each pair of points.  As in the previous challenges, the accuracy of the
simulated robot will be comparable to that of a real robot.

<video width="480" height="270" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge/task3_clip.mp4">
Your browser does not support the video tag.
</video>
