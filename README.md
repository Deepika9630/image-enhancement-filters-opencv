# Image Smoothing and Sharpening Using OpenCV
## NAME: DEEPIKA R
## REG NO: 212224230054
## Aim:

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used:

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm:

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---


## Program:



### 1. Smoothing Filters

#### i) Using Averaging Filter
```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("taj.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
## Output
<img width="758" height="274" alt="image" src="https://github.com/user-attachments/assets/99aea850-cbaf-451e-a89e-cf025bf65772" />


#### ii) Using Weighted Averaging Filter
```python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
## Output
<img width="569" height="404" alt="image" src="https://github.com/user-attachments/assets/73457b97-8844-49f3-a0ec-3f1ac0f0246d" />

#### iii) Using Gaussian Filter
```python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
## Output
<img width="568" height="414" alt="image" src="https://github.com/user-attachments/assets/1e649293-8336-4613-b7bb-e803eab70129" />

#### iv)Using Median Filter
```python
median=cv2.medianBlur(image2,13)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
## Output
<img width="366" height="274" alt="image" src="https://github.com/user-attachments/assets/9a9a67f9-fbd8-4e60-99e7-0f9cb46db7d6" />


### 2. Sharpening Filters

#### i) Using Laplacian Linear Kernal
```python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
## Output

<img width="548" height="411" alt="image" src="https://github.com/user-attachments/assets/f72a4f4b-3381-41e7-a047-1ea12c747568" />

#### ii) Using Laplacian Operator
```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
## Output
<img width="534" height="406" alt="image" src="https://github.com/user-attachments/assets/39cd5424-2567-4074-af03-86ff6f1f006d" />


##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
