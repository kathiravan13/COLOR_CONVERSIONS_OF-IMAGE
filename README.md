# COLOR_CONVERSIONS_OF-IMAGE

#### Developed By: KATHIRAVAN P
#### Register Number: 212222230063
#### Date: 

## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) 	Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o	Draw a line from the top-left to the bottom-right of the image.
o	Draw a circle at the center of the image.
o	Draw a rectangle around a specific region of interest in the image.
o	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
o	Convert the image from RGB to HSV and display it.
o	Convert the image from RGB to GRAY and display it.
o	Convert the image from RGB to YCrCb and display it.
o	Convert the HSV image back to RGB and display it.

### Step4:
o	Access and print the value of the pixel at coordinates (100, 100).
o	Modify the color of the pixel at (200, 200) to white.

### Step5:
o	Resize the original image to half its size and display it.
### Step6:
o	Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o	Flip the original image horizontally and display it.
o	Flip the original image vertically and display it.

### Step8:
o	Save the final modified image to your local directory.

### i)Read and Display an Image

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image_path = 'dog.jpg' 
image = cv2.imread(image_path)
plt.figure(figsize=(10, 8))
plt.subplot(3, 3, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```

![Screenshot 2024-09-14 103812](https://github.com/user-attachments/assets/e8cfadac-3446-4949-8303-c9e220fb08fc)


### ii)Draw Shapes and Add Text

```
height, width, _ = img.shape

# Define start and stop points based on the image size
start = (9, 9)  # Slight offset from the top left corner
stop = (width - 9, height - 9)  # Slight offset from the bottom right corner

# Define the rectangle color and thickness
color = (100, 255, 100)
thickness = 9

# Draw the rectangle
res_img = cv2.rectangle(img, start, stop, color, thickness)

# Display the image with the rectangle
cv2.imshow('Image Window', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Get image dimensions
height, width, _ = img.shape

# Calculate the center of the image
center_coordinates = (width // 2, height // 2)

# Draw the circle at the center with a radius of 30 and thickness of 5
res = cv2.circle(img, center_coordinates, 30, (255, 0, 0), 5)

# Display the image with the circle
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-09-14 113857](https://github.com/user-attachments/assets/f901af05-c41b-4d37-8500-56f691bf2616)

![image](https://github.com/user-attachments/assets/a8f4c004-d0a2-47ae-a5be-3b1b7008c7d4)




### iii)Image Color Conversion
```
# Convert to HSV
image_hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
# Convert to GRAY
image_gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Convert to YCrCb
image_ycrcb = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
# Convert HSV back to RGB
image_rgb_from_hsv = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2BGR)


plt.subplot(3, 3, 3)
plt.imshow(cv2.cvtColor(image_hsv, cv2.COLOR_BGR2RGB))
plt.title('Image in HSV')
plt.axis('off')

plt.subplot(3, 3, 4)
plt.imshow(image_gray, cmap='gray')
plt.title('Image in GRAY')
plt.axis('off')

plt.subplot(3, 3, 5)
plt.imshow(cv2.cvtColor(image_ycrcb, cv2.COLOR_BGR2RGB))
plt.title('Image in YCrCb')
plt.axis('off')

plt.subplot(3, 3, 6)
plt.imshow(cv2.cvtColor(image_rgb_from_hsv, cv2.COLOR_BGR2RGB))
plt.title('HSV to RGB')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/be49b576-fb65-446e-bb34-e205b9995786)



### iv)Access and Manipulate Image Pixels

```
pixel_value = image[100, 100]  # Access pixel value at (100, 100)
print(f'Pixel value at (100, 100): {pixel_value}')
image[200, 200] = [255, 255, 255]  # Set pixel color at (200, 200) to white

# Display updated image with manipulated pixels
plt.subplot(3, 3, 7)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Image with Manipulated Pixels')
plt.axis('off')
```
![Screenshot 2024-09-14 134239](https://github.com/user-attachments/assets/9e6116d3-9a1a-492d-85df-9c50204d622d)
![Screenshot 2024-09-14 134512](https://github.com/user-attachments/assets/57e877cb-0634-408a-80c2-d12854dfeaec)
![Screenshot 2024-09-14 134533](https://github.com/user-attachments/assets/6bb4ad06-69b7-400d-b162-46d6ea820d46)



### v)Image Resizing
```
import cv2
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('dog.jpeg')  # Make sure to use the correct path to your image

# Resize the image
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))

# Setup for displaying the image using Matplotlib
plt.subplot(3, 3, 8)  # Positioning the image at the 8th subplot in a 3x3 grid
plt.imshow(cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title('Resized Image')
plt.axis('off')  # Turn off the axis

# Display the plot
plt.show()

```
![image](https://github.com/user-attachments/assets/06a3c1dd-6d76-431a-b520-0df0122f3f0d)



### vi)Image Cropping
```
import cv2
import matplotlib.pyplot as plt

# Load the image using cv2
image = cv2.imread('dog.jpeg')

# Crop the image (e.g., keeping the center portion)
# Let's say you want to crop the image by slicing from [y1:y2, x1:x2]
crop_img = image[100:400, 150:450]  # Adjust these numbers based on your image size

# Plot the cropped image
plt.subplot(3, 3, 8)  # Position it in the 8th subplot of a 3x3 grid
plt.imshow(cv2.cvtColor(crop_img, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for correct color display
plt.title('Cropped Image')
plt.axis('off')  # Hide the axes

plt.show()  # Display the cropped image


```
![image](https://github.com/user-attachments/assets/3a96eaa6-12d2-4985-ba83-3f11bd6ef127)


### vii)Image Flipping
```
import cv2
import matplotlib.pyplot as plt

# Load the image using cv2
image = cv2.imread('dog.jpeg')

# Flip the image
flipped_image_horizontal = cv2.flip(image, 1)  # Horizontal flip
flipped_image_vertical = cv2.flip(image, 0)    # Vertical flip

# Plot the horizontally and vertically flipped images
plt.figure(figsize=(10, 8))

# Horizontally flipped image
plt.subplot(1, 2, 1)  # 1 row, 2 columns, position 1
plt.imshow(cv2.cvtColor(flipped_image_horizontal, cv2.COLOR_BGR2RGB))
plt.title('Flipped Horizontally')
plt.axis('off')

# Vertically flipped image
plt.subplot(1, 2, 2)  # 1 row, 2 columns, position 2
plt.imshow(cv2.cvtColor(flipped_image_vertical, cv2.COLOR_BGR2RGB))
plt.title('Flipped Vertically')
plt.axis('off')

# Show both images
plt.show()

```

![image](https://github.com/user-attachments/assets/964f8251-45f6-43e4-a980-54808dea5101)
![image](https://github.com/user-attachments/assets/50856ed3-0652-4c87-86fe-c606853c9718)



### viii)Write and Save the Modified Image
```
output_path = 'modified_image.jpg'
cv2.imwrite(output_path, image)

plt.show()

```


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.







