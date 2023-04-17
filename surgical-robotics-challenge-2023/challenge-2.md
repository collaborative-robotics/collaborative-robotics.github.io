---
layout: default
---

## Challenge 2: Complete four running sutures using both instruments

### Task

Develop algorithms to drive the needle through the phantom from the first entry point to
the corresponding exit point. The left instrument should pull the needle through the phantom and
hand back the needle to the right instrument. This completes one suture. The algorithm should repeat
the entry and exit for each pair of points.  As in the previous challenge, the accuracy of the
simulated robot will be comparable to that of a real robot.

### Provided Data

1. The poses of all entry and exit points on the phantom
2. The starting pose between the needle and the (right) instrument

### Simulator Test Conditions

Test conditions will be the same as specified for [Challenge 1](./challenge-1.md), except that the
challenge will begin with the right instrument holding the needle in a correct grasp.

### Physical Test Conditions

TBD

### Evaluation Metric

The evaluation metric will be the same as [Challenge 1](./challenge-1.md); specifically, all
entries that meet the specified accuracy thresholds will be ranked based on completion time.
Time will be measured from when the user script is started until the task completion message is received.
