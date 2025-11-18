# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

## Program:


import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('Tiger.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

<img width="642" height="478" alt="image" src="https://github.com/user-attachments/assets/b709dd0d-b86a-49de-8d3b-c9fc332145d0" />


### SOBEL EDGE DETECTOR

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

<img width="642" height="477" alt="image" src="https://github.com/user-attachments/assets/1921eeb6-619c-45c2-a554-9a8511da3358" />

### LAPLACIAN EDGE DETECTOR

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

<img width="642" height="478" alt="image" src="https://github.com/user-attachments/assets/8337c611-a6bb-45d7-9357-30c12943a1a5" />


### CANNY EDGE DETECTOR

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  

<img width="641" height="477" alt="image" src="https://github.com/user-attachments/assets/badbeb6f-3590-4fb2-9b69-37832f0a34f3" />

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
