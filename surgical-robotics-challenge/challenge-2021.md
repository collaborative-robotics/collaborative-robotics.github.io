---
layout: default
---

# 2021-2022 AccelNet Surgical Robotics Challenge (online)

Automating surgical subtasks is an oft-mentioned research target for robot-assisted surgery. Certain
subtasks, such as suturing and resection, have been automated on test bench setups. Yet current
works are often limited in scope (i.e., based on very simplistic setups) and lack a standardized
setup to reproduce results. In this challenge, we provide a simulation platform for participants to
develop algorithms to address various questions in surgical subtask automation. The simulator
contains two seven degrees-of-freedom (DOF) instrument arms based on the da Vinci Surgical System
large needle driver, a controllable camera based on the da Vinci Endoscopic Camera Manipulator
(ECM), a suturing phantom, and a needle with suture.

The philosophy of this challenge is to provide competitors with the tools to generate any required data
(e.g., for training neural networks), rather than providing common datasets. We encourage contributions
back to the repository, which can be made during or after the challenge.
For example, one useful contribution would be a script file that facilitates the
collection of ground-truth data for training a neural network.

## News

12/14/2021: Announcing the [GitHub Discussions forum](https://github.com/collaborative-robotics/surgical_robotics_challenge/discussions) for questions and comments. See the [Community page](./community.md) for more information.

01/26/2022: Deadline extended from Feb 1, 2022 to May 1, 2022 and added registration form (see below). One motivation is to enable student projects organized around the challenge for the Spring 2022 semester.

03/16/2022: Additional details in [System Setup](./system-setup.md); clarification about target entry and exit points for
[Challenge 2](./challenge-2.md) and [Challenge 3](./challenge-3.md); cash prize total is $3000.

04/06/2022: Added example script files (see [System Setup](./system-setup.md)); updated scripts in Surgical Robotics Challenge Assets to use new CRTK convention for `measured_cp` (`geometry_msgs/PoseStamped` instead of `geometry_msgs/TransformStamped`); added information about simulation units (1 mm = 0.01 SU, 1 SU = 100 mm = 0.1 m) -- see new figure in [Challenge 2](./challenge-2.md).

04/16/2022: Updated example script files ([interface_via_crtk_ros_api.py](https://github.com/collaborative-robotics/surgical_robotics_challenge/blob/master/scripts/surgical_robotics_challenge/examples/interface_via_crtk_ros_api.py) and
[interface_via_method_api.py](https://github.com/collaborative-robotics/surgical_robotics_challenge/blob/master/scripts/surgical_robotics_challenge/examples/interface_via_method_api.py))
to demonstrate reporting of Challenge Task completion, and to call method (`task_3_setup_init`)
or publish ROS topic (`task_3_setup/init`) that initializes needle in grasper for [Challenge 3](./challenge-3.md).
Also, added information about robot kinematic error in [Challenge 2](./challenge-2.md).

04/23/2022: Deadline extended from May 1 to June 6 to avoid conflicts with final exams, ICRA and the US Memorial Day holiday. This is the final deadline extension.

04/26/2022: Changed time limit for Challenge 1 from 10 seconds to 60 seconds.

05/20/2022: Added [evaluation script](https://github.com/collaborative-robotics/surgical_robotics_challenge/blob/master/scripts/surgical_robotics_challenge/evaluation/evaluation.py) to GitHub repository. This script will be used to evaluate entries submitted to each of the 3 challenges and is provided so that competitors can better test their algorithms prior to submission. Note that this is a beta version of the script and may be updated. See the [GitHub Discussions forum](https://github.com/collaborative-robotics/surgical_robotics_challenge/discussions/50) for more information.

06/01/2022: Added submission instructions, summarized below, with details [here](./submission.md).

06/30/2022: Winners announced -- see below.

## Timeline

**September 15, 2021:**  Challenge opens

**June 6, 2022:**  Challenge closes (all Docker containers must be submitted)

**June 30, 2022:**  Challenge results announced

## Registration

Please register as soon as possible if you wish to submit an entry to the challenge. This will allow us
to better plan for the evaluation phase. It will also enable us to inform you about any important updates.

There are no restrictions on who can participate in this challenge. We expect most participants to be part of a team,
so it is only necessary for one person to register the team. If you wish, you can add the names of other participants in
the "Additional comments" box.

[Registration form](https://docs.google.com/forms/d/e/1FAIpQLSdvMuCxsjfvFgs0coQdIU9OBRH2Al7OsUDGsmN_WbY1AL090Q/viewform?usp=sf_link)

## Awards

Awards will be given for the winning entries in each challenge. The awards will consist of
cash prizes and travel grants to a future (in-person) AccelNet Surgical Robotics Challenge.

Intuitive Surgical is sponsoring a cash prize total of $3000, to be distributed between the winning entries for each challenge.

## Results

We thank all competitors for participating in the challenge and we are pleased to announce the
following results:

* **First Place ($1,700)**: Team Tstone, Chinese University of Hong Kong
* **Second Place ($800)**:  Team WPI Aim Lab, Worcester Polytechnic Institute
* **Third Place ($500)**:   Team SDU, University of Southern Denmark

Additional details are available [**here**](./results.md).

## [System Setup](./system-setup.md)

The challenge is based on the [Asynchronous Multi-Body Framework (AMBF)](https://github.com/WPI-AIM/ambf)
simulator. Participants will be required to install AMBF on a Linux system and download a Docker
container. Algorithms should be implemented within a Docker container and submitted for testing.
Additional details are provided [**here**](./system-setup.md).

## [Submission Instructions](./submission.md)

Submissions to the challenge should use this [**form**](https://forms.gle/EECUaqJ2YReGbJte9).
The challenge tasks are difficult enough, so our goal is to make the submission process
as easy and as flexible as possible. See [**this page**](./submission.md) for additional details.

## Challenge Tasks

The challenge is partitioned into three tasks summarized below. While these tasks naturally build on each other, it
is possible to perform any subset of the tasks. All tasks will use a suturing phantom,
a needle with suture, and up to two da Vinci
large needle drivers. The view of the scene is provided by a simulated stereo endoscope (1080p, 30fps), with a
camera baseline as in a real da Vinci. By default, there is one light attached to the endoscope, but
lighting can vary up to twice this amount (i.e., equivalent to two lights attached to the
endoscope).

The only requirement is that the developed algorithms perform the tasks autonomously. There is no
requirement to use a particular type of machine learning, or even to use machine learning at all.
Note that the videos below for Challenges 2 and 3 were created using teleoperation.

All entries will be tested under the same set of test conditions. Descriptions of the test
conditions are provided in the detailed pages for each challenge.

<hr>

### [Challenge 1: Find the needle](./challenge-1.md)

<div style="float:right; margin-left:25px">
<video width="480" height="270" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge/task1_clip.mp4">
Your browser does not support the video tag.
</video></div>

<p style="height:270px">
<b>Task:</b> Develop algorithms to identify the pose (position and orientation) of the metallic suture
needle, with respect to the current endoscope pose. The video shows two sample endoscope images.
<a href="./challenge-1.html">[More...]</a>.
</p>

<hr>

### [Challenge 2: Grasp needle and drive through tissue](./challenge-2.md)

<div style="float:right; margin-left:25px">
<video width="480" height="270" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge/task2_clip.mp4">
Your browser does not support the video tag.
</video></div>

<p style="height:270px">
<b>Task:</b> Move the large needle driver to grasp the needle and then move the needle tip to the target
and drive the needle through the tissue until the tip exits. The accuracy of the simulated robot
will be comparable to that of a real robot and thus visual feedback would be required to ensure
accurate performance.
<a href="./challenge-2.html">[More...]</a>.
</p>

<hr>

### [Challenge 3: Suture the phantom](./challenge-3.md)

<div style="float:right; margin-left:25px">
<video width="480" height="270" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge/task3_clip.mp4">
Your browser does not support the video tag.
</video></div>

<p style="height:270px">
<b>Task:</b> Drive the needle through the phantom from the first entry point to
the corresponding exit point. The left instrument should pull the needle through the phantom and
hand back the needle to the right instrument. This completes one suture. The algorithm should repeat
the entry and exit for each pair of points.
<a href="./challenge-3.html">[More...]</a>.
</p>

<hr>

### Contact

Please use the [GitHub Discussions forum](https://github.com/collaborative-robotics/surgical_robotics_challenge/discussions) for questions and comments. See the [Community page](./community.md) for more information.

To contact the organizers by email: [accelnet-robotics-challenge-admin@googlegroups.com](mailto:accelnet-robotics-challenge-admin@googlegroups.com)

### Acknowledgments

<p><img src="/images/NSF-logo.png" alt="NSF Logo" style="float:left; width:80px; height:80px; margin-right:25px">
Development of this Surgical Robotics Challenge is supported by the United States National Science Foundation (NSF)
via OISE-1927354 and OISE-1927275, <i>AccelNet: International Collaboration to Accelerate Research in Robotic Surgery</i>.</p>
