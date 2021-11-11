---
layout: default
---

# [ISMR 2021](http://www.ismr.gatech.edu/) Workshop on Data-Driven Methods for Robotic Minimally-Invasive Surgery

**Workshop Date:**  November 17, 2021

**Venue:** Georgia Institute of Technology, Atlanta, GA USA

**Location:** Marcus 1118

**UPDATE (11/11/21):** See Final Program

## Objectives

The objective of this workshop is to engage the international community interested in data-driven methods for robotic minimally-invasive surgery. The primary application domain is the telesurgical approach exemplified in operating rooms by the da Vinci surgical system and in research labs by the da Vinci Research Kit (dVRK) and Raven II open platforms. The workshop will present recent developments of infrastructure to support machine learning in robotic surgery, which includes physical infrastructure, such as phantoms, data collection infrastructure, and software environments, including simulators. One goal is to build a worldwide collaboration focused on collection and sharing of data and algorithms for machine learning in robotic minimally-invasive surgery, from projects on similar topics funded by multiple national and international agencies, including NSF in the United States, ERC in the European Union and UGC in Hong Kong. The workshop will also provide a forum for researchers to present their results in data-driven methods for scene perception, intelligent assistance, semi-autonomous teleoperation and surgical autonomy.

*This workshop was originally scheduled for ISMR 2020.*

## Hands-On Simulator Session

Attendees will have the opportunity to test out the [AMBF simulator](https://github.com/WPI-AIM/ambf) during Session 4.
Interested participants should set up their laptop prior to the workshop. There are two different ways to install AMBF on your machine:

  1. **(Preferred)** Install Ubuntu 18.04 or 20.04 on your computer and install the relevant ROS [version](http://wiki.ros.org/ROS/Installation). Then install AMBF based on these [instructions](https://github.com/WPI-AIM/ambf/blob/ambf-2.0/README.md).
  2. If you instead prefer to use MacOS or a Windows computer, and do not wish to create a bootable Ubuntu partition, you can use the AMBF [docker](https://github.com/collaborative-robotics/docker-ambf) image and install it according to these [instructions](https://github.com/collaborative-robotics/docker-ambf). The performance of AMBF would be limited in this case.

The agenda for this session is as follows:

  1. Introduction to AMBF 2.0 (last presentation in Session 3)
  2. Creating robots and environments using the [Blender-AMBF Addon](https://github.com/WPI-AIM/ambf_addon)
  3. Application: Interfacing AMBF with RBDL for creating dynamic controllers
  4. Controlling robots and acquiring scene data from the [surgical robotics challenge environment](https://github.com/collaborative-robotics/surgical_robotics_challenge)
  5. QnA/Wrapup.

## Organizers

|Peter Kazanzides          | Blake Hannaford           | Gregory S. Fischer              |
|--------------------------|---------------------------|---------------------------------|
|Johns Hopkins University  | University of Washington  | Worcester Polytechnic Institute |

|Michael Yip                    | Paolo Fiorini         |
|-------------------------------|-----------------------|
|Univ. of California, San Diego | University of Verona  |

## Final Program

| Time  | Topic        | Speakers |
|:------|:-------------|:---------|
| 08:30 | Welcome and Workshop Overview | Peter Kazanzides (JHU) |
| 08:40 | **Session 1** | |
| 08:40 | Infrastructure for Machine Learning in Minimally-Invasive Robotic Surgery | Peter Kazanzides (JHU) |
| 09:00 | Collaborative Robotics Toolkit (CRTK): Open Software Framework for Surgical Robotics Research | Melody Su (UW) |
| 09:20 | Autonomous Robotic Suction for Hemostasis | Florian Richter (UCSD) |
| 09:40 | Cognitive Surgical Robots: Theoretical Background and Initial Experiments | Paolo Fiorini (Univ. of Verona) |
| 10:00 | Coffee Break | | |
| 10:30 | **Session 2** | |
| 10:30 | Data-Driven Error Correction for Soft-Tissue Simulations | Jie Ying Wu (JHU) |
| 10:50 | Learning Robotic Suturing from Human Demonstration | Kim Lindberg Schwaner (Univ. of Southern Denmark) |
| 11:10 | Segmentation and Tracking of Endoscopic and Microscopic Surgical Instruments | Niveditha Kalavakonda (Univ. of Washington) |
| 11:30 | Data-Driven Detection of Executional Errors in Robot-Assisted Surgery | Homa Alemzadeh (Univ. of Virginia) |
| 11:50 | Session wrapup/discussion
| 12:00 | Lunch | | |
| 13:30 | **Session 3** | |
| 13:30 | Deep Learning for Calibration and Control in Robot-Assisted Surgery | Ken Goldberg, Daniel Seita, Minho Hwang or Brijen Thananjeyan (Univ. of California, Berkeley) |
| 13:50 | Data-Driven Online Learning and Manipulation of Unmodeled Deformable Tissues and Continuum Robots | Farshid Alambeigi (Univ. of Texas, Austin) |
| 14:10 | Surgical Simulators to Support Machine Learning | Farid Tavakkolmoghaddam, Greg Fischer (WPI) |
| 14:30 | Introduction to AMBF 2.0 | Adnan Munawar (JHU) |
| 14:50 | Preparation for Hands-On Session |
| 15:00 | Coffee Break | |
| 15:30 | **Session 4: AMBF Simulator Hands-On Tutorial** | |
| 15:30 | Creating robots and environments with Blender-AMBF Addon | Adnan Munawar (JHU) |
| 16:00 | Creating dynamic controllers with AMBF and RBDL | Farid Tavakkolmoghaddam (WPI) |
| 16:20 | Sensing and control in the surgical robotics challenge environment | Adnan Munawar (JHU) |
| 17:00 | Adjourn | | |
