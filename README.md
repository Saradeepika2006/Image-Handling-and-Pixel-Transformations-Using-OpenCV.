# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** [MOPURI SARADEEPIKA]  
- **Register Number:** [212224040201]

  ### Ex. No. 01
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('thamana.webp', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
image = cv2.imread('thamana.webp') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (0, 255, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
image = cv2.imread('thamana.webp') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
image = cv2.imread('thamana.webp') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
image = cv2.imread('thamana.webp') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
image = cv2.imread('thamana.webp') 
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
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
image = cv2.imread('thamana.webp')
image.shape
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
image = cv2.imread('thamana.webp')
image.shape
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
image = cv2.imread('thamana.webp')
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
## Output:

<img width="635" height="507" alt="Screenshot 2026-08-07 110631" src="https://github.com/user-attachments/assets/35a3bde9-ef2d-4bbf-8fc4-ba8dc1019906" />
<img width="631" height="508" alt="Screenshot 2026-08-07 110711" src="https://github.com/user-attachments/assets/7f933170-ae8f-4d87-b3f5-581928afd465" />

<img width="632" height="505" alt="Screenshot 2026-08-07 110738" src="https://github.com/user-attachments/assets/f87ba1c0-381e-446c-b4bb-b631e9a6ce42" />

<img width="631" height="502" alt="Screenshot 2026-08-07 110934" src="https://github.com/user-attachments/assets/086b1b26-c3c6-4a8c-a352-287f64ec31ca" />

<img width="635" height="498" alt="Screenshot 2026-08-07 111000" src="https://github.com/user-attachments/assets/4b878bf8-349c-4be6-ae4a-082c439ce268" />

<img width="635" height="498" alt="Screenshot 2026-08-07 111000" src="https://github.com/user-attachments/assets/053fb92f-ebf4-44cf-be79-b668d6ca5613" />

<img width="633" height="510" alt="Screenshot 2026-08-07 111203" src="https://github.com/user-attachments/assets/e7b4fc12-9af7-40d9-984f-b43d85ff795f" />

<img width="635" height="503" alt="Screenshot 2026-08-07 111242" src="https://github.com/user-attachments/assets/db4a2089-fd4d-4106-92cb-45cb484c45da" />

<img width="630" height="507" alt="Screenshot 2026-08-07 111304" src="https://github.com/user-attachments/assets/740bcfe9-a227-4368-a59f-017f1160bf18" />

<img width="632" height="512" alt="Screenshot 2026-08-07 111325" src="https://github.com/user-attachments/assets/396304ce-d324-4bb6-b227-a0565453a17d" />

<img width="605" height="505" alt="Screenshot 2026-08-07 111347" src="https://github.com/user-attachments/assets/9980811c-f5a7-4c79-a3f4-209f6b24af81" />

<img width="481" height="506" alt="Screenshot 2026-08-07 111421" src="https://github.com/user-attachments/assets/77441214-bb82-4734-b98e-4fe5147c8c96" />

<img width="632" height="505" alt="Screenshot 2026-08-07 111440" src="https://github.com/user-attachments/assets/7b9a4149-5634-4617-939b-5c80d48bbe2c" />

<img width="635" height="512" alt="Screenshot 2026-08-07 111503" src="https://github.com/user-attachments/assets/9b1dec98-2825-413a-9c8a-c3229bff397c" />
```
## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.


