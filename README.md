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

## Program
```
Name: S.Thirisha
Reg no:212222230160
```

# Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```python
image = cv2.imread("nature.png",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("nature.png",0)
```

# Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```



# Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Display the results

```python
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


```
## Output

### Original Image
![image](https://github.com/Thirisha-s/Thresholdingg/assets/120380280/95f3320a-1af2-4d80-88e0-fe6a44bf489f)



### Global Thresholding
![image](https://github.com/Thirisha-s/Thresholdingg/assets/120380280/8ddae94b-9143-40e1-9f65-c1f03a845173)

![image](https://github.com/Thirisha-s/Thresholdingg/assets/120380280/c70cf3a0-0ad4-439a-8bed-3d937e5a58e4)

![image](https://github.com/Thirisha-s/Thresholdingg/assets/120380280/67469008-22c6-411e-8549-c17886f44930)

![image](https://github.com/Thirisha-s/Thresholdingg/assets/120380280/9a1b2bd7-82f2-456f-ba4b-7a47a5e19219)

![image](https://github.com/Thirisha-s/Thresholdingg/assets/120380280/cd47ebbb-5c62-44d7-9868-b9a0e7744ce8)


### Adaptive Thresholding

![image](https://github.com/Thirisha-s/Thresholdingg/assets/120380280/c099d9ac-6ded-440d-8c05-b8d155671b5d)

![image](https://github.com/Thirisha-s/Thresholdingg/assets/120380280/52885f60-eda1-40df-b467-2f2b779251d6)



### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/Thirisha-s/Thresholdingg/assets/120380280/0a1b181c-cd4a-4013-91b6-3ee91c86d62f)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
