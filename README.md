# Image-Handling-and-pixel-Transformation

## Aim

To develop a Python program using the OpenCV library to read, display, and save an image, and to perform pixel-level transformations such as brightness and contrast adjustment, along with color channel splitting.

## Software Required

Laptop with Jupyter lab

## Algorithm

1. Start the experiment by importing the required libraries such as OpenCV and NumPy for performing image processing operations.

2. Load the input image from the specified file path using OpenCV functions like cv2.imread().

3. Display the loaded image on the screen using cv2.imshow() to verify that the image is read correctly.

4. Save the image to a new file using cv2.imwrite() to understand image writing operations.

5. Perform brightness adjustment by increasing or decreasing pixel intensity values of the image.

6. Apply contrast adjustment using suitable scaling techniques to enhance or reduce image contrast.

7. Split the image into individual color channels (Red, Green, Blue) using OpenCV functions.

8. Display each color channel separately to observe the effect of channel separation.

9. Combine or analyse the processed outputs as required for understanding transformations.

10. End the experiment.

## Program
```
Experiment 1: Image Handling and Pixel Transformations Using OpenCV

Developed By : Naveen Kumar E

Register Number : 212224230181
```
### Step1:
#### Load an image from your local directory and display it.
```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread(r"D:\Digital Image Processing Techniques\WhatsApp Unknown 2026-04-20 at 14.04.31\Qno. 1.jpeg")

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

print(img)

image = cv2.imread('Qno. 1.jpg')

plt.imshow(img_rgb, cmap='viridis') 
plt.title("Original Image")
plt.axis('off')  
plt.show()
```

### Step2:
#### o Draw a line from the top-left to the bottom-right of the image.
#### o Draw a circle at the center of the image. 
#### o Draw a rectangle around a specific region of interest in the image. 
#### o Add the text "OpenCV Drawing" at the top-left corner of the image.

#### Draw a line from the top-left to the bottom-right of the image

```python
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2)

plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```
#### Draw a circle at the center of the image.

```python
image = cv2.imread('Qno. 1.jpg') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10)

plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

#### Draw a rectangle around  the whole image

```python
image = cv2.imread('Qno. 1.jpg') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape

rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  

plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

#### Add the text "OpenCV Drawing" at the top-left corner of the image.

```python
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)

plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
### Step3:

#### o Convert the image from RGB to HSV and display it.
    
#### o Convert the image from RGB to GRAY and display it. 

#### o Convert the image from RGB to YCrCb and display it. 
    
#### o Convert the HSV image back to RGB and display it.

```python
image = cv2.imread(r"D:\Digital Image Processing Techniques\WhatsApp Unknown 2026-04-20 at 14.04.31\Qno. 1.jpeg")

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")

image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")

image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")

image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")

image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```
### Step4:
#### o Access and print the value of the pixel at coordinates (100, 100). 

#### o Modify the color of the pixel at (200, 200) to white.

```python
image[200:500, 200:500] = [255, 255, 255]

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

### Step5:

#### o Resize the original image to half its size and display it.

~~~python
image = cv2.imread(r"D:\Digital Image Processing Techniques\WhatsApp Unknown 2026-04-20 at 14.04.31\Qno. 1.jpeg")

image.shape

resized_image_rgb = cv2.resize(image, (768 // 2, 600 // 2))

resized_image_rgb.shape

plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
~~~

### Step6:
#### o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

```python
roi = image[50:350, 50:350]

roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

### Step7:
#### o Flip the original image horizontally and display it. 

#### o Flip the original image vertically and display it.

```python
flipped_horizontally = cv2.flip(image, 1)

flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")

flipped_vertically = cv2.flip(image, 0)

flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
### Step 8
#### o Save the final modified image to your local directory.

## Output

<img width="796" height="605" alt="image" src="https://github.com/user-attachments/assets/272b61b1-5ee0-4b1a-82f2-133b6e72441b" />


<img width="493" height="409" alt="04c6902d-ba9a-414a-81bc-20d90c65da96" src="https://github.com/user-attachments/assets/5020dbbb-367f-41b6-9e9c-58e730af6ec2" />

<img width="896" height="93" alt="image" src="https://github.com/user-attachments/assets/ee387f71-2a08-44b4-aa66-ea5490f1626e" />

<img width="493" height="409" alt="8e34314a-3e2b-4a94-97c6-39688f83e72b" src="https://github.com/user-attachments/assets/23707a2c-edff-499b-9daf-49165a49ff11" />

<img width="493" height="409" alt="d9f43c52-263f-4609-8dd2-5f3f07247630" src="https://github.com/user-attachments/assets/18846b28-ab6e-40ff-87ef-6605d9ad63c6" />

<img width="493" height="409" alt="b79b3cbc-0f12-435e-afa5-d75a35684e74" src="https://github.com/user-attachments/assets/64344d50-29d1-4837-9909-965eafc2e584" />

<img width="493" height="409" alt="5d95b520-952e-49a0-a3e8-f2d7ed04a43e" src="https://github.com/user-attachments/assets/eead82db-add8-4ec5-843a-361cddbba19a" />

<img width="493" height="409" alt="fdffca94-2737-489f-b5c5-b4e0912a83e8" src="https://github.com/user-attachments/assets/9fd57d6e-2d37-4f7d-bc6d-6005756bb612" />

<img width="493" height="409" alt="9737757c-7805-4149-87eb-d8a96591140c" src="https://github.com/user-attachments/assets/0a4d1f07-2737-4eb2-872e-90f2d4425c5c" />

<img width="493" height="409" alt="e4edcf4b-ad60-434e-bcb5-434aadac9987" src="https://github.com/user-attachments/assets/86d78688-ead3-43e1-8f11-7f98d55eb1da" />

<img width="493" height="409" alt="e4dc776a-e51f-4d1e-ad4c-9d83171c0b09" src="https://github.com/user-attachments/assets/481d7119-5c24-4863-a246-564ce534e758" />

<img width="493" height="409" alt="2b388b7e-c3a7-45ac-91f8-850d18d786fb" src="https://github.com/user-attachments/assets/3feef98d-e373-4c1d-9853-71700a5c5929" />

<img width="493" height="409" alt="6001518f-acd7-42d8-9108-0475bdcdb6ac" src="https://github.com/user-attachments/assets/63e8e5af-1c4d-4f2a-bd69-d071cde1f3be" />

<img width="493" height="409" alt="d1675785-deb6-4e77-9766-c99b0a506010" src="https://github.com/user-attachments/assets/1c112eff-b49e-4374-ad5b-5bb47a29f30b" />

<img width="389" height="409" alt="e323e2b4-2c73-4fee-911d-72f5d302607a" src="https://github.com/user-attachments/assets/9dbba356-2bda-40c8-8559-fa22c302ca06" />

<img width="493" height="409" alt="0695224b-d57b-4072-ab31-2eb97a1cc939" src="https://github.com/user-attachments/assets/2434b9fb-d7ff-4a37-8e6a-d78cc97a2e67" />

<img width="493" height="409" alt="bbef86ae-bbd7-4338-9c5f-dc7fc75979fe" src="https://github.com/user-attachments/assets/e39d63f4-cb9e-43e1-a199-650f45379065" />
