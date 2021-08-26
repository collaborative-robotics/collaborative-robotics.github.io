---
layout: default
---

# Challenge 3: Suture the phantom

##Task
Develop algorithms to drive the needle through the phantom from the first entry point to
the corresponding exit point. The left instrument should pull the needle through the phantom and
hand back the needle to the right instrument. This completes one suture. The algorithm should repeat
the entry and exit for each pair of points.  As in the previous challenges, the accuracy of the
simulated robot will be comparable to that of a real robot.

<video width="960" height="540" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge/task3_clip.mp4">
Your browser does not support the video tag.
</video>

##Provided Data
1. The positions of all entry and exit points on the phantom
2. Additional points to define the desired circular path between each entry and exit point
3. The starting pose between the needle and the (right) instrument

##Test Conditions
Test conditions will be the same as specified for Challenge 2, except that the
challenge will begin with the right instrument holding the needle in a correct grasp.

##Evaluation Metric
The evaluation metric will be the same as Challenge 2; specifically, all
entries that meet the specified accuracy thresholds will be ranked based on completion time.
