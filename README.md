# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: 
# Register Number:
 
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
plt.show()

plt.hist(image.ravel(),256,[0,256])
plt.title('Histogram')
plt.show()

img_eq = cv2.equalizeHist(cv2.cvtColor(image, cv2.COLOR_BGR2GRAY))

plt.hist(img_eq.ravel(),256,[0,256])
plt.title('Equalized Histogram')
plt.show()

img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()


```
## Output:
### Input Grayscale Image and Color Image
#### Color image: 
<img width="642" height="463" alt="image" src="https://github.com/user-attachments/assets/d7e67d04-bc72-4908-a413-09dbb8206a37" />

#### Gray image:
<img width="645" height="465" alt="image" src="https://github.com/user-attachments/assets/c14124e6-434b-4781-b448-179d3452e250" />

### Histogram of Grayscale Image and any channel of Color Image
<img width="726" height="544" alt="image" src="https://github.com/user-attachments/assets/e3973566-a789-45f5-9626-d032d7278b15" />

### Histogram Equalization of Grayscale Image.
<img width="723" height="543" alt="image" src="https://github.com/user-attachments/assets/4b93656f-36c2-450f-b6f8-1cc61bb6c9e7" />

### Equalized Image:
<img width="687" height="492" alt="image" src="https://github.com/user-attachments/assets/a106be85-99ae-4c7e-b500-5fffe5fcefb0" />

### Histogram of Equalized Image:
<img width="720" height="541" alt="image" src="https://github.com/user-attachments/assets/47f377a3-cdc1-4193-98a9-0d9fa88262d3" />




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
