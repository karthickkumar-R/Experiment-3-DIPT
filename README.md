# Histogram Equalization Using OpenCV (Grayscale & Color Images)
**Name       :** Karthickkumar R

**Register No:** 212223040087


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


img_gray = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

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


img_color = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
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

<img width="502" height="337" alt="Screenshot 2026-11-06 001040" src="https://github.com/user-attachments/assets/fb4772a8-6b68-4df4-8e53-8770e6db92e9" />

<img width="598" height="440" alt="Screenshot 2026-11-06 001145" src="https://github.com/user-attachments/assets/ddb6eac9-2e1d-4c5f-a692-2e3b5c8107b3" />

<img width="600" height="442" alt="Screenshot 2026-11-06 001512" src="https://github.com/user-attachments/assets/abc9dccf-7733-4706-a47d-a90c88b1ad79" />

<img width="588" height="393" alt="Screenshot 2026-11-06 001523" src="https://github.com/user-attachments/assets/03d6eb8d-d3ae-46d4-91ee-b9ff0ad0cb7d" />

<img width="562" height="397" alt="Screenshot 2026-11-06 001625" src="https://github.com/user-attachments/assets/c3e4237d-52b5-4f34-9b7e-adb4aaa8cfd7" />

<img width="611" height="430" alt="Screenshot 2026-11-06 001633" src="https://github.com/user-attachments/assets/adb84b0d-27b5-4f04-8e0c-77102a42dad6" />

<img width="1122" height="327" alt="Screenshot 2026-11-06 001645" src="https://github.com/user-attachments/assets/4143e5f4-bac4-43a4-9dee-48cbe421318f" />

<img width="1103" height="337" alt="Screenshot 2026-11-06 001805" src="https://github.com/user-attachments/assets/842be63b-7330-4060-b11e-76a615695bc7" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility. 
