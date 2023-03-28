---
layout: default
---

# [ISMR 2023](http://www.ismr.gatech.edu/) Workshop: Hands-On Machine Learning in Simulation and Reality with the da Vinci Research Kit

**Workshop Date:**  April 19, 2023

**Venue:** Georgia Institute of Technology, Atlanta, GA USA

**Location:** TBD

## Objectives

The objective of this workshop is to advance the application of machine learning in robotic surgery. The primary application domain is the telesurgical approach exemplified in operating rooms by the da Vinci surgical system and in research labs by the da Vinci Research Kit (dVRK) and Raven II open platforms. The AccelNet Surgical Robotics Challenge represents one step toward this objective, specifically focusing on autonomous suturing in minimally-invasive surgery. The first iteration of this challenge was implemented in the Asynchronous Multi-Body Framework (AMBF) dynamic simulation environment and the second challenge includes both simulated and real environments.

The workshop will present the challenge infrastructure, including a hands-on session for the [AMBF simulator](https://github.com/WPI-AIM/ambf), the [Medical Open Network for Artificial Intelligence (MONAI)](https://monai.io/) (including nVidia Clara Holoscan), and the [da Vinci Research Kit (dVRK)](https://github.com/jhu-dvrk/sawIntuitiveResearchKit/wiki).

One goal is to build a worldwide collaboration focused on collection and sharing of data and algorithms for machine learning in robotic minimally-invasive surgery, from projects on similar topics funded by multiple national and international agencies, including NSF in the United States, ERC in the European Union and UGC in Hong Kong. The workshop will also provide a poster session for researchers to present their results in data-driven methods for scene perception, intelligent assistance, semi-autonomous teleoperation and surgical autonomy.

## Organizers

| Peter Kazanzides, Adnan Munawar    | Gregory S. Fischer              | Jie Ying Wu           |
|------------------------------------|---------------------------------|-----------------------|
| Johns Hopkins University           | Worcester Polytechnic Institute | Vanderbilt University |

## Tentative Program

Session 1:  Invited Talks (90 minutes)
  * Peter Kazanzides:  The da Vinci Research Kit and AccelNet Surgical Robotics Challenge
  * Adnan Munawar:  AMBF and the AccelNet Surgical Robotics Challenge
  * TBD:  MONAI:  Open source AI platform for medical imaging and devices
  * Animesh Garg:  Paving the path to surgical autonomy with simulation
  * Greg Fischer:  User studies, data collection, and learning from demonstration on the dVRK
  * Jie Ying Wu:  Machine learning with the dVRK

Session 2:  Hands-On Session and Poster Session, in parallel (90 minutes)
  * Tentative outline for hands-on session (see below for preparation):
    * Set up AMBF and MONAI segmentation network (hopefully in advance)
    * Evaluate performance of pre-trained network with AMBF simulator output
    * Collect training data in AMBF and re-train network (small number of epochs)
    * Evaluate performance of re-trained network with AMBF simulator output
    * Evaluate performance with dVRK images (sim-to-real)
    * If labeled dVRK images available, re-train network and re-evaluate

## Preparation for Hands-On Session

Attendees will have the opportunity to test out the [AMBF simulator](https://github.com/WPI-AIM/ambf),
[MONAI](https://monai.io/) and [dVRK](https://github.com/jhu-dvrk/sawIntuitiveResearchKit/wiki) during Session 2.
The following hardware will be available during the hands-on session:

  * nVidia Clara Holoscan AGX (Qty ?)
  * dVRK system
    * PSM-Si (Qty ?)
    * Endoscope
    * Suturing phantom
  * AMBF server (Qty ?)

Interested participants should set up their laptop prior to the workshop.

**NOTE: Do not follow these instructions yet. We will update by 3/31/23.**

There are two different ways to install AMBF on your machine:

  1. Install Ubuntu, ROS and AMBF:
   * a. **(Preferred)** Install Ubuntu 20.04 on your computer and install ROS [Noetic](http://wiki.ros.org/ROS/Installation). Then install AMBF based on these [instructions](https://github.com/WPI-AIM/ambf/blob/ambf-2.0/README.md).
   * b. If you instead prefer to use MacOS or a Windows computer, and do not wish to create a bootable Ubuntu partition, you can use the AMBF [docker](https://github.com/collaborative-robotics/docker-ambf) image and install it according to these [instructions](https://github.com/collaborative-robotics/docker-ambf). The performance of AMBF would be limited in this case.
  
  2. Clone the [surgical_robotics_challenge](https://github.com/collaborative-robotics/surgical_robotics_challenge) repo on the Linux OS from the first step.

## Resources

  * [Video playlist](https://www.youtube.com/playlist?list=PLtoSVSQ2XzyAJAGzaHF0nUIkav0BnxhrJ) for MONAI Bootcamp 2023
