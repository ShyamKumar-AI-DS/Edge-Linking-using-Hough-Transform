# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:Import all the necessary Python libraries which are required for the program.
<br>

### Step2:Load a image using imread() from cv2 module.
<br>

### Step3:Convert the image to grayscale.
<br>

### Step4:Using Canny operator from cv2,detect the edges of the image
<br>

### Step5:Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
<br>


## Program:
```
Name : Shyam Kumar A
Reg No : 212221230098
```
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('out.jpg',0)
plt.imshow(image1)
img= cv2.GaussianBlur(image1,(3,3),0)
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
    cv2.line(edges1,(x1, y1),(x2, y2),(255, 0, 0),3)


# Display the result

plt.imshow(edges1,'gray')


```
## Output

### Input image and grayscale image:


![](dip1.png)


### Canny Edge detector output:

![](dip2.png)


### Display the result of Hough transform:


![](dip3.png)




## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
