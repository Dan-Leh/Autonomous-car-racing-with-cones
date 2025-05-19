# Autonomous-car-racing-with-cones
In this repository, I share the report and presentation of my team's design of a system for autonomously racing a small-scale car, and I describe my role in the project.

Please find the [Report](https://drive.google.com/file/d/1rWZNW5TMAkuEV3pIUT0pYL6_9b_-Ks6X/view?usp=sharing) and [Presentation](https://docs.google.com/presentation/d/1RSqe1nYWGugPqaRepjg1uu-9szCLEMhJ/edit?usp=sharing&ouid=110775942767811403002&rtpof=true&sd=true) for this project for a complete overview of the system and video demonstrations.

## Overview of Perception Module
My role in the project consisted mostly in the design and software implementation of a perception system capable of mapping out a track and generating waypoints for the autonomous vehicle to race through using the [pure pursuit](https://www.ri.cmu.edu/pub_files/pub3/coulter_r_craig_1992_1/coulter_r_craig_1992_1.pdf) algorithm. Here is a very high level overview of the working system:

1. Contruct a racing track with two different colored cones for inner and outer track boundaries.
2. Manually drive robot through track (human RC driver) to scan the map and log each detection of a cone.
3. Use cone detection algorithm (YOLOv3 finetuned for cones, able to detect cone color).
4. Implement filtering techniques to reliably filter out false positive detections.
5. Extract "waypoints" from detected race track boundaries for autonomous agent to use as control reference.

