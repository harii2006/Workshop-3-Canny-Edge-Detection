# Workshop-3-Canny-Edge-Detection
## Aim
To read a digital image, convert it to grayscale, and detect the edges present in it using the Canny Edge Detection algorithm with the OpenCV library in Python.

## Procedure
Theory
The Canny edge detector is a multi-stage algorithm that identifies the boundaries of objects within an image. It proceeds through the following stages:

Noise reduction — The image is smoothed using a Gaussian filter to suppress noise that could be mistaken for edges.
Gradient calculation — The intensity gradient of the smoothed image is computed to highlight regions of rapid intensity change.
Non-maximum suppression — The algorithm thins out the edges by keeping only the local maxima in the gradient direction.
Double thresholding — Pixels are classified as strong, weak, or non-edges using two threshold values (a lower and an upper bound).
Edge tracking by hysteresis — Weak edges connected to strong edges are retained, while isolated weak edges are discarded, producing the final edge map.
Implementation Steps
Import the required libraries — OpenCV (cv2) for image processing and Matplotlib for visualization.
Read the input image in grayscale mode using cv2.imread().
Apply a Gaussian blur (5×5 kernel) to the grayscale image using cv2.GaussianBlur() to reduce noise.
Apply the Canny edge detection algorithm using cv2.Canny() with a lower threshold of 50 and an upper threshold of 150.
Display the original image and the detected edges side by side using matplotlib.pyplot for comparison.
## Program
```
# Import libraries
import cv2
import matplotlib.pyplot as plt

# Read the image in grayscale
img = cv2.imread('img.jpeg', cv2.IMREAD_GRAYSCALE)

# Reduce noise with a Gaussian blur
blurred = cv2.GaussianBlur(img, (5,5), 0)

# Apply the Canny edge detector
edges = cv2.Canny(blurred, 50, 150)

# Display original image and detected edges side by side
plt.figure(figsize=(10,5))
plt.subplot(121), plt.imshow(img, cmap='gray')
plt.title('Original Image'), plt.axis('off')
plt.subplot(122), plt.imshow(edges, cmap='gray')
plt.title('Detected Edges'), plt.axis('off')
plt.show()
```
## Output
<img width="908" height="495" alt="image" src="https://github.com/user-attachments/assets/539a8e59-56f1-4af8-a533-e6a5c2cc8261" />

Result
The Canny Edge Detection algorithm was successfully implemented using OpenCV. The grayscale input image was denoised using a Gaussian blur, and the edges of the objects (facial features, hair, and clothing outline) were accurately detected and highlighted in the output image, thereby verifying the working of the Canny edge detection technique.
