<div align="center"> <h2> Real-time Detection of Surgeon Stress Level During Laparoscopic Training </h2> </div>

<div align="center"> <h3> Yi Zheng, Grey Leonard, Ann Majewicz Fey </h3> </div>

### Introduction
Laparoscopic surgery is a new surgical technique which has the advantages of less large open wounds and less pain or
discomfort. It helps decrease the patient's recovery time. Surgical stress during the operation is commonly experienced by
the surgeons and has a negative effect on their surgical performance and patient safety. The purpose of this study is to find a
framework for a real-time and objective detection of the stress levels in conjunction with an assessment of performance using
the kinematic data.

### Method
30 medical students were recruited for the study and were randomized into control and stressed group. Each subject was
asked to complete a six-minute peg transfer drill on a simulation hardware (FLS trainer). The control group proceed while
hearing normal vital signs. The stress group performed under a period of progressively deteriorating vital signs with a
particular increase in intensity beginning at the three-minute mark. The moderator also simultaneously provided feedback
to the illusory anesthesiologist and nurse circulator of the increased danger of the dummy patient. The movement of hands
were recorded and streamed using electromagnetic trackers mounted on the handles of tools (3D positional data).

### Results
The data of control group was annotated as stress level 0. The data of the first and second halves of stressed group was
annotated as stress level 1 and 2, respectively. A LSTM Classifier was trained by using the recorded movement data to detect
the stress levels. The data was framed into 60-sample windows with a 50% overlap. We used the Leave-One-Participant-Out
cross-validation method (LOPO) to test the classifier and got an overall F1 score of 0.8630(0.011).

### Conclusion
This study showed the feasibility of using kinematic data to objectively detect the stress level experienced by the surgeons
during laparoscopic training. And the proposed method can serve as a groundwork for the stress detection in robotic surgical
training (da Vinci System) in which the kinematic data can be streamed directly.
