# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Read the test image

### Step2
Define the identity kernel, using a 3×3 NumPy array

### Step 3
Use the filter2D() function in OpenCV to perform the linear filtering operation

### Step 4
Display the original and filtered images, using imshow()

### Step 5
Save the filtered image to disk, using imwrite()


## Program:
```
### Developed By :Samyuktha S
### Register Number:212222240089
```

### 1. Smoothing Filters

i) Using Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread(r'C:\Users\SEC\Pictures\Screenshots\dog.jpg')
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
ii) Using Weighted Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread(r'C:\Users\SEC\Pictures\Screenshots\dog.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')

```
iii) Using Gaussian Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread(r'C:\Users\SEC\Pictures\Screenshots\dog.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

iv) Using Median Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread(r'C:\Users\SEC\Pictures\Screenshots\dog.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')

```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread(r'C:\Users\SEC\Pictures\Screenshots\dog.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')

```
ii) Using Laplacian Operator
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread(r'C:\Users\SEC\Pictures\Screenshots\dog.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')

```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

![image](https://github.com/SamyukthaSreenivasan/Implementation-of-filter/assets/119475703/d2a77bf1-9ea0-4127-84e4-6e8cb5d6c0b1)

ii) Using Weighted Averaging Filter

![image](https://github.com/SamyukthaSreenivasan/Implementation-of-filter/assets/119475703/37f8a7cc-627d-4560-b468-4d0355b3cde3)

iii) Using Gaussian Filter

![image](https://github.com/SamyukthaSreenivasan/Implementation-of-filter/assets/119475703/beb783e5-17a9-4759-bb7a-33889e601402)


iv) Using Median Filter

![image](https://github.com/SamyukthaSreenivasan/Implementation-of-filter/assets/119475703/a0c28c02-36e0-492e-8a4c-55dd15c61f06)


### 2. Sharpening Filters

i) Using Laplacian Kernal

![image](https://github.com/SamyukthaSreenivasan/Implementation-of-filter/assets/119475703/1f5e77c4-ce95-4583-8a6e-7dda6bf8e8c4)

ii) Using Laplacian Operator

![image](https://github.com/SamyukthaSreenivasan/Implementation-of-filter/assets/119475703/f4cf58db-b1c7-4930-af8b-f2230b4daaa8)


### Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
