---
layout: default
---

## System Setup

The challenge is based on the [Asynchronous Multi-Body Framework (AMBF)](https://github.com/WPI-AIM/ambf)
simulator, Version 2.0, along with the
[Surgical Robotics Challenge Assets](https://github.com/collaborative-robotics/surgical_robotics_challenge).
To install AMBF and the associated assets (including the launch file), follow the instructions
[here](https://github.com/collaborative-robotics/surgical_robotics_challenge).
Note that AMBF and the Assets should be installed directly on Linux, rather than within Docker.

The competition will be managed via Docker containers that contain Linux, ROS and Python scripts that use ROS to communicate
with AMBF running outside Docker. Information for setting up the Docker containers is provided
[here](https://github.com/collaborative-robotics/docker_surgical_robotics_challenge).
Competitors can choose the most convenient configuration from one of the two provided [Dockerfiles](https://github.com/collaborative-robotics/docker_surgical_robotics_challenge):
1. Ubuntu 18.04, ROS Melodic, and sample Python scripts.
2. Ubuntu 20.04, ROS Noetic, and sample Python scripts.

Challenge competitors should update the Dockerfile to install their files and submit it
for judging via a link to be provided.

## System Architecture

There are two supported system architectures, as illustrated below.
In both cases, user code obtains scene images from AMBF via ROS messages. Note that
only the endoscope stereo video (`sensor_msgs/Image`) will be provided during the
evaluation, but you are free to use the depth data (`sensor_msgs/PointCloud2`)
during development, for example, to provide ground truth data for training neural networks.

The difference between the two architectures below is how your user code interfaces to
the Surgical Robotics Challenge Assets (and ultimately AMBF), which can be via ROS (Option 1, recommended)
or via Python (Option 2). Note that there are two example script files (one for each option)
in the Challenge Assets, as indicated below. You can copy these script files to your
own workspace and rename/modify them as needed.

**Important:** Competitors should not rely on the implementation details of the AMBF Python Client
or the provided scripts, even though in Option 2, they will be located in the same Docker
container as the User Code. During the evaluation phase, these scripts will be replaced by
new versions. The reason for doing this is to prevent tactics such as writing software that
obtains the simulated robot kinematic error from the code.

### Option 1: ROS interface to Challenge Assets (recommended)

See [interface_via_crtk_ros_api.py](https://github.com/collaborative-robotics/surgical_robotics_challenge/blob/master/scripts/surgical_robotics_challenge/examples/interface_via_crtk_ros_api.py) example interface script.

![ROS Interface](./system-ros.svg)

### Option 2: Python interface to Challenge Assets

See [interface_via_method_api.py](https://github.com/collaborative-robotics/surgical_robotics_challenge/blob/master/scripts/surgical_robotics_challenge/examples/interface_via_method_api.py) example interface script.

![Python Interface](./system-python.svg)
