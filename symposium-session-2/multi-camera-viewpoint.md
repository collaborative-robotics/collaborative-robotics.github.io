<div align="center"> <h2> Multicamera 3D Viewpoint Adjustment for Robotic Surgery via Deep Reinforcement Learning </h2> </div>

While robot-assisted minimally invasive surgery (RMIS) procedures afford a variety of benefits over open surgeon and manual laparoscopic operations (including increased tool dexterity, reduced patient pain, incision size, trauma and recovery time, and lower infection rates\[1\]), lack of spatial awareness remains an issue. Typical laparoscopic imaging can lack sufficient depth cues and haptic feedback, if provided, rarely reflects realistic tissue-tool interactions. The presented work is part of a larger ongoing research effort to reconstruct 3D surfaces using multiple viewpoints in RMIS to increase visual perception. The manual placement and adjustment of multi-camera systems in RMIS is non-ideal and prone to error\[2\], and other autonomous approaches focus on tool-tracking and do not consider reconstruction of the surgical scene\[3-5\]. The groups previous work investigated a novel, context-aware autonomous camera positioning method\[6\], which incorporated both tool location and scene coverage for multiple camera viewpoint adjustments. In this manuscript, the authors expand upon this prior work by implementing a streamlined deep reinforcement learning approach between optimal viewpoints calculated using the prior method\[6\] which encourages discovery of otherwise unobserved and additional camera viewpoints. Combining the framework and robustness of the previous work with the efficiency and additional viewpoints of the augmentations presented here results in improved performance and scene coverage promising towards real-time implementation.

### References:
\[1\] K. Fuchs, Minimally invasive surgery, Endoscopy 34(02) (2002) 154-159.

\[2\] A. Pandya, L. Reisner, B. King, N. Lucas, A. Composto, M. Klein and R. Ellis, A review of camera viewpoint automation in robotic and laparoscopic surgery, Robotics 3(3) (2014) 310-329.

\[3\] O. Weede, H. Moennich, B. Mueller and H. Woern, An intelligent and autonomous endoscopic guidance system for minimally invasive surgery, 2011 IEEE International Conference on Robotics and Automation, IEEE (2011), pp. 5762-5768.

\[4\] K.-T. Song and C.-J. Chen, Autonomous and stable tracking of endoscope instrument tools with monocular camera, 2012 IEEE/ASME International Conference on Advanced Intelligent Mechatronics (AIM), IEEE (2012), pp. 39-44.

\[5\] L. Yu, Z. Wang, L. Sun, W. Wang and T. Wang, A kinematics method of automatic visual window for laparoscopic minimally invasive surgical robotic system, 2013 IEEE International Conference on Mechatronics and Automation, IEEE (2013), pp. 997-1002.

\[6\] Y. H. Su, K. Huang and B. Hannaford, Multicamera 3d reconstruction of dynamic surgical cavities: Autonomous optimal camera viewpoint adjustment, Medical Robotics (ISMR), 2020 International Symposium on, IEEE (2020).
