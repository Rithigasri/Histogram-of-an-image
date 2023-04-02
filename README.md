# EXPERIMENT 04: HISTOGRAM AND HISTOGRAM EQUALIZATION OF AN IMAGE
## AIM:
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### Step 1:
Import the required libraries and read the grayscale and BGR image.
### Step 2:
Use cv2.calcHist() to plot the histogram for grayscale image and BGR image(Single color channel).
### Step 3:
Display the histogram of grayscale image and BGR image for single channel.
### Step 4:
Use cv2.equalizeHist() to plot the histogram equalization of an image.
### Step 5:
Display the orignal image and histogram equalized image.
## PROGRAM:
```
# Developed By: RITHIGA SRI.B
# Register Number: 212221230083
```
### Importing Libraries:
```
import cv2
import matplotlib.pyplot as plt
```
### Write your code to find the histogram of gray scale image and color image channels.
```
# Histogram for Grayscale image
grayscale_img=cv2.imread("black.jpg")
plt.imshow(grayscale_img)
plt.show()
hist=cv2.calcHist([grayscale_img],[0],None,[256],[0,255])

# Histogram for BGR image for a single channel
color_img=cv2.imread("color.jpeg")
hist1=cv2.calcHist([color_img],[1],None,[256],[0,255])
plt.imshow(color_img)
plt.show()
```
### Display the histogram of gray scale image and any one channel histogram from color image
```
#Plotting histogram for Grayscale image
plt.figure()
plt.title("Histogram")
plt.xlabel("Grayscale value")
plt.ylabel("Pixel Count")
plt.stem(hist)
plt.show()

#Plotting histogram for BGR image -Single Channel
plt.figure()
plt.title("Histogram for BGR image")
plt.xlabel("BGR intensity value")
plt.ylabel("Pixel Count")
plt.stem(hist1)
plt.show()
```

### Write the code to perform histogram equalization of the image. 
```
#Histogram equalization for Grayscale image
import cv2
Gray_image=cv2.imread('black.jpg',0)
equalize=cv2.equalizeHist(Gray_image)
#Resizing image 
Gray_image= cv2.resize(Gray_image, (270,190))
equalize= cv2.resize(equalize, (270,190))
#Output
cv2.imshow('GRAY IMAGE',Gray_image)
cv2.imshow('EQUALIZED IMAGE',equalize)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## OUTPUT:
### Input Grayscale Image and Color Image:
* Grayscale Image:  
![image](https://user-images.githubusercontent.com/93427256/229346880-a0db4fa3-4a6a-4eab-ad1f-0f91ae135a62.png)
* Color Image:  
![image](https://user-images.githubusercontent.com/93427256/229346923-6eda3505-c63a-406d-9922-053a768948f7.png)
### Histogram of Grayscale Image and any channel of Color Image:
* Grayscale Image:  
![image](https://user-images.githubusercontent.com/93427256/229346990-e111337f-4cb2-425f-a122-ccff25af9e98.png)
* Color Image:  
![image](https://user-images.githubusercontent.com/93427256/229347009-b17a8778-cb72-4290-a3be-2c8ce193a3df.png)
  
### Histogram Equalization of Grayscale Image:  
![image](https://user-images.githubusercontent.com/93427256/229347067-85fb7c3e-1272-4906-9ce1-16c38ae98f33.png)

## RESULT: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
