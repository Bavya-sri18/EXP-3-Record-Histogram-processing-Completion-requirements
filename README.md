# EXP-3-Record-Histogram-processing-Completion-requirements

## Name : BAVYA SRI B
## REGISTER NUMBER : 212224230034
## EXPERIMENT : Record-Histogram processing 

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:**  BAVYA SRI B

**Register Number:** 212224230034

```PYTHON
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread(r"D:\Screenshots\Bavya.jpeg", cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread(r"D:\Screenshots\Bavya.jpeg", cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="402" height="501" alt="image" src="https://github.com/user-attachments/assets/44a2e675-d150-4559-9cc1-4ea523eb7caf" />



### Input Grayscale Image Range

<img width="682" height="492" alt="image" src="https://github.com/user-attachments/assets/ce9046bb-f40c-42ea-b3c5-ffdd4f94714b" />



### Input Grayscale Image Equalized Histogram

<img width="682" height="497" alt="image" src="https://github.com/user-attachments/assets/25267a59-1f11-40f6-972d-4340ed6465e3" />



### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="422" height="490" alt="image" src="https://github.com/user-attachments/assets/7dcdb670-e0b9-4c7c-b331-3fed09628adf" />



### Equalized Image

<img width="390" height="492" alt="image" src="https://github.com/user-attachments/assets/14cbb888-f0b4-4da2-be7a-949d050679e5" />




### Equalized Histogram

<img width="671" height="505" alt="image" src="https://github.com/user-attachments/assets/cc941bef-d283-4594-8d1c-49547b943bfb" />



### Final Output of Original Image and Equalized 

<img width="832" height="292" alt="image" src="https://github.com/user-attachments/assets/3673f05e-0956-4714-8f29-e8ed53f87c4c" />



### Final Output of Original Image and its Histogram Equalized

<img width="817" height="286" alt="image" src="https://github.com/user-attachments/assets/f0b67439-f5c7-4852-8e5a-c2f027d60872" />



## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
