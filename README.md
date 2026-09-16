# Exp-10--Record-IMPLEMENTATION-OF-OPENING-AND-CLOSING

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



## Developed By

*Name: Sivaprasath R* 

*Register No:212224243007* 


## Program
### Original Image

- The input image is displayed.
- The image serves as the source for morphological processing.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = np.zeros((300, 500), dtype=np.uint8)

cv2.putText(image, "Sivaprasath R", (30, 150),
            cv2.FONT_HERSHEY_SIMPLEX, 1.5, 255, 5)

plt.imshow(image, cmap="gray")
plt.title("Original Image")
plt.axis("off")
plt.show()
```
### Opening Operation

- Original image is displayed.
- Opened image is displayed.
- Small foreground noise is removed.
- Thin protrusions and isolated pixels are eliminated.
- Object boundaries become smoother.
```
kernel = np.ones((5, 5), np.uint8)

opening = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

plt.imshow(opening, cmap="gray")
plt.title("Opening Operation")
plt.axis("off")
plt.show()
```
### Closing Operation

```
closing = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)

plt.imshow(closing, cmap="gray")
plt.title("Closing Operation")
plt.axis("off")
plt.show()
```
### comparison of three
```
plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.imshow(image, cmap="gray")
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(opening, cmap="gray")
plt.title("Opening")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(closing, cmap="gray")
plt.title("Closing")
plt.axis("off")

plt.show()
```
## Output
<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/827737f8-6e8a-4eac-8faf-3be504c7a075" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/f42a24f4-5950-48c8-9c0b-9abfa6f6558b" />

<img width="389" height="409" alt="download" src="https://github.com/user-attachments/assets/bea54e48-f343-4962-84e3-ec0757c9ec18" />

<img width="950" height="313" alt="download" src="https://github.com/user-attachments/assets/00be55bc-eef7-4241-a3ff-472d626b288b" />



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
## Comparison of three


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

Thus, the morphological operations *Opening* and *Closing* are successfully implemented using OpenCV.
