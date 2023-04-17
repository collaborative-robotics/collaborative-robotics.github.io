---
layout: default
---

# [ISMR 2023](http://www.ismr.gatech.edu/) Workshop: Hands-On Machine Learning in Simulation and Reality with the da Vinci Research Kit

**Workshop Date:**  April 19, 2023, 8:30 AM - 12:00 PM (half-day)

**Venue:** Georgia Institute of Technology, Atlanta, GA USA

**Location:** Marcus 1116

## Objectives

The objective of this workshop is to advance the application of machine learning in robotic surgery. The primary application domain is the telesurgical approach exemplified in operating rooms by the da Vinci surgical system and in research labs by the da Vinci Research Kit (dVRK) and Raven II open platforms. The AccelNet Surgical Robotics Challenge represents one step toward this objective, specifically focusing on autonomous suturing in minimally-invasive surgery. The first iteration of this challenge was implemented in the Asynchronous Multi-Body Framework (AMBF) dynamic simulation environment and the second challenge includes both simulated and real environments.

The workshop will present the challenge infrastructure, including a hands-on session for the [AMBF simulator](https://github.com/WPI-AIM/ambf), the [Medical Open Network for Artificial Intelligence (MONAI)](https://monai.io/) (including nVidia Clara Holoscan), and the [da Vinci Research Kit (dVRK)](https://github.com/jhu-dvrk/sawIntuitiveResearchKit/wiki).

The following videos summarize the hands-on session, where partipants will learn how to capture video in the AMBF simulation environment (left), with corresponding ground truth labels, train a neural network to segment the instrument, needle and suture, and then run this network on video obtained from the simulation environment (right) as well as the physical dVRK.

| Video input to Network | Video output (segmentations) from Network |
|:----------------------:|:-----------------------------------------:|
|<img src='./images/InputVideo.gif'  width=200/> | <img src='./images/OutputVideo.gif' width=200/> |

One goal is to build a worldwide collaboration focused on collection and sharing of data and algorithms for machine learning in robotic minimally-invasive surgery, from projects on similar topics funded by multiple national and international agencies, including NSF in the United States, ERC in the European Union and UGC in Hong Kong.

## Organizers

| Peter Kazanzides, Adnan Munawar    | Gregory S. Fischer              | Jie Ying Wu           |
|------------------------------------|---------------------------------|-----------------------|
| Johns Hopkins University           | Worcester Polytechnic Institute | Vanderbilt University |

## Tentative Program

Session 1:  Invited Talks, 8:30 - 10:00 AM (90 minutes)

| Time  | Topic        | Speakers |
|:------|:-------------|:---------|
| 08:30 | The da Vinci Research Kit and AccelNet Surgical Robotics Challenge | Peter Kazanzides (JHU) |
| 08:50 | AMBF and the Accelnet Surgical Robotics Challenge | Adnan Munawar (JHU) |
| 09:10 | MONAI:  Open source AI platform for medical imaging and devices | Marc Edgar (nVidia) |
| 09:30 | Paving the path to surgical autonomy with simulation | Animesh Garg (Georgia Tech) |
| 09:50 | User studies, data collection, and learning from demonstration on the dVRK | Greg Fischer (WPI) |
| 10:10 | Machine learning with the dVRK | Jie Ying Wu (Vanderbilt Univ.) |

Coffee Break:  10:00 - 10:30 AM (30 minutes)

Session 2:  Hands-On Session (and Poster Session), 10:30 AM - 12:00 PM (90 minutes)
  * Set up AMBF and MONAI segmentation network (hopefully in advance)
  * Evaluate performance of pre-trained network with AMBF simulator output
  * Collect training data in AMBF and re-train network (small number of epochs)
  * Evaluate performance of re-trained network with AMBF simulator output
  * Evaluate performance with dVRK images (sim-to-real)
  * If labeled dVRK images available, re-train network and re-evaluate

## Community Poster Session

We will run a poster session during the coffee break and concurrently with the hands-on session.
Interested participants are invited to bring
their posters, as long as they are related to the workshop theme of machine learning in robotic surgery.
Relevant poster topics include data-driven methods for scene perception, intelligent assistance, semi-autonomous
teleoperation and surgical autonomy.

There is no submission or review process for posters, although we encourage attendees to let us know if they will
to bring a poster so that we can be sure to have enough poster stands. We currently plan to have approximately
10 poster stands in the room.

## Preparation for Hands-On Session

Attendees will have the opportunity to test out the [AMBF simulator](https://github.com/WPI-AIM/ambf),
[MONAI](https://monai.io/) and [dVRK](https://github.com/jhu-dvrk/sawIntuitiveResearchKit/wiki) during Session 2.
The following hardware will be available during the hands-on session:

  * AMBF server
  * dVRK system
    * PSM
    * PSM-Si
    * Stereo Camera
    * Suturing phantom
  * nVidia Clara Holoscan AGX

Interested participants should set up their laptop prior to the workshop.

There are two different ways to install AMBF on your machine:

  1. Install Ubuntu, ROS and AMBF:
   * a. **(Preferred)** Install Ubuntu 20.04 on your computer and install ROS [Noetic](http://wiki.ros.org/ROS/Installation). Then install AMBF based on these [instructions](https://github.com/WPI-AIM/ambf/blob/ambf-2.0/README.md).
   * b. If you instead prefer to use MacOS or a Windows computer, and do not wish to create a bootable Ubuntu partition, you can use the AMBF [docker](https://github.com/collaborative-robotics/docker-ambf) image and install it according to these [instructions](https://github.com/collaborative-robotics/docker-ambf). The performance of AMBF would be limited in this case.
  
  2. Clone the [surgical_robotics_challenge](https://github.com/collaborative-robotics/surgical_robotics_challenge) repo on the Linux OS from the first step.

  3. Install MONAI (instructions TBA)

## Resources

  * [Video playlist](https://www.youtube.com/playlist?list=PLtoSVSQ2XzyAJAGzaHF0nUIkav0BnxhrJ) for MONAI Bootcamp 2023
