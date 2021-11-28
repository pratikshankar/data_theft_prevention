# Data Theft Prevention
This repo is about applying machine learning principles to prevent any person steal data from the screen by capturing a photo of the screen.
As soon as the system detects a cell phone pointed towards the screen it will create a screen blackout.
![Alt text](https://github.com/pratikshankar/data_theft_prevention/blob/master/Demo.gif)

## Requirements
This project uses the following dependencies:
* Python
* Numpy
* Opencv-python
* Pygame
* Yolo v3(tiny) Weights and Config file

## Object Detection Algorithm used
* [Yolo v3](https://arxiv.org/abs/1506.02640)

## Approach
* At first we take the input video feed from the webcam of the laptop.
* Using OpenCv-Python we split the income video frame by frame.
* After we get the frame we pass it to the YOLO algorithm wich detects if a cellphone is present in the frame
* If it detects a cellphone it uses Pygame module to create a black screen on top of the actual screen so that no one can click pictures of the screen.
* When the cellphone is not detected anymore the black screen is destroyed and the actual screen is visible again.



