---
layout: default
---

## Challenge 1: Grasp needle with right instrument and move to first entry point

### Task

Move large needle driver to grasp the needle and then move the needle tip to the target.
The accuracy of the simulated robot
will be comparable to that of a real robot and thus visual feedback would be required to ensure
accurate performance.

The needle should be grasped near its base (i.e., back third of needle) with the gripper orthogonal to
the plane of the needle. However, the evaluation metrics
do not consider the needle grasp pose, so any pose that produces successful results
is acceptable.

### Provided Data

1. Initial ground-truth pose of needle (if required)
2. Ground-truth poses of first target entry and exit on phantom

Note that the entry and exit points are specified as poses (transforms). See this
[figure](https://github.com/collaborative-robotics/surgical_robotics_challenge/blob/master/docs/scene_coordinate_frames.md#entry--exit-frames).

### Simulator Test Conditions

Each entry will be tested with multiple trials, where the needle position and
target positions will vary for each trial.
In addition, the robot position will include a realistic amount of error to emulate
the inaccuracy of a physical robot.
Stereo endoscope video will be provided at 1080p resolution at 30 fps.

### Physical Test Conditions

TBD

### Evaluation Metric

Entries will be judged based on the time the algorithm required to perform
the task and the achieved accuracy. Accuracy will be measured by the distance between the needle
trajectory and the target entry position.
User scripts should publish the specified ROS topic or call
the specified Python method to indicate task completion.
All entries must be within &plusmn;2.5 mm of the target entry.
Note that the squares surrounding the entry/exit points have dimensions
5 mm x 5 mm, so the needle tip must lie within this square.
All entries that pass the accuracy threshold will be ranked based on completion time.
Time will be measured from when the user script is started until the task completion message is received.
