# NFL 1st and Future - Impact Detection Competition
*Detect helmet impacts in videos of NFL plays*

## 1.00 Introduction
### 1.01 The Competition
The National Football League (NFL) has teamed up with Amazon Web Services (AWS) to develop the “Digital Athlete,” a virtual representation of a composite NFL player that the NFL can use to model game scenarios to try to better predict and prevent player injury. The NFL is actively addressing the need for a computer vision system to detect on-field helmet impacts as part of the “Digital Athlete” platform.

In this repository, we develop a computer vision model that automatically detects helmet impacts that occur on the field. We kick off with a dataset of more than one thousand definitive head impacts from thousands of game images, labeled video from the sidelines and end zones, and player tracking data. This information is sourced from the NFL’s Next Gen Stats (NGS) system, which documents the position, speed, acceleration, and orientation for every player on the field during NFL games.

This competition is part of the NFL’s annual 1st and Future competition, which is designed to spur innovation in athlete safety and performance. Successful participants could support the NFL’s research programs in a big way: improving athletes' safety. Backed by this research, the NFL may implement rule changes and helmet design improvements to try to better protect the athletes who play the game millions watch each week.

### 1.02 Evaluation
In this task, we segment helmet collisions in videos of football plays using bounding boxes. The competition is evaluated using a micro F1 score at an Intersection over Union (IoU) threshold of 0.35.

There are a few important differences from other bounding box metrics:

 1. The main departure from a traditional metric is that some imprecision on the timing of the impact is acceptable. For a given ground truth impact, a prediction within +/- 4 frames (9 frames total) within the same play can be accepted as valid without necessarily degrading the score. Assuming the player is moving over the course of those frames, the exact bounding box predicted to achieve an IoU of 1.0 would also vary depending on the frame.
 2. As one helmet may partially obscure another from the camera's perspective, both predicted and ground truth bounding boxes may overlap. However, at most one prediction will ever be assigned to a given ground truth box.
 3. The two criteria described above mean that one or more predictions could theoretically be assigned to more than one ground truth boxes. If this happens, our metric will optimize for the assignments between your prediction(s) and the ground truth boxes that lead to the highest total number of True Positives (thereby maximizing the F1 score). At most one prediction will be assigned to any ground truth box and vice versa.

The IoU of a proposed bounding box and a ground truth bounding box is calculated as:

<a href="https://www.codecogs.com/eqnedit.php?latex=IoU(A,B)&space;=&space;\frac{A&space;\cap&space;B}{&space;A&space;\cup&space;B}." target="_blank"><img src="https://latex.codecogs.com/svg.latex?IoU(A,B)&space;=&space;\frac{A&space;\cap&space;B}{&space;A&space;\cup&space;B}." title="IoU(A,B) = \frac{A \cap B}{ A \cup B}." /></a>

The metric treats any IoU of at least 0.35 as a true positive.

F1 is calculated as follows:

<a href="https://www.codecogs.com/eqnedit.php?latex=F_1&space;=&space;2&space;*&space;\frac{precision&space;*&space;recall}{precision&space;&plus;&space;recall}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?F_1&space;=&space;2&space;*&space;\frac{precision&space;*&space;recall}{precision&space;&plus;&space;recall}" title="F_1 = 2 * \frac{precision * recall}{precision + recall}" /></a>

where:

<a href="https://www.codecogs.com/eqnedit.php?latex=precision&space;=&space;\frac{TP}{TP&space;&plus;&space;FP}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?precision&space;=&space;\frac{TP}{TP&space;&plus;&space;FP}" title="precision = \frac{TP}{TP + FP}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=recall&space;=&space;\frac{TP}{TP&space;&plus;&space;FN}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?recall&space;=&space;\frac{TP}{TP&space;&plus;&space;FN}" title="recall = \frac{TP}{TP + FN}" /></a>

## 2.00 Repository

WILL UPDATE ONCE COMPETITION IS COMPLETE

## 3.00 Requirements

WILL UPDATE ONCE COMPETITION IS COMPLETE
