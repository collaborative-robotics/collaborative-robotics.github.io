---
layout: default
---

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

