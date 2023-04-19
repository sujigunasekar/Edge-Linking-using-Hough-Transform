# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step1:

Import all the necessary modules for the program.
## Step2:

Load a image using imread() from cv2 module.
## Step3:

Convert the image to grayscale.
## Step4:

Using Canny operator from cv2,detect the edges of the image
## Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.

## Program:
```Python

# Read image and convert it to grayscale image

import cv2
import numpy as np
import matplotlib.pyplot as plt
BGR_image=cv2.imread('s.png')
gray=cv2.cvtColor(BGR_image,cv2.COLOR_BGR2GRAY)
img= cv2.GaussianBlur(BGR_image,(3,3),0)
plt.imshow(img)


# Find the edges in the image using canny detector and display

edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)



# Draw lines on the image

for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(BGR_image,(x1, y1),(x2, y2),(250,0,150),2)


# Display the result

plt.axis('off')
plt.imshow(BGR_image)



```
## Output

### Input image and grayscale image

![Screenshot from 2023-04-19 14-25-47](https://user-images.githubusercontent.com/119559822/233023921-69b8b54f-a230-45b0-bf81-1cee4c78d357.png)

### Canny Edge detector output
![Screenshot from 2023-04-19 14-25-58](https://user-images.githubusercontent.com/119559822/233024025-a287429e-1c1f-4022-8e34-c65006c296b7.png)




### Display the result of Hough transform
![Screenshot from 2023-04-19 14-26-07](https://user-images.githubusercontent.com/119559822/233024101-777a9903-e181-4b20-8013-a8b81a5ef6b7.png)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
