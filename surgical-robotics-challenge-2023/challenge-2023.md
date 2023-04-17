---
layout: default
---

# 2023-2024 AccelNet Surgical Robotics Challenge

This is a relaunch and update of the
[2021-2022 AccelNet Surgical Robotics Challenge](../surgical-robotics-challenge/challenge-2021.md).
As with the prior challenge, the goal is to further advance research in the
automation of surgical subtasks during robot-assisted surgery.
The primary changes are:
  * The challenge consists of an online phase (in simulation) followed by an in-person phase (with physical hardware)
  * The simulation environment uses models of real phantoms
  * The accuracy of the simulated robots is consistent with that of the physical robots
  * The stereo endoscope video in the physical setup is consistent with that of the simulated environment (i.e., will be higher quality)

In this challenge, we provide the specifications for multiple physical platforms that each consist of two
seven degrees-of-freedom (DOF) instrument arms based on the da Vinci Surgical System
large needle driver, a controllable stereo camera,
a suturing phantom, and a needle with suture.
Note that the stereo camera has higher quality than the stereo endoscope provided with
the first-generation da Vinci surgical system.
We also provide a simulation environment for each specified physical platform.
The goal is to conduct the first part of the challenge in simulation, followed by a sim-to-real transfer
on the physical platforms. The following video provides a "teaser" of the updated simulation environment.

<video width="640" height="360" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge-2023/Suturing-AMBF.mp4">
Your browser does not support the video tag.
</video>

## News

Stay tuned...

## Timeline

**October 30, 2022:**  Challenge prelaunch

**April 19, 2023:**  Presentation of challenge at [ISMR 2023 Workshop](https://collaborative-robotics.github.io/ismr-2023-workshop.html)

**December 2023:** Online challenge closes

**January 2024:** Physical (in-person) challenge

## Registration

Please register to participate in these challenges. This enables us to inform you about any important updates.

There are no restrictions on who can participate in this challenge. We expect most participants to be part of a team,
so it is only necessary for one person to register the team. If you wish, you can add the names of other participants in
the "Additional comments" box.

[Registration form]()

## Awards

TBD

## Results


## [System Setup]()

The challenge is based on the [Asynchronous Multi-Body Framework (AMBF)](https://github.com/WPI-AIM/ambf)
simulator. Participants will be required to install AMBF on a Linux system and download a Docker
container. Algorithms should be implemented within a Docker container and submitted for testing.
Additional details are provided [**here**]().

## [Submission Instructions]()

TBD

## Challenge Tasks

### Challenge 1: [Grasp needle with right instrument and move to first entry point](./challenge-1.md)

### Challenge 2: [Complete four running sutures using both instruments](./challenge-2.md)

### Contact

Please use the [GitHub Discussions forum](https://github.com/collaborative-robotics/surgical_robotics_challenge/discussions) for questions and comments. See the [Community page]() for more information.

To contact the organizers by email: [accelnet-robotics-challenge-admin@googlegroups.com](mailto:accelnet-robotics-challenge-admin@googlegroups.com)

### Acknowledgments

<p><img src="/images/NSF-logo.png" alt="NSF Logo" style="float:left; width:80px; height:80px; margin-right:25px">
Development of this Surgical Robotics Challenge is supported by the United States National Science Foundation (NSF)
via OISE-1927354 and OISE-1927275, <i>AccelNet: International Collaboration to Accelerate Research in Robotic Surgery</i>.</p>
