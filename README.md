# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
## Step5:
Use Otsu's method to segment the image and display the results.

## Program

```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread('profile.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('GATE.jpg',0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

#Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
# Display the results

for i in range(0,9):
    plt.figure(figsize=(10,10))
  
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image
![delhi-pl](https://github.com/user-attachments/assets/4b307b3a-fbab-400c-bed0-07c79730980d)
### Gray Image
![image](https://github.com/user-attachments/assets/a246c004-992f-4359-b859-4abb13ad637f)

### Global Thresholding
![image](https://github.com/user-attachments/assets/d5bffb30-01be-4d73-a2e3-119887de689f)
![image](https://github.com/user-attachments/assets/8c9b1fe6-4ce9-4ff5-a227-7d263c47c04a)
![image](https://github.com/user-attachments/assets/a4b4a8eb-0de5-4f60-8738-9a20780435c6)
![image](https://github.com/user-attachments/assets/e2b8a98c-567c-44ff-afac-a7f39ab4b152)

### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/35cef6b2-3a39-4928-bb3a-0f56bef797fa)
![image](https://github.com/user-attachments/assets/e4fca39e-7dca-43b6-a228-d8e00f2169d2)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/5e33e7f4-81c2-401a-a171-b0bad663fb67)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
