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
<br>
Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:
<br>
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)



### Step 3:
<br>
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)



### Step 4:
<br>
Display the image until the loop gets over



### Step 5:
<br>
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)





## Program:

### Developed By: Eluru Ganesh
### Register No:212220230016

## i) Write the frame as JPG file
```python
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imwrite("ganesh.jpg",frame)
```




## ii) Display the video
```python
import cv2
import numpy as np

cap = cv2.VideoCapture(0)


while True:
    ret, frame = cap.read()

    cv2.imshow("NewPicture",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

videoCaptureObject.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```python
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
```

## iv) Rotate and display the video
```python
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

![Image](https://github.com/Ganesh517/Image-acquisition-from-web-camera/blob/main/1.jpg.jfif)



### ii) Display the video
![image](https://github.com/Ganesh517/Image-acquisition-from-web-camera/blob/main/2.jpg.jfif)


### iii) Display the video by resizing the window
![image](https://github.com/Ganesh517/Image-acquisition-from-web-camera/blob/main/3.jpg.jfif)



### iv) Rotate and display the video
![image](https://github.com/Ganesh517/Image-acquisition-from-web-camera/blob/main/4.jpg.jfif)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
