---
layout: default
---

# Challenge 2: Grasp needle and drive through tissue

##Task
Move large needle driver to grasp the needle and then move the needle tip to the target
and drive the needle through the tissue until the tip exits. The accuracy of the simulated robot
will be comparable to that of a real robot and thus visual feedback would be required to ensure
accurate performance.

<video width="960" height="540" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge/task2_clip.mp4">
Your browser does not support the video tag.
</video>

##Provided Data
1. Ground-truth pose of needle
2. Ground-truth position of first target entry and exit on phantom
3. Target pose for grasping needle (i.e., relative pose between PSM gripper and needle)

##Test Conditions
Each entry will be tested with multiple trials, where the needle position and
target positions will vary for each trial. In addition, the kinematic parameters of the robot will
vary from the nominal values to emulate robot inaccuracy. Specifically, the simulator will use the
nominal kinematic parameters for inverse kinematics (e.g., to convert Cartesian goals into joint
goals), but then will use the perturbed kinematic parameters in the forward kinematics to compute
the Cartesian trajectory of the simulated robot. For some trials, the kinematic parameters will
have little or no error, thereby allowing the task to be completed without visual feedback,
whereas for other trials, visual feedback will be necessary to successfully complete the task.

#Evaluation Metric
Entries will be judged based on the time the algorithm required to perform
the task and the achieved accuracy. Accuracy will be measured by the distance between the needle
trajectory and the target entry and exit positions, and the amount of needle that is visible
beyond the exit point. All entries must be within *TBD (5 mm?)* of the target entry/exit and at
least *TBD (5 mm?)* of the neele tip must be visible. All entries that pass the accuracy threshold
will be ranked based on completion time.

