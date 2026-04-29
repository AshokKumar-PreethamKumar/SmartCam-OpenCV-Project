# SmartCam-OpenCV-Project

# Image Capture and Video Processing Using OpenCV

## Aim

To develop a Python program using OpenCV to capture images from a webcam and perform real-time video processing operations such as displaying, resizing, and rotating frames.

---

## Technologies Used

* Python 3.x
* OpenCV (`cv2`)
* Matplotlib
* Jupyter Notebook / VS Code

---

## Features

* Capture image from webcam
* Save captured frame as JPG file
* Display live video stream
* Resize video frames (640 × 480)
* Rotate video frames (90° clockwise)

---


## How to Run

1. Open Jupyter Notebook
2. Run cells step-by-step
3. Allow camera access
4. Execute each section:

   * Capture image
   * Display video
   * Resize video
   * Rotate video

---

## 🧠 Algorithm

1. Import required libraries
2. Initialize webcam using `cv2.VideoCapture(0)`
3. Capture frame using `cap.read()`
4. Save frame using `cv2.imwrite()`
5. Convert BGR → RGB for display
6. Display using Matplotlib
7. Resize frame using `cv2.resize()`
8. Rotate frame using `cv2.rotate()`
9. Release camera using `cap.release()`

---

##  Output

### 1️) Captured Image

* Image saved as `captured_image.jpg`


Code:
```py
# Display the captured frame using Matplotlib
if ret:
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    
    plt.imshow(frame_rgb)
    plt.title("Captured Image")
    plt.axis('off')
    plt.show()
```
<img width="617" height="460" alt="image" src="https://github.com/user-attachments/assets/d6dd7580-a1fc-40bb-9cb5-3ba6b46fe562" />

### 2️) Live Video Display

* Webcam video shown in real-time

Code:
```py
# To Display the video

for i in range(30):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.title("Live Video")
    plt.axis('off')
    plt.show()
```
<img width="609" height="453" alt="image" src="https://github.com/user-attachments/assets/7b1e0e49-4de1-43f8-9577-77ec2c1a8ef3" />


### 3️) Resized Video

* Video resized to **640 × 480 resolution**

Code:
```py
# Display the video by resizing the window

for i in range(30):   # runs only 30 frames
    ret, frame = cap.read()

    if not ret:
        break

    resized = cv2.resize(frame, (640, 480))
    resized_rgb = cv2.cvtColor(resized, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(resized_rgb)
    plt.title("Resized Video (640x480)")
    plt.axis('off')
    plt.show()
```
<img width="644" height="459" alt="image" src="https://github.com/user-attachments/assets/de247d10-d2fc-47f7-a469-9cf3879fa632" />

### 4️) Rotated Video

* Video rotated **90° clockwise**

Code:
```py
# Rotate and display the video

for i in range(30):   # runs only 30 frames
    ret, frame = cap.read()

    if not ret:
        break

    rotated = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    rotated_rgb = cv2.cvtColor(rotated, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(rotated_rgb)
    plt.title("Rotated Video (90°)")
    plt.axis('off')
    plt.show()
```
<img width="355" height="452" alt="image" src="https://github.com/user-attachments/assets/37508489-ca5e-4f61-a8be-9bb64ef6826d" />

## Result

The program successfully captures images from the webcam and performs real-time video processing operations including display, resizing, and rotation using OpenCV.

---
