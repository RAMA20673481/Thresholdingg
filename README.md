# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

Step1:
Load the necessary packages.

Step2:
Read the Image and convert to grayscale.

Step3:
Use Global thresholding to segment the image.

Step4:
Use Adaptive thresholding to segment the image.

Step5:
Use Otsu's method to segment the image and display the results


## Program

# Load the necessary packages
```
import cv2
import matplotlib.pyplot as plt
```

# Read the Image and convert to grayscale
```
image=cv2.imread("Spidy.png")
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
```

```
plt.subplot(2,2,1)
plt.imshow(cv2.cvtColor(image,cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
```
_,global_thresholded = cv2.threshold(gray_img, 127, 255, cv2.THRESH_BINARY)

adaptive_thresholded = cv2.adaptiveThreshold(gray_img, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

_,otsu_thresholded = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```
# Use Global thresholding to segment the image
```
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
```
# Use Adaptive thresholding to segment the image
```
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
```
# Use Otsu's method to segment the image 
```
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
```
# Display the results

## Output

### Original Image

<img width="723" height="260" alt="Screenshot 2025-11-13 102934" src="https://github.com/user-attachments/assets/358de5a1-5aac-4fdc-b3aa-7e6f3334109f" />


### Global Thresholding

<img width="740" height="266" alt="Screenshot 2025-11-13 102945" src="https://github.com/user-attachments/assets/0616b99d-6775-4169-964b-1edfce50239b" />


### Adaptive Thresholding

<img width="741" height="249" alt="Screenshot 2025-11-13 102958" src="https://github.com/user-attachments/assets/bae4c42e-c37c-459e-b36d-40754eb41ed8" />


### Optimum Global Thesholding using Otsu's Method

<img width="738" height="262" alt="Screenshot 2025-11-13 103010" src="https://github.com/user-attachments/assets/2780b266-587b-4bbf-87f7-2796ce01365b" />



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
