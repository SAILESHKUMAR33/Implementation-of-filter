# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step 2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step 3:

Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
### Step 4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

### Step 5 :
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
### Step 6 :
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.

## Program:
```
 Developed By   : Saileshkumar A
 Register Number: 212222230126
```

### 1. Smoothing Filters

#### i) Using Averaging Filter
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('car.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/4d842966-789b-4994-ada8-dafd18edc8da)          
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/8b3c6bb4-afbe-4ad6-99ff-67f4280e9326)


#### ii) Using Weighted Averaging Filter
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('car.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/755b56f5-3410-4f31-ba19-0f3bedf5380c)        
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/8181e4da-1d5a-4ec6-9964-0cc3c0d7aaa6)


#### iii) Using Gaussian Filter
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('car.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/ce7b44d3-1d65-486f-9e74-cd0f639045e7)
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/d59e8aff-e86c-4004-a898-6f1034a32efc)


#### iv) Using Median Filter
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('car.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/cb44a53d-8693-4877-926c-8bcf7f445b98)
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/7394429e-39ba-4339-94bd-1990f7660ba0)


### 2. Sharpening Filters
#### i) Using Laplacian Kernal
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('car.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/f2ea1d8d-465e-4ad5-ac5e-966304130ec0)          
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/3598403a-d910-4b80-bca5-a02ed32f0c57)

#### ii) Using Laplacian Operator
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('car.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/95124a5e-fc10-457e-9515-1e63ef41e257)
![image](https://github.com/Yogeshvar005/Implementation-of-filter/assets/113497367/3bceb455-c191-4566-b01c-9f185f31ef94)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
