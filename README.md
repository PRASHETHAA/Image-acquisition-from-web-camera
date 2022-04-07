# Image-Acquisition-from-Web-Camera
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
### Step 1:
Use VideoCapture(0) to access web camera

### Step 2:
Use imread to read the video or image

### Step 3:
Use imwrite to save the image

### Step 4:
Use imshow to show the video

### Step 5:
End the program and close the output video windows by pressing 'q'.

## Program:
``` Python
### Developed By: PRASHEETHA
### Register No: 212220230036

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow("apple.jpg",frame)
    result = False
    if cv2.waitKey(1) == ord('q'): 
        break
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('q'): 
        break
cap.release()
cv2.destroyAllWindows()





## iii) Display the video by resizing the window

import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()






## iv) Rotate and display the video

import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()





```
## Output

### i) Write the frame as JPG image

![Screenshot (185)](https://user-images.githubusercontent.com/75234942/162216474-75749115-67dc-4f34-8072-7f44db583173.png)


### ii) Display the video

![Screenshot (186)](https://user-images.githubusercontent.com/75234942/162216665-9f2c534e-6918-48bb-b551-ec37c885e26f.png)


### iii) Display the video by resizing the window

![Screenshot (189)](https://user-images.githubusercontent.com/75234942/162216681-b5deef8c-4ad7-4cc8-9084-1342dc8e90d9.png)


### iv) Rotate and display the video

![Screenshot (191)](https://user-images.githubusercontent.com/75234942/162216691-0c88c3fc-66e3-4135-8024-6a35f71eb1a4.png)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
