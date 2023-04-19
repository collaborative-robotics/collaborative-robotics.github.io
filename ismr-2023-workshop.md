---
layout: default
---

# [ISMR 2023](http://www.ismr.gatech.edu/) Workshop: Hands-On Machine Learning in Simulation and Reality with the da Vinci Research Kit

**Workshop Date:**  April 19, 2023, 8:30 AM - 12:00 PM (half-day)

**Venue:** Georgia Institute of Technology, Atlanta, GA USA

**Location:** Marcus 1116

## Objectives

The objective of this workshop is to advance the application of machine learning in robotic surgery. The primary application domain is the telesurgical approach exemplified in operating rooms by the da Vinci surgical system and in research labs by the da Vinci Research Kit (dVRK) and Raven II open platforms. The AccelNet Surgical Robotics Challenge represents one step toward this objective, specifically focusing on autonomous suturing in minimally-invasive surgery.
The [first challenge (2021-2022)](https://collaborative-robotics.github.io/surgical-robotics-challenge/challenge-2021.html)
was implemented in the Asynchronous Multi-Body Framework (AMBF) dynamic simulation environment and the ongoing
[second challenge (2023-2024)](https://collaborative-robotics.github.io/surgical-robotics-challenge-2023/challenge-2023.html)
includes both simulated and real environments.

The workshop will present the challenge infrastructure, including a hands-on session for the [AMBF simulator](https://github.com/WPI-AIM/ambf), the [Medical Open Network for Artificial Intelligence (MONAI)](https://monai.io/), and the [da Vinci Research Kit (dVRK)](https://github.com/jhu-dvrk/sawIntuitiveResearchKit/wiki).

The following videos summarize the hands-on session, where partipants will learn how to capture video in the AMBF simulation environment (left), with corresponding ground truth labels, train a neural network to segment the instruments, needle and suture, and then run this network on video obtained from the simulation environment (right) as well as the physical dVRK.

| Video input to Network | Video output (segmentations) from Network |
|:----------------------:|:-----------------------------------------:|
| <img src='./images/InputVideo.gif' /> | <img src='./images/OutputVideo.gif' /> |

One goal is to build a worldwide collaboration focused on collection and sharing of data and algorithms for machine learning in robotic minimally-invasive surgery, from projects on similar topics funded by multiple national and international agencies, including NSF in the United States, ERC in the European Union and UGC in Hong Kong.

## Organizers

| Peter Kazanzides, Adnan Munawar    | Gregory S. Fischer              | Jie Ying Wu           |
|------------------------------------|---------------------------------|-----------------------|
| Johns Hopkins University           | Worcester Polytechnic Institute | Vanderbilt University |

## Tentative Program

**Session 1:**  Invited Talks, 8:30 - 10:00 AM (90 minutes)

| Time | Topic        | Speakers |
|:-----|:-------------|:---------|
| 8:30 | The da Vinci Research Kit and AccelNet Surgical Robotics Challenge | Peter Kazanzides, Juan Antonio Barragan (JHU) |
| 8:45 | AMBF and the Accelnet Surgical Robotics Challenge | Adnan Munawar (JHU) |
| 9:00 | MONAI and NVIDIA Holoscan + IGX for Realtime AI and Visualization in Medical Devices | Marc Edgar (nVidia) |
| 9:15 | Paving the path to surgical autonomy with simulation | Animesh Garg (Georgia Tech) |
| 9:30 | User studies, data collection, and learning from demonstration on the dVRK | Greg Fischer, Haoying Zhou (WPI) |
| 9:45 | Machine learning with the dVRK | Jie Ying Wu (Vanderbilt Univ.) |

**Coffee Break:**  10:00 - 10:30 AM (30 minutes)

**Session 2:**  Hands-On Session (and Poster Session), 10:30 AM - 12:00 PM (90 minutes)
  1. Verify installation of AMBF and Surgical Robotics Challenge (see **Preparation** below)
  2. Collect data in AMBF (video and ground-truth segmentations)
  3. Process data to obtain labeled images for neural network
  4. Upload data to Google drive, so that it is available in Google colab
  5. Set up MONAI in Google colab (links provided in Jupyter notebook)
  6. Train neural network in Google colab (links provided in Jupyter notebook)
  7. Run neural network (inferencing) with test data in Google colab (links provided in Jupyter notebook)
  8. Run neural network (inferencing) with dVRK images (sim-to-real)

## Community Poster Session

We will run a poster session during the coffee break and concurrently with the hands-on session.
Interested participants are invited to bring
their posters, as long as they are related to the workshop theme of machine learning in robotic surgery.
Relevant poster topics include data-driven methods for scene perception, intelligent assistance, semi-autonomous
teleoperation and surgical autonomy.

There is no submission or review process for posters, although we encourage attendees to let us know if they will
to bring a poster so that we can be sure to have enough poster stands. We currently plan to have approximately
10 poster stands in the room.

## Hands-On Session Overview

Attendees will have the opportunity to test out the [AMBF simulator](https://github.com/WPI-AIM/ambf),
[MONAI](https://monai.io/) and [dVRK](https://github.com/jhu-dvrk/sawIntuitiveResearchKit/wiki) during Session 2.
The following hardware will be available during the hands-on session:

  * dVRK system
    * PSM
    * Stereo camera
    * Suturing phantom

In addition, we will have an [nVidia Clara Holoscan AGX](https://www.nvidia.com/en-us/clara/medical-devices/)
and will run a demonstration application.

## Preparation for Hands-On Session

Interested participants should set up their laptop prior to the workshop.
We recommend installing ROS, AMBF and the Surgical Robotics Challenge, as described below.
In addition, participants should have a Google account so that the machine learning tasks
can be performed on the [Google colab](https://colab.research.google.com/) cloud server.

Preferred installation (on Ubuntu 20.04):

  1. Install ROS [Noetic](http://wiki.ros.org/ROS/Installation), if not already installed.
  2. Install AMBF based on these [instructions](https://github.com/WPI-AIM/ambf/blob/ambf-2.0/README.md).
  3. Clone the [surgical_robotics_challenge](https://github.com/collaborative-robotics/surgical_robotics_challenge) repository.

Participants who do not have Ubuntu 20.04 can instead use the AMBF [docker](https://github.com/collaborative-robotics/docker-ambf) image and install it according to these [instructions](https://github.com/collaborative-robotics/docker-ambf). The performance of AMBF would be limited in this case.

Advanced participants, with a good GPU, can skip Google colab and instead install PyTorch
and MONAI on their laptops.

## Resources

  * [Video playlist](https://www.youtube.com/playlist?list=PLtoSVSQ2XzyAJAGzaHF0nUIkav0BnxhrJ) for MONAI Bootcamp 2023
