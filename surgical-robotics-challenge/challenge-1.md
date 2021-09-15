---
layout: default
---

## Challenge 1: Finding the needle

### Task

Develop algorithms to identify the pose (position and orientation) of the metallic suture
needle, with respect to the current endoscope pose.

<video width="960" height="540" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge/task1_clip.mp4">
Your browser does not support the video tag.
</video>

### Provided Data

1. 3D model of needle (part of AMBF scene)
2. Camera calibration
3. Competitors must generate their own training data (if needed)

### Test Conditions

Each entry will be tested with different views of the surgical scene, with the
needle in different locations. The entire needle will be in the field-of-view. One or two
instruments may be present in the scene but will not overlap with the needle. The needle will be
located between 80 mm and 200 mm from the endoscope. Lighting can vary as specified above.
Stereo endoscope video will be provided at 1080p resolution at 30 fps.


### Evaluation Metric

Entries will be evaluated on the time to find the pose estimate and the
difference between the estimated pose and the ground truth. All algorithms must output a needle
pose within 10 seconds. The pose difference will be determined by the distance between three fixed
points on the needle: tip, middle and end. All entries that meet the time requirement will be
ranked by the sum of the three distance errors.

### Variations

Algorithms may move the camera to better identify the needle pose. Note, however,
that the simulator will add a realistic amount of error to the measurement of camera pose. Also,
moving the camera will increase the time required to find the needle and will count toward the 10
second time limit.
