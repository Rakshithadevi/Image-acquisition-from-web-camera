# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
```
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video
```

## Software Used
Anaconda - Python 3.7
## Algorithm
```
Step 1: Import cv2 and capture the video using cv2.VideoCapture(0)

Step 2: Write the captured image using cv2.imwrite("out.jpg",frame)

Step 3: Resize the image using cv2.resize() to get a four-split screen.

Step 4: Rotate the image using cv2.rotate(smaller_frame,cv2.ROTATE_180)

Step 5: Display the image until the key to close the window is pressed.
```

## Program:
Python
```
### Developed By:J RAKSHITHA DEVI
### Register No: 212221230082
```

## i) Write the frame as JPG file

```
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video_image.jpg',frame)
    cv2.imwrite("out.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
cv2.destroyAllWindows()
```




## ii) Display the video

```
import cv2
object=cv2.VideoCapture(0)
while(True):
    ret,frame=object.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1)==ord('q'):
        break
object.release()
cv2.destroyAllWindows()
```




## iii) Display the video by resizing the window

```
import numpy as np
import cv2
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```





## iv) Rotate and display the video

```
import numpy as np
import cv2
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame


    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```









## Output

### i) Write the frame as JPG image
![image](https://user-images.githubusercontent.com/94165326/226581923-29d10850-055a-4bbc-910c-736f3984ad52.png)




### ii) Display the video

![image](https://user-images.githubusercontent.com/94165326/226586188-f9559e9f-db98-44f4-891e-b2f3126fc4f1.png)



### iii) Display the video by resizing the window
![image](https://user-images.githubusercontent.com/94165326/226586502-c83c4b80-66ec-4ff1-ab67-e143c3569df2.png)



### iv) Rotate and display the video
![image](https://user-images.githubusercontent.com/94165326/226586632-ae89429a-9b21-4557-be68-e4fdc85da7cf.png)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
