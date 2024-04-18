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

### Step5:
Use Otsu's method to segment the image and display the results.

## PROGRAM
### Developed By : T MOUNISH
### Register Number : 212223240098


### Load the necessary packages
python
import numpy as np
import matplotlib.pyplot as plt
import cv2

### Read the Image and convert to grayscale
python
image = cv2.imread('pandaa.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('pandaa.jpg',0)

### Use Global thresholding to segment the image
python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

### Use Adaptive thresholding to segment the image
python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

### Use Otsu's method to segment the image 
python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

### Display the results
python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
### OUTPUT

### Original Image
![image](https://github.com/Abburehan/THRESHOLDING-/assets/138849336/009e880c-ab2a-44b4-93e5-7ad3e3af2b6d)

### Global Thresholding
![image](https://github.com/Abburehan/THRESHOLDING-/assets/138849336/b5eaa350-fa5c-4740-ad6c-3671cfd70feb)
![image](https://github.com/Abburehan/THRESHOLDING-/assets/138849336/5922edf8-f313-4178-b0f8-167ffae61f22)
![image](https://github.com/Abburehan/THRESHOLDING-/assets/138849336/7d08afab-6690-4d57-91f2-d4a6acad9ed3)
![image](https://github.com/Abburehan/THRESHOLDING-/assets/138849336/1090f843-04c5-438b-ae32-3f2205b305fc)
![image](https://github.com/Abburehan/THRESHOLDING-/assets/138849336/0e3bc534-c08f-4d46-849a-6a7913044851)


### Adaptive Thresholding
![image](https://github.com/Abburehan/THRESHOLDING-/assets/138849336/d3469580-fe9a-4852-b3c2-fc30c1d23756)
![image](https://github.com/Abburehan/THRESHOLDING-/assets/138849336/a73b2fcc-55bd-4b10-84f2-402bd05d0770)



### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Abburehan/THRESHOLDING-/assets/138849336/446564d1-e41c-4f4c-9f8c-2a654fe7ec99)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
