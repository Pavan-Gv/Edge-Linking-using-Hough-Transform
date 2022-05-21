# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required modules.

### Step2:
Import the image to operate on.

### Step3:
Convert the imported image from BGR to GRAYSCALE.

### Step4:
Find the edges using canny edge detector and display the image.

### Step5:
Detect the points that form a line using hough transform.

### Step6:
Draw the lines on the image

### Step7:
Display the output

### Step8:
End the program.


## Program:
```Python
Developed by: G Venkata Pavan Kunmar
Registeration Number: 212221240013
# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np
image = cv2.imread("road.jpeg")
smoothImage = cv2.GaussianBlur(image,(3,3),0)
plt.imshow(smoothImage)
grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)




# Find the edges in the image using canny detector and display

cannyEdges = cv2.Canny(smoothImage,120,200)
plt.imshow(cannyEdges,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()


# Detect points that form a line using HoughLinesP

lines = cv2.HoughLinesP(cannyEdges,1,np.pi/180,threshold=80,minLineLength = 50,maxLineGap = 250)



# Draw lines on the image

for line in lines:
    x1, y1, x2, y2 = line [0]
    cv2.line(smoothImage,(x1, y1),(x2, y2),(255, 0, 0),3)



# Display the result
plt.title("Hough Transform")
plt.imshow(cannyEdges)
plt.show()

```
## Output

### Input image and grayscale image
![DIP9 1](https://user-images.githubusercontent.com/94827772/169645557-dfdbab1c-9e21-48ea-bdac-56bc59f7a279.png)

### Canny Edge detector output
![DIP9 2](https://user-images.githubusercontent.com/94827772/169645563-5fcf6b7b-31c8-4e24-babf-179a67d6338d.png)


### Display the result of Hough transform
![DIP9 3](https://user-images.githubusercontent.com/94827772/169645573-720f04f7-804d-4bf8-94d8-5952e6cd78b4.png)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
