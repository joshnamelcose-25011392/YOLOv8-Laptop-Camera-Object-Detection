# YOLOv8-Laptop-Camera-Object-Detection

# Reference no: 212225230118
# Developed by: Joshna.M

## Aim
To access the laptop camera, capture an image, and detect objects using YOLOv8.

## Requirements
- Anaconda
- Jupyter Notebook
- Python
- OpenCV
- Matplotlib
- YOLOv8
- Laptop Camera

## Steps
1. Open **Jupyter Notebook** using Anaconda.
2. Import the required libraries.
3. Load the pretrained **YOLOv8 Nano model**.
4. Access the **laptop camera** using OpenCV.
5. Wait for **5 seconds** and capture an image.
6. Display the captured image.
7. Apply **YOLOv8 object detection**.
8. Display the detected image with **bounding boxes and labels**.
9. Repeat the experiment with **3 different scenes**.
10. Save the original and detected images.

## Algorithm

Laptop Camera
↓
Capture Image
↓
Display Image
↓
Load YOLOv8 Model
↓
YOLOv8 Detection
↓
Draw Bounding Boxes
↓
Display Detected Objects

## Program
### Step 1: Import Required Libraries

```python
import cv2
import matplotlib.pyplot as plt
from ultralytics import YOLO
import time
```
### Step 2: Load YOLOv8 Model
```
model = YOLO("yolov8n.pt")
print("YOLOv8 model loaded successfully!")
```
### Step 3: Open Laptop Camera
```
cap = cv2.VideoCapture(0)
if cap.isOpened():
    print("Laptop camera opened successfully!")
else:
    print("Error: Could not open camera.")
```
### Step 4: Capture Image
```
print("Get ready...")
print("Capturing image in 5 seconds...")
time.sleep(5)
ret, frame = cap.read()
if ret:
    print("Image captured successfully!")
else:
    print("Failed to capture image.")
```
### Step 5: Display Captured Image
```
captured_image = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
plt.figure(figsize=(10, 6))
plt.imshow(captured_image)
plt.axis("off")
plt.title("Captured Image")
plt.show()
```
### Step 6: Perform Object Detection
```
results = model(captured_image)
print("Object detection completed!")
```
### Step 7: Display Detected Image
```
detected_image = results[0].plot()
plt.figure(figsize=(10, 6))
plt.imshow(detected_image)
plt.axis("off")
plt.title("YOLOv8 Object Detection")
plt.show()
```
### Step 8: Release Camera
```
cap.release()
print("Camera released successfully!")
```
## Task
- Capture your own images using the laptop camera.
- Detect the objects present in the images.
- Display the original and detected images.
- Perform the experiment with **3 different scenes**.
- Save the captured and YOLOv8 output images.

## Submission
- Jupyter Notebook (`.ipynb`)
- Original captured images
- YOLOv8 output images
- Screenshot of the final result
- README file

## Conclusion
The experiment demonstrates how a laptop camera can be integrated with OpenCV and YOLOv8 to capture images and perform object detection. The detected objects are visualized using bounding boxes and labels.
