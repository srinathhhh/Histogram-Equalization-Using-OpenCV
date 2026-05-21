# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---



### Developed By:
**Name:** SRINATH N

**Register Number:** 2305003009

## Program
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```python
img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)
```
```python
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)
```
```python
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
```python
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
```
```python
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
```python
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
```python
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
```python
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```python
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.ashow()
```
```python
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed


  <img width="552" height="396" alt="download" src="https://github.com/user-attachments/assets/ac95e1a7-f9ae-4e84-a4d6-ae0c0451b72d" />
  
 
- Histogram of original grayscale image is plotted

  <img width="578" height="435" alt="download" src="https://github.com/user-attachments/assets/c5a090f0-0be7-4226-be11-d2a290a3296b" />

- Enhanced image after histogram equalization is displayed

  <img width="578" height="435" alt="download" src="https://github.com/user-attachments/assets/757d86e5-0bba-4bc2-b781-b7773889b4f7" />

- Histogram of enhanced grayscale image shows improved contrast  

  <img width="552" height="396" alt="download" src="https://github.com/user-attachments/assets/7f79813b-af71-44f9-a6e3-b0070a4e7b97" />


### Color Image Histogram Equalization

- Original color image is displayed

  <img width="552" height="396" alt="download" src="https://github.com/user-attachments/assets/71a95ba2-e214-420a-92bf-7f55f61e40c9" />
 
- Histogram of B, G, R channels is plotted

  <img width="578" height="435" alt="download" src="https://github.com/user-attachments/assets/437aac62-5290-4463-bceb-0fc3bd85ebc3" />


- Enhanced image after HSV-based equalization is displayed

  <img width="1426" height="416" alt="download" src="https://github.com/user-attachments/assets/15a65c94-c25e-45ec-9a7f-3a389a5e488a" />

- Histogram of enhanced image shows better intensity distribution

  <img width="1244" height="374" alt="download" src="https://github.com/user-attachments/assets/6492b993-00b3-4b74-b334-5bfb9044f474" />


---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
