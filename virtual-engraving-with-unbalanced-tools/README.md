# Virtual engraving with unbalanced tools

## Description
This project aims to see if the balance of a tool replica in a virtual environment have an effect on user performance during a letter engraving job. For this, users will use a tool replica with a variation in its balance and the virtual tool will have a fake camera attached to the model to indicate an unbalanced state.

## Visuals
![Training Mode](./project_visuals/training.png)
![Experiment Mode](./project_visuals/experiment.png)
![Training Mode but the letter I is dug](./project_visuals/digging2.png)
![The letter I is dug (zoom)](./project_visuals/digging1.png)

## Installation
- Download and launch Unity Hub.
- Download and install Unity 2020.3.48f1.
- In Projects, select Add then select the folder were the project is.

## Libraries and third-party software
This project require :

- Unity 2020.3.48f1.
- SteamVR Unity package (needs to be reinstall on fresh cloning),
- Unity XR Plugin Management,
- Optitrack Package for Unity

## Calibrate the Optitrack system
- Don't wear things with reflective surfaces or hide it.
- In the calibration tab on Motive (Optitrack Software) click on Clear Mask then on Mask Visible. If there are too many red dots on cameras' screens, the calibration won't be great. If it's the case, try to limit exposures.
- Assemble the wand and click the Start Wanding button when you are ready.
- Move the head of the wand in every corner of the room and try to cover most of the cameras' angles. Try to get a minimum of 1000 images by camera.
- Click on the Calculate button when you have finished.
- Put the wand away from the cameras and save the result. If it takes more than 5 minutes or the result is less than "Great", close and restart Motive then restart the calibration.
- Put the triangle in the centre of the room (the Z axis been the same as the one in Unity).
- Correct the levels on the triangle if needed. Check its height and apply it in Motive if it is different.
- Remove the triangle from the cameras
- The system is fully calibrated

## Optitrack room setup for a Unity project
- On Motive check that the IP address in the streaming tab is set on a fixed address not loopback.
- Download and install Optitrack OpenVR plugin.
- Download and install Steam and SteamVR.
- Check if the PC you put the project on is on the same network as the Motive PC.
- In the plugin window, add Motive's IP address and that of your PC.
- Tick the box for the headset and add the ID of the tracked headset, which can be found in the asset tab in Motive.
- Press the save button on the plugin window.
- Launch SteamVR.
- Press the retry button on the plugin window.
- If the T symbol doesn't blink on SteamVR, that means SteamVR communicate with Motive and you can launch the project.

## Problem & Answer
P: The tool model is constantly in the camera view and doesn't follow the tool replica.

A: On Motive, disable and re-enable the tracking of the tool in the asset tab. If the Unity script lost tracking information, it will give a default position instead.

P: My SteamVR window doesn't find Optitrack, the T symbol is still blinking.

A: Close SteamVR and restart it, then press the retry button in the plugin window. I still don't know why, but sometimes SteamVR doesn't find Optitrack, but both are linked to the plugin and the retry button is blocked. If it still can't find Optitrack, check that your PC and the Motive PC are on the same network.

## Commands in this project
**Space bar**: When the back of the tool replica is on a base press "Space" to quit Training Mode to start the experiment. It's the same when the user finished engraving the letter to enter a 30s break time or the unlimited break time after engraving all letters by also pressing "Space".

**Retry button**: During the experiment, the block will regenerate itself when pressing "Space" to do the next step. However, in Training Mode, users don't have time restriction so they can reset the block by colliding the back of the tool with the retry button.

## Authors and acknowledgment
Former Author : Lucas Thomesse \[[mail](mailto:thomesse.lucas@outlook.fr)\]

This project is an extension of Julien Cauquis's work. \[[mail1](mailto:julien.cauquis@imt-atlantique.fr)\] \[[mail2](mailto:julien.cauquis@clarte-lab.fr)\]

The Marching Cubes algorithm is from this repository \[[link](https://github.com/Scrawk/Marching-Cubes-On-The-GPU)\]

## Project status
What's left for this project is to add a system to collect users' data related to the block with the letter engraved into a CSV file.

One way is to find points on the block and take their distance from planes. That way, we can find the depth dug and users' overflow by matching plane orientation and position with the letter.

This project can be updated to Unity 2022, but some functions are deprecated, like Graphics.DrawProcedural().