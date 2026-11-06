# Histogram Equalization Using OpenCV (Grayscale & Color Images)

## Name       : Karthickkumar R
## Register No: 212223040087


## Aim:
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

## Program

### Developed By:
**Name       :** **Karthickkumar R**
**Register No:** **212223040087**  
```

import cv2
import numpy as np
import matplotlib.pyplot as plt


img_gray = cv2.imread('3d.jpg', cv2.IMREAD_GRAYSCALE)

plt.figure(figsize=(10, 4))
plt.subplot(1, 2, 1)
plt.imshow(img_gray, cmap='gray')
plt.title('Original Grayscale Image')

plt.subplot(1, 2, 2)
plt.hist(img_gray.ravel(), 256, range=[0, 256])
plt.title('Original Grayscale Histogram')
plt.show()


img_gray_eq = cv2.equalizeHist(img_gray)

plt.figure(figsize=(10, 4))
plt.subplot(1, 2, 1)
plt.imshow(img_gray_eq, cmap='gray')
plt.title('Equalized Grayscale Image')

plt.subplot(1, 2, 2)
plt.hist(img_gray_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Grayscale Histogram')
plt.show()


img_color = cv2.imread('3d.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img_color, cv2.COLOR_BGR2HSV)


img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_color_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)


plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.imshow(img_color[:, :, ::-1])  # BGR to RGB
plt.title('Original Color Image')

plt.subplot(1, 2, 2)
plt.imshow(img_color_eq[:, :, ::-1])  # BGR to RGB
plt.title('Equalized Color Image')
plt.show()


plt.figure(figsize=(12, 4))
plt.subplot(1, 2, 1)
plt.hist(img_color.ravel(), 256, range=[0, 256])
plt.title('Original Color Histogram')

plt.subplot(1, 2, 2)
plt.hist(img_color_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Color Histogram')
plt.show()
```

---

##  Output

<img width="350" height="430" alt="Screenshot 2026-11-06 154321" src="https://github.com/user-attachments/assets/0361c1e0-c603-4ee0-a40c-b77503b5c2ef" />

<img width="607" height="437" alt="Screenshot 2026-11-06 154342" src="https://github.com/user-attachments/assets/ac037331-4fb1-426a-95e8-ae99b577fabb" />

<img width="593" height="431" alt="Screenshot 2026-11-06 154353" src="https://github.com/user-attachments/assets/2ed57b7e-9e1e-4884-8c32-b8425d58f8bd" />

<img width="367" height="437" alt="Screenshot 2026-11-06 154401" src="https://github.com/user-attachments/assets/49782c5c-47a2-4980-81e3-8107a5df9116" />

<img width="362" height="432" alt="Screenshot 2026-11-06 154409" src="https://github.com/user-attachments/assets/2349d784-f73a-45f2-8391-6cb2e1d64368" />

<img width="587" height="432" alt="Screenshot 2026-11-06 154419" src="https://github.com/user-attachments/assets/b83749c4-660a-4d6f-b55f-b39b5c155a46" />

<img width="1096" height="397" alt="Screenshot 2026-11-06 154428" src="https://github.com/user-attachments/assets/93b86a91-eaed-4f5d-abaa-55a9df07c0f4" />

<img width="1101" height="337" alt="Screenshot 2026-11-06 154438" src="https://github.com/user-attachments/assets/b7b3cad4-36e2-4524-a82f-1484ee3bb2e5" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility. 
