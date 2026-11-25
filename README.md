# Opening and Closing Operations Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 7:

Compare the original, opened, and closed images.

## Program

## Developed By

**Name:** R P Loshini

**Register No:** 212225230155

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load input image in grayscale
img = cv2.imread(r"C:\Users\acer\DIPT\dog.jpg", 0)

# Create structuring element (kernel)
kernel = np.ones((9, 9), np.uint8)

# Apply Opening and Closing operations
opened_img = cv2.morphologyEx(img, cv2.MORPH_OPEN, kernel)
closed_img = cv2.morphologyEx(img, cv2.MORPH_CLOSE, kernel)

# Display Original, Opened, and Closed images side-by-side
plt.figure(figsize=(15, 5))

plt.subplot(1, 3, 1)
plt.imshow(img, cmap='gray')
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(opened_img, cmap='gray')
plt.title("Opening Operation")
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(closed_img, cmap='gray')
plt.title("Closing Operation")
plt.axis('off')

plt.tight_layout()
plt.show()
```

## Output

### Original Image

- The input image is displayed.
- The image serves as the source for morphological processing.

### Opening Operation

- Original image is displayed.
- Opened image is displayed.
- Small foreground noise is removed.
- Thin protrusions and isolated pixels are eliminated.
- Object boundaries become smoother.

### Closing Operation

- Original image is displayed.
- Closed image is displayed.
- Small holes and gaps inside objects are filled.
- Broken regions are connected.
- Object boundaries become more continuous.

<img width="1072" height="385" alt="image" src="https://github.com/user-attachments/assets/fd3fc266-ca4a-4893-8231-8594bef6d639" />


## Applications

### Opening

- Noise removal in binary images.
- Separation of connected objects.
- Preprocessing for object detection.

### Closing

- Filling small holes in objects.
- Connecting nearby components.
- Enhancing segmented regions.

## Advantages

### Opening

- Removes unwanted foreground noise.
- Preserves major object structures.
- Improves segmentation quality.

### Closing

- Restores object continuity.
- Eliminates small background gaps.
- Improves object representation.

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV. 
