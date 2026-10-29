# Geometric Transformations Using OpenCV

---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---
### Developed By:
**Name:** PELLETI SINDHU SRI

**Register No:** 212224240113

---

##  Program 
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load the image
image_path = r"C:\Users\admin\little-cat-sitting-grass.jpg"
image = cv2.imread(image_path)

if image is None:
    print("Error: Image not found")
else:
    # Step 2: Display Original Image
    plt.figure()
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.title("Original Image")
    plt.axis('off')
    plt.show()

    # Step 3: Image Translation
    tx, ty = 100, 50
    M_translation = np.float32([
        [1, 0, tx],
        [0, 1, ty]
    ])

    translated_image = cv2.warpAffine(
        image, M_translation,
        (image.shape[1], image.shape[0])
    )

    plt.figure()
    plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
    plt.title("Translated Image")
    plt.axis('off')
    plt.show()

    # Step 4: Image Scaling
    scaled_image = cv2.resize(
        image, None, fx=2.0, fy=2.0,
        interpolation=cv2.INTER_LINEAR
    )

    plt.figure()
    plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))
    plt.title("Scaled Image")
    plt.axis('off')
    plt.show()

    # Step 5: Image Shearing
    shear_matrix = np.float32([
        [1, 0.5, 0],
        [0.5, 1, 0]
    ])

    sheared_image = cv2.warpAffine(
        image, shear_matrix,
        (image.shape[1], image.shape[0])
    )

    plt.figure()
    plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
    plt.title("Sheared Image")
    plt.axis('off')
    plt.show()

    # Step 6: Image Reflection
    reflected_image = cv2.flip(image, 1)

    plt.figure()
    plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
    plt.title("Reflected Image")
    plt.axis('off')
    plt.show()

    # Step 7: Image Rotation
    height, width = image.shape[:2]
    angle = 45
    center = (width // 2, height // 2)

    M_rotation = cv2.getRotationMatrix2D(center, angle, 1)

    rotated_image = cv2.warpAffine(
        image, M_rotation, (width, height)
    )

    plt.figure()
    plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
    plt.title("Rotated Image")
    plt.axis('off')
    plt.show()

    # Step 8: Image Cropping
    x, y, w, h = 100, 100, 200, 150
    cropped_image = image[y:y+h, x:x+w]

    plt.figure()
    plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
    plt.title("Cropped Image")
    plt.axis('off')
    plt.show()
```
---

##  Output

### Image Translation
- Original image is displayed  
- Translated image (shifted right and down) is displayed  

### Image Scaling
- Original image is displayed  
- Downscaled image (0.5×) is displayed  
- Upscaled image (2×) is displayed  

### Image Shearing
- Original image is displayed  
- Horizontally sheared image is displayed  
- Vertically sheared image is displayed  

### Image Reflection
- Original image is displayed  
- Horizontally flipped image is displayed  
- Vertically flipped image is displayed  
- Both-axis flipped image is displayed  

### Image Rotation
- Original image is displayed  
- 45° rotated image is displayed  
- 90° rotated image is displayed

<img width="667" height="462" alt="image" src="https://github.com/user-attachments/assets/59271320-4d25-4a6d-bb0a-f947c96ebe6d" />

<img width="653" height="471" alt="image" src="https://github.com/user-attachments/assets/dae600a6-6361-4157-bef9-610e19a5a06d" />

<img width="650" height="468" alt="image" src="https://github.com/user-attachments/assets/cd4338b4-a07f-44f5-abef-4037ffe8e5fc" />

<img width="648" height="471" alt="image" src="https://github.com/user-attachments/assets/68d6ad62-aefa-4cdc-adc0-ec713cb6b765" />

<img width="667" height="460" alt="image" src="https://github.com/user-attachments/assets/03e46b19-cfc2-4b43-98ce-295c2e11039a" />

<img width="671" height="473" alt="Screenshot 2026-10-29 222032" src="https://github.com/user-attachments/assets/1c46453c-0269-464f-b59f-27b33e88168b" />

<img width="653" height="517" alt="Screenshot 2026-10-29 222043" src="https://github.com/user-attachments/assets/54b29d3d-4c36-4e6b-a300-c9788273836e" />

---

##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
