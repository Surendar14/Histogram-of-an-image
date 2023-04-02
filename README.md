# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import cv2, matplotlib.py libraries and display the saved images using cv2.imshow().

### Step2:
Use cv2.calcHist(images, channels, mask, histSize, ranges[, hist[, accumulate]]) to find the histogram of the image.

### Step3:
Plot the image and its stem plots using the plt.show() and plt.stem() functions.

### Step4:
Equalize the grayscale image using the in-built function cv2.equalizeHist().

### Step5:
Print the original and equalized image using cv2.imshow() and end the program.

## Program:
```
# Developed By: SURENDAR S
# Register Number: 212220230051
```

import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.
gray_image = cv2.imread("doggy (1).jpg")
color_image =cv2.imread("cat (1).jpg",-1)
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Colour Image",color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Display the histogram of gray scale image and any one channel histogram from color image
gray_hist = cv2.calcHist([gray_image],[0],None,[256],[0,256])
color_hist = cv2.calcHist([color_image],[0],None,[256],[0,256])
plt.figure()
plt.imshow(gray_image)
plt.show()
plt.title("Histogram")
plt.xlabel("Grayscale Value")
plt.ylabel("Pixel Count")
plt.stem(gray_hist)
plt.show()
plt.imshow(color_image)
plt.show()
plt.title("Histogram of Color Image - Green Channel")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(color_hist)
plt.show()

# Write the code to perform histogram equalization of the image. 
gray_image = cv2.imread("doggy (1).jpg",0)
cv2.imshow("Gray Image",gray_image)
equ = cv2.equalizeHist(gray_image)
cv2.imshow("Equalized Image",equ)
cv2.waitKey(0)
cv2.destroyAllWindows

```
## Output:
### Input Grayscale Image and Color Image

![download (4)](https://user-images.githubusercontent.com/75235759/229364699-f7b19e65-dd93-4614-91a6-342c499c61f7.png)

![download (3)](https://user-images.githubusercontent.com/75235759/229364680-7d55fb4c-c62b-42a4-96b9-36c88e605d12.png)


### Histogram of Grayscale Image and any channel of Color Image

![download (2)](https://user-images.githubusercontent.com/75235759/229364880-3b903f52-77a0-4413-af9f-5dfb6272cddf.png)

![download (1)](https://user-images.githubusercontent.com/75235759/229364897-fde77abb-566d-442b-8f0a-8a2b0385ae59.png)

![download](https://user-images.githubusercontent.com/75235759/229364917-624ffbb8-c1a4-425f-a63e-5993089a37ad.png)


### Histogram Equalization of Grayscale Image

<img width="299" alt="hist" src="https://user-images.githubusercontent.com/75235759/229364934-ead92dac-8ab4-4145-9d64-c8035230c45a.png">\

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
