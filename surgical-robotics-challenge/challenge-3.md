---
layout: default
---

## Challenge 3: Suture the phantom

### Task

Develop algorithms to drive the needle through the phantom from the first entry point to
the corresponding exit point. The left instrument should pull the needle through the phantom and
hand back the needle to the right instrument. This completes one suture. The algorithm should repeat
the entry and exit for each pair of points.  As in the previous challenges, the accuracy of the
simulated robot will be comparable to that of a real robot.

<video width="960" height="540" autoplay muted loop>
  <source type="video/mp4" src="/surgical-robotics-challenge/task3_clip.mp4">
Your browser does not support the video tag.
</video>

### Provided Data

1. The poses of all entry and exit points on the phantom (see [Challenge 2](./challenge-2.md) for more information)
2. The starting pose between the needle and the (right) instrument

### Test Conditions

Test conditions will be the same as specified for [Challenge 2](./challenge-2.md), except that the
challenge will begin with the right instrument holding the needle in a correct grasp. Note that
it is necessary to call the `task_3_setup_init` method or publish the `task_3_setup/init` ROS topic
to place the needle in the right instrument.

### Evaluation Metric

The evaluation metric will be the same as [Challenge 2](./challenge-2.md); specifically, all
entries that meet the specified accuracy thresholds will be ranked based on completion time.
Time will be measured from when the user script is started until the task completion message is received.

The [evaluation script](https://github.com/collaborative-robotics/surgical_robotics_challenge/blob/master/scripts/surgical_robotics_challenge/evaluation/evaluation.py) for this challenge is in the GitHub repository and can be run as follows (use `python` or `python3` as appropriate):

```
python evaluation.py -t <team_name> -e 3
```

See also the [GitHub Discussions forum](https://github.com/collaborative-robotics/surgical_robotics_challenge/discussions/50).
