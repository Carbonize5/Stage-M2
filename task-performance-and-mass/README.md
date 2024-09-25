# Task Performance and Mass

## Description
The source code for a Fitts's Law experiment in VR with motion tracking on objects by Optitrack. 

## Visuals
![Use case](./project_visuals/Capture1.jpg)
![Targets' position on the table](./project_visuals/XPDesign_resize_contour.png)

## Installation
- Download and launch Unity Hub.
- Download and install Unity 2022.3.22f1 or higher.
- In Projects, select Add then select the folder were the project is.

## Libraries and third-party software
This project require :

- SteamVR and the Unity package (needs to be reinstall on fresh cloning),
- Unity OpenXR plugin and Unity XR Plugin Management,
- Optitrack Package for Unity

## Experimental Protocol

## Usage
When the project is launched, it starts with a training phase with infinite time. Press Space to start the experiment and to continue after changing the replica.

After each validate target, data are record in the Unity's Persistent Data Path under "Fitts/XPLogs/Logs.csv". Each data type is separated with ";".

## Authors and acknowledgment
Author : Lucas Thomesse [[mail](mailto:thomesse.lucas@outlook.fr)]
