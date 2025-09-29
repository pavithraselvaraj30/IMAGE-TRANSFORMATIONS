# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step 1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

## Step 2:
Read the input image using cv2.imread() and store it in a variable for further processing

## Step 3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

## Step 4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

## Program:
```python
Developed By:Pavithra S
Register Number:212223230147
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image=cv2.imread("Image1.jpg")
image.shape
#Display the images.
plt.imshow(image[:,:,::-1])
plt.title("Original Image")
plt.show()
```
## Output:

<img width="313" height="313" alt="Screenshot 2025-09-29 120658" src="https://github.com/user-attachments/assets/72d4c4bb-6845-4c80-a543-004c1ea6d1a7" />


## i)Image Translation
```
tx,ty=100,200
M_translation=np.float32([[1,0,tx],[0,1,ty]])
translated_image=cv2.warpAffine(image,M_translation, (673,419))
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis("on")
plt.show()
```
## Output:
<img width="439" height="274" alt="Screenshot 2025-09-29 120708" src="https://github.com/user-attachments/assets/b359fddf-c817-432f-96a7-83143ad98f12" />


## ii) Image Scaling
```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  # Set title
plt.axis('off')
```
## Output:
<img width="379" height="194" alt="Screenshot 2025-09-29 120718" src="https://github.com/user-attachments/assets/99ea6148-cbd7-4f95-b42b-21c765d4220b" />


## iii)Image shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  
plt.title("Sheared Image")  
plt.axis('off')
```
## Output:
<img width="307" height="289" alt="Screenshot 2025-09-29 120725" src="https://github.com/user-attachments/assets/fd9a974a-41e1-45b5-b477-3afffe397056" />



## iv)Image Reflection
```
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image")  
plt.axis('off')
```
## Output:

<img width="248" height="287" alt="Screenshot 2025-09-29 120733" src="https://github.com/user-attachments/assets/7e270ab0-3586-4cd8-9522-8f2b3626ea32" />



## v)Image Rotation
```
(height, width) = image.shape[:2] 
angle = 45 
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Rotated Image")  
plt.axis('off')
```
## Output:

<img width="261" height="290" alt="Screenshot 2025-09-29 120742" src="https://github.com/user-attachments/assets/85fb77f8-8196-400e-a872-72301e6f5a4d" />


## vi)Image Cropping
```
x, y, w, h = 100, 100, 200, 150 
cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")  
plt.axis('off')
```
## Output:
<img width="398" height="287" alt="Screenshot 2025-09-29 120749" src="https://github.com/user-attachments/assets/d8f0d743-59ec-488b-9ced-16d1bc24b606" />


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
