# EXP.2-RECORD-IMAGE-ACQUISTION-USING-WEB-CAMERA


## NAME: THARSHINI M
## REG.NO: 212224230287

## AIM

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the captured frame as a JPG file.
2. Display the live video.
3. Display the video by resizing the frame.
4. Rotate and display the video.

## SOFTWARE REQUIRED

- Anaconda – Python 3.7
- Jupyter Notebook
- OpenCV (`cv2`)
- Matplotlib
- IPython

## ALGORITHM

## Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

## Step 2:
Capture frames from the webcam.

## Step 3:
Save a captured frame as a JPG image using `cv2.imwrite()`.

## Step 4:
Display the live video by capturing and displaying frames continuously.

## Step 5:
Resize the captured frames using `cv2.resize()` and display the resized video.

## Step 6:
Rotate the video frames using `cv2.rotate()` and display the rotated video.

---

# PROGRAM

## i) Write the Frame as JPG File

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("Captured_frame.jpg", frame)

cap.release()

captured_image = cv2.imread('Captured_frame.jpg')

plt.imshow(captured_image[:, :, ::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

## ii) Display the Video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```

## iii) Display the Video by Resizing the Window

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(
        resized_frame,
        cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```

## iv) Rotate and Display the Video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(
        frame,
        cv2.ROTATE_90_CLOCKWISE
    )

    frame_rgb = cv2.cvtColor(
        rotated_frame,
        cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

# OUTPUT

### i) Write the Frame as JPG Image
The captured webcam frame is successfully saved as `Captured_frame.jpg`.
<img width="381" height="310" alt="{78825090-8DEC-478B-B532-34AFB3C69C21}" src="https://github.com/user-attachments/assets/9cbd5738-61af-4c2e-b773-4ad5cebf5b71" />


### ii) Display the Video
The live webcam video is displayed using Matplotlib.

<img width="383" height="290" alt="{9EB277FB-12A7-4001-B69C-1A311FFB01B9}" src="https://github.com/user-attachments/assets/d6f1fc8d-dd79-4537-b27c-e3648217f252" />


### iii) Display the Video by Resizing the Window
The video is displayed after resizing the frames to 100 × 150 pixels.

<img width="192" height="291" alt="{717AD47D-43EB-4647-9DAC-2C1A81CC51DA}" src="https://github.com/user-attachments/assets/49462d2a-a4d3-444f-aa8a-2f39fbebd0d4" />


### iv) Rotate and Display the Video
The video is displayed after rotating the frames 90° clockwise.

<img width="209" height="287" alt="{6FA67620-AF32-4269-B1A6-C98808AF8C85}" src="https://github.com/user-attachments/assets/ad3b844f-91f0-4209-a371-61cd3a48913a" />


---

## RESULT

Thus, an image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
