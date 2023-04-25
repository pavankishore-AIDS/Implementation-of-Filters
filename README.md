# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the necessary modules.

### Step2
For performing smoothing operation on a image.
1.	Average filter
kernel=np.ones((11,11),np.float32)/121
image3=cv2.filter2D(image2,-1,kernel)
2.	Weighted average filter
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
3.	Gaussian Blur
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
4.	Median filter
median=cv2.medianBlur(image2,13)


### Step3
For performing sharpening on a image.
1.	Laplacian Kernel
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
2.	Laplacian Operator
laplacian=cv2.Laplacian(image2,cv2.CV_64F)


### Step4
Display all the images with their respective filters.

## Program:
### Developed By   : M.Pavan Kishore
### Register Number: 212221230076

```python
import cv2
import numpy as np
image = cv2.imread("rin.jpg")
original_image = image
cv2.imshow('original',original_image)

cv2.waitKey(0)
cv2.destroyAllWindows()
``` 

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
kernel1 = np.ones((11,11),np.float32)/121
box_filter = cv2.filter2D(original_image,-1,kernel2)
cv2.imshow('box_filter',box_filter)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
ii) Using Weighted Averaging Filter
```Python
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
cv2.imshow('weighted_filter',weighted_filter)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
iii) Using Gaussian Filter
```Python
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0) 
cv2.imshow('gaussian_filter',gaussian_blur)

cv2.waitKey(0)
cv2.destroyAllWindows()

```

iv) Using Median Filter
```Python
median = cv2.medianBlur(src=original_image,ksize = 11)
cv2.imshow('median_filter',median)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]]) 
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
cv2.imshow('laplacian_kernel',laplacian_kernel)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
ii) Using Laplacian Operator
```Python
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
cv2.imshow('laplacian_operator',laplacian_operator)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

## OUTPUT:
### Original Image


### 1. Smoothing Filters
### Using Averaging Filter
![Screenshot (4)](https://user-images.githubusercontent.com/94154941/234290061-ce09e635-22af-4da0-98de-724ef969366f.png)


### Using Weighted Averaging Filter

![Screenshot (5)](https://user-images.githubusercontent.com/94154941/234290267-33db4964-88aa-48c5-98dc-eb855bff8eb2.png)


### Using Gaussian Filter

![Screenshot (6)](https://user-images.githubusercontent.com/94154941/234290343-903ccd02-56b4-4906-a431-4d6fc07895c0.png)

### Using Median Filter

![Screenshot (7)](https://user-images.githubusercontent.com/94154941/234290419-42f90910-c794-4a68-bf28-eabbfd937768.png)


### 2. Sharpening Filters

### Using Laplacian Kernal
![Screenshot (8)](https://user-images.githubusercontent.com/94154941/234290458-4b2c8d0a-f042-4f40-92fc-3a5c0c9c83ed.png)


### Using Laplacian Operator

![Screenshot (9)](https://user-images.githubusercontent.com/94154941/234290490-1465575d-c321-44d8-a459-fecb8e9b338a.png)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
