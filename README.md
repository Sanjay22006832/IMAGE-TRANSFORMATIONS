# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.


### Step3:

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.
2.Scaling resizes the image by scaling factors.
3.Shearing distorts the image along one axis.
4.Reflection flips the image horizontally or vertically.
5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.
## Program:
```python
Developed By: M Sanjay
Register Number:212222240090
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('kettavan.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib

# 1. Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))

# 2. Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x

# 3. Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))

# 4. Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)

# 5. Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))

# 6. Cropping
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image

# Plot the original and transformed images
plt.figure(figsize=(12, 8))

Original Image

plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()
i)Image Translation
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
plt.show()



ii) Image Scaling
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
plt.show()


iii)Image shearing


plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
plt.show()

iv)Image Reflection



plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
plt.show()
v)Image Rotation

plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
plt.show()




vi)Image Cropping

# Plot cropped image separately as its aspect ratio may be different
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()



```
## Output:
### Original Image:
![Screenshot 2024-10-03 162617](https://github.com/user-attachments/assets/6734fc31-6f13-4098-b66e-1b256edf2e72)

### i)Image Translation
<br>![Screenshot 2024-10-03 162648](https://github.com/user-attachments/assets/b79d62a5-a7d6-42d5-812c-68f701b0c557)


<br>
<br>
<br>

### ii) Image Scaling
<br>![Screenshot 2024-10-03 162654](https://github.com/user-attachments/assets/779e75f7-0444-4c7b-9160-b8a0f8e31ff0)

<br>
<br>
<br>


### iii)Image shearing
<br>![Screenshot 2024-10-03 162700](https://github.com/user-attachments/assets/c5392a73-952e-425b-8163-e2c2c23c5343)

<br>
<br>
<br>


### iv)Image Reflection
<br>![Screenshot 2024-10-03 162706](https://github.com/user-attachments/assets/92cf2bbe-c223-4fc3-ae47-e4a19223c450)

<br>
<br>
<br>



### v)Image Rotation
<br>![Screenshot 2024-10-03 162711](https://github.com/user-attachments/assets/70c72204-9ffd-4191-92fc-3b4a77f98afb)

<br>
<br>
<br>



### vi)Image Cropping
<br>![Screenshot 2024-10-03 162715](https://github.com/user-attachments/assets/f0da1b32-9e81-4c15-9fcb-e8f7f40042d8)

<br>
<br>
<br>




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
