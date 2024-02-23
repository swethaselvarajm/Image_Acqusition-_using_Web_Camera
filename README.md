# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
## Step 1:
Import cv2 and capture the viedo using cv2.ViedoCapture(0).

## Step 2:
Write the capture image using cv2.imwrite("NewPicture.jpg",frame).

## Step 3:
Resize the image using cv2.resize(frame,(0,0),fx=0.5,fy=0.5).

## Step 4:
Display the image until the loop gets over.

## Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.ROTATE_180).

## Program:
``` Python
### Developed By: SWETHA.S
### Register No: 212222230155

## i) Write the frame as JPG file
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("swetha.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()

## ii) Display the video
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('ironman',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iii) Display the video by resizing the window
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230155_swetha',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230155_swetha',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![image](https://github.com/swethaselvarajm/Image_Acqusition-_using_Web_Camera/assets/119525603/67d0e7ba-6ba1-48ff-b8d6-3b959e6b7749)

### ii) Display the video
![image](https://github.com/swethaselvarajm/Image_Acqusition-_using_Web_Camera/assets/119525603/6d976c3a-c8bb-46b7-b07d-c3a973361a30)

### iii) Display the video by resizing the window
![image](https://github.com/swethaselvarajm/Image_Acqusition-_using_Web_Camera/assets/119525603/6150bb5b-e49e-4e27-bbac-ca816bd9ea41)

### iv) Rotate and display the video
![Screenshot 2024-02-23 220321](https://github.com/swethaselvarajm/Image_Acqusition-_using_Web_Camera/assets/119525603/cff1370e-b5e8-43d0-a5c2-cdf218772d28)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
