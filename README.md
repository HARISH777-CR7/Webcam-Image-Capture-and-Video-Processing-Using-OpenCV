# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program

### Developed By:
**Name:** HARISH K

### Register No:
212225230094

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`
```
import cv2

cap = cv2.VideoCapture(0)
if not cap.isOpened():
    raise RuntimeError("Cannot open webcam")

ret, frame = cap.read()          # capture a single frame
if ret:
    cv2.imwrite("captured_image.jpg", frame)
    print("Captured image is saved as captured_image.jpg")
else:
    print("Failed to capture frame")

cap.release()
```
### ii) Display the video
Live webcam video is displayed
```
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    if not ret:
        break
    cv2.imshow("Live Video", frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```
### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
```
import cv2

cap = cv2.VideoCapture(0)

cv2.namedWindow("Resized Video", cv2.WINDOW_NORMAL)   # allows the window to be resized
cv2.resizeWindow("Resized Video", 640, 480)

while True:
    ret, frame = cap.read()
    if not ret:
        break
    cv2.imshow("Resized Video", frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```
### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
```
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    if not ret:
        break

    frame = cv2.resize(frame, (640, 480))                 # resize to 640 x 480
    rotated = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)  # rotate 90° clockwise

    cv2.imshow("Rotated Video (90° Clockwise)", rotated)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```
---

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`
<img width="785" height="596" alt="image" src="https://github.com/user-attachments/assets/277a80d4-f7da-4008-a696-aee687959897" />

### ii) Display the video
Live webcam video is displayed
<img width="792" height="637" alt="Screenshot 2026-10-31 171806" src="https://github.com/user-attachments/assets/b641201b-5f78-4844-9d29-a92cdadcc21a" />

### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
<img width="790" height="630" alt="Screenshot 2026-10-31 171837" src="https://github.com/user-attachments/assets/f1c7fc45-f130-4753-9181-b4d93fb91a03" />

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

<img width="587" height="827" alt="Screenshot 2026-10-31 171939" src="https://github.com/user-attachments/assets/8305dcc2-0d1b-4c4b-a471-bec29f37e407" />

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
