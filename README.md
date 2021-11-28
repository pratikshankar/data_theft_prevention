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

```python
cap=cv2.VideoCapture(0)

```
* Using OpenCv-Python we split the income video frame by frame.

```python
while(True):
    _,frame= cap.read()
   print("frame captured")
   frame_id+=1

```
* After we get the frame we pass it to the YOLO algorithm wich detects if a cellphone is present in the frame

``` python
camera_detection.is_camera_present(frame,frame_id) 

```
* If it detects a cellphone it uses Pygame module to create a black screen on top of the actual screen so that no one can click pictures of the screen.
``` python
if(camera_detection.is_camera_present(frame,frame_id)):
        print("detection unit called")
        black()
        def black():
        i=0
        screen=pygame.display.set_mode(size,pygame.FULLSCREEN,pygame.RESIZABLE)
        print("display=",(i+1))
         
```

* When the cellphone is not detected anymore the black screen is destroyed and the actual screen is visible again.
``` python
else:
      print("not detected")
      pygame.quit()
 
```



