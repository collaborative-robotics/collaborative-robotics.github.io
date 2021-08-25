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

![Sample Surgical Scene](/surgical-robotics-challenge/figure_eight.gif)

**Please check back for details of the challenge. Tentative details below -- subject to change.**

## Timeline

**September 1, 2021:**  Challenge opens

**February 1, 2022:**  Challenge closes (all Docker containers must be submitted)

**March 1, 2022:**  Challenge results announced

## Awards

Awards will be given for the winning entries in each challenge. Details to be announced.

## System Setup

The challenge is based on the [Asynchronous Multi-Body Framework (AMBF)](https://github.com/WPI-AIM/ambf)
simulator, *Version 2.0.X*, along with the
[Surgical Robotics Challenge Assets](https://github.com/adnanmunawar/surgical_robotics_challenge).
To install AMBF and the associated assets (including the launch file), follow the instructions
[here](https://github.com/adnanmunawar/surgical_robotics_challenge).
Note that AMBF and the Assets should be installed directly on Linux, rather than within Docker.

We will provide Docker containers that contain Linux, ROS and Python scripts that use ROS to communicate
with AMBF running outside Docker.
Challenge competitors should add all required software to the Docker container and submit it
for judging via a link to be provided.
Competitors can choose the most convenient configuration from one of the two provided Docker containers:
1. Ubuntu 18.04, ROS Melodic, and sample Python scripts.
2. Ubuntu 20.04, ROS Noetic, and sample Python scripts.

## Challenge Tasks

The challenge is partitioned into three tasks. While these tasks naturally build on each other, it
is possible to perform any subset of the tasks. All tasks will use the suture phantom shown in the
above image, where the scene contains the phantom, a needle with suture, and up to two da Vinci
large needle drivers. The view of the scene is provided by a simulated stereo endoscope, with a
camera baseline as in a real da Vinci. By default, there is one light attached to the endoscope, but
lighting can vary up to twice this amount (i.e., equivalent to two lights attached to the
endoscope).

The only requirement is that the developed algorithms perform the tasks autonomously. There is no
requirement to use a particular type of machine learning, or even to use machine learning at all.

All entries will be tested under the same set of test conditions. Descriptions of the test
conditions for each challenge are provided below.

### Challenge 1: Finding the needle

**Task:** Develop algorithms to identify the pose (position and orientation) of the metallic suture
needle, with respect to the current endoscope pose.

**Provided Data:**
1. 3D model of needle (part of AMBF scene)
2. Camera calibration
3. Competitors must generate their own training data (if needed)

**Test Conditions:** Each entry will be tested with different views of the surgical scene, with the
needle in different locations. The entire needle will be in the field-of-view. One or two
instruments may be present in the scene but will not overlap with the needle. The needle will be
located between *MIN* and *MAX* meters from the endoscope. Lighting can vary as specified above.

**Evaluation Metric:** Entries will be evaluated on the time to find the pose estimate and the
difference between the estimated pose and the ground truth. All algorithms must output a needle
pose within 10 seconds. The pose difference will be determined by the distance between three fixed
points on the needle: tip, middle and end. All entries that meet the time requirement will be
ranked by the sum of the three distance errors.

**Variations:** Algorithms may move the camera to better identify the needle pose. Note, however,
that the simulator will add a realistic amount of error to the measurement of camera pose. Also,
moving the camera will increase the time required to find the needle and will count toward the 10
second time limit.

### Challenge 2: Grasp needle and drive through tissue

**Task:** Move large needle driver to grasp the needle and then move the needle tip to the target
and drive the needle through the tissue until the tip exits. The accuracy of the simulated robot
will be comparable to that of a real robot and thus visual feedback would be required to ensure
accurate performance.

<video width="640" height="480" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge/task2_clip.mp4">
Your browser does not support the video tag.
</video>

**Provided Data:**
1. Ground-truth pose of needle
2. Ground-truth position of first target entry and exit on phantom
3. Target pose for grasping needle (i.e., relative pose between PSM gripper and needle)

**Test Conditions:** Each entry will be tested with multiple trials, where the needle position and
target positions will vary for each trial. In addition, the kinematic parameters of the robot will
vary from the nominal values to emulate robot inaccuracy. Specifically, the simulator will use the
nominal kinematic parameters for inverse kinematics (e.g., to convert Cartesian goals into joint
goals), but then will use the perturbed kinematic parameters in the forward kinematics to compute
the Cartesian trajectory of the simulated robot. For some trials, the kinematic parameters will
have little or no error, thereby allowing the task to be completed without visual feedback,
whereas for other trials, visual feedback will be necessary to successfully complete the task.

**Evaluation Metric:** Entries will be judged based on the time the algorithm required to perform
the task and the achieved accuracy. Accuracy will be measured by the distance between the needle
trajectory and the target entry and exit positions, and the amount of needle that is visible
beyond the exit point. All entries must be within *TBD (5 mm?)* of the target entry/exit and at
least *TBD (5 mm?)* of the neele tip must be visible. All entries that pass the accuracy threshold
will be ranked based on completion time.

### Challenge 3: Suture the phantom

**Task:** Develop algorithms to drive the needle through the phantom from the first entry point to
the corresponding exit point. The left instrument should pull the needle through the phantom and
hand back the needle to the right instrument. This completes one suture. The algorithm should repeat
the entry and exit for each pair of points.  As in the previous challenges, the accuracy of the
simulated robot will be comparable to that of a real robot.

**Provided Data:**
1. The positions of all entry and exit points on the phantom
2. Additional points to define the desired circular path between each entry and exit point
3. The starting pose between the needle and the (right) instrument

**Test Conditions:** Test conditions will be the same as specified for Challenge 2, except that the
challenge will begin with the right instrument holding the needle in a correct grasp.

**Evaluation Metric:** The evaluation metric will be the same as Challenge 2; specifically, all
entries that meet the specified accuracy thresholds will be ranked based on completion time.
