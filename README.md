# IMPLEMENTATION-OF-FILTERSS
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import libraries and read the saved images using cv2.imread().


### Step2
Convert the saved BGR image to RGB using cvtColor().

### Step3
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

### Step4
Apply the filters using cv2.filter2D() for each respective filters.
 

### Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().


## Program:
### Developed By   :SHARMILA A
### Register Number:212221230094

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("temp.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)

### 1. Smoothing Filters

i) Using Averaging Filter
```
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")

```
ii) Using Weighted Averaging Filter
```

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")

```
iii) Using Gaussian Filter
```
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")
```

iv) Using Median Filter
```
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")

```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```

kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")

```
ii) Using Laplacian Operator
```
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")

```

## OUTPUT:
### 1. Smoothing Filters


i) Using Averaging Filter
![c1](https://github.com/Sharmilasha/IMPLEMENTATION-OF-FILTERSS/assets/94506182/6bccf1a0-4b2b-4348-bda3-3b833dcfd7a3)



ii) Using Weighted Averaging Filter
![c2](https://github.com/Sharmilasha/IMPLEMENTATION-OF-FILTERSS/assets/94506182/79df3bc5-0b5b-4b22-9355-c27cbf115281)



iii) Using Gaussian Filter


![c3](https://github.com/Sharmilasha/IMPLEMENTATION-OF-FILTERSS/assets/94506182/f0791e42-70e1-4d77-94c2-aca426764af3)


iv) Using Median Filter

![c4](https://github.com/Sharmilasha/IMPLEMENTATION-OF-FILTERSS/assets/94506182/c43f3dd6-8276-40ee-bd2f-a4092fdca1c0)



### 2. Sharpening Filters

i) Using Laplacian Kernal

![c5](https://github.com/Sharmilasha/IMPLEMENTATION-OF-FILTERSS/assets/94506182/c4d21bea-8696-4446-9430-4dda4fc2aac0)


ii) Using Laplacian Operator

![c6](https://github.com/Sharmilasha/IMPLEMENTATION-OF-FILTERSS/assets/94506182/db87dcf6-b5f5-4c80-bb90-722e5a13cc1f)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
