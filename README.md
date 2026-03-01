# 🖐️ Hand Tracking & Finger Counter using MediaPipe and OpenCV

This project is a real-time hand tracking and finger counting system built using **Python**, **OpenCV**, and **MediaPipe**.

It detects one or two hands from your webcam, extracts the 21 hand landmarks, and determines how many fingers are raised.

---

## 🚀 Features

- Real-time hand detection
- 21 landmark tracking per hand
- Finger state detection (open / closed)
- Total number of raised fingers calculation
- Works with one or two hands
- Live webcam visualization

---

## 🧠 How It Works

### 1️⃣ Hand Detection  
We use MediaPipe Hands to detect and track hands in real time.

Each detected hand provides **21 landmarks**, representing key points of the hand:

- 0 → Wrist  
- 4 → Thumb tip  
- 8 → Index tip  
- 12 → Middle tip  
- 16 → Ring tip  
- 20 → Pinky tip  

---

### 2️⃣ Coordinate System (Important)

In OpenCV:

- (0,0) is located at the **top-left corner**
- X increases → to the **right**
- Y increases → **downwards**

This is crucial for finger detection logic.

---

### 3️⃣ Finger Detection Logic

- The thumb is detected using the **X-axis comparison** (because it moves sideways).
- Other fingers are detected using the **Y-axis comparison**:
  
If the fingertip Y coordinate is **smaller** than the lower joint Y coordinate,  
the finger is considered **raised**.

Example logic:

```
if points[8][1] < points[6][1]:
    finger_is_up = True
```

---

## 🛠️ Technologies Used

- Python 3.x
- OpenCV
- MediaPipe
- NumPy (optional)

---

Install dependencies:

```
pip install opencv-python mediapipe numpy
```

---

Controls:

- Press **Q** → Quit
- Press **A** → Capture current frame

---

## 🎯 Future Improvements

- Gesture recognition (👍 ✌️ 👌 ✋)
- Handedness detection (Left / Right)
- Machine learning gesture classifier
- Virtual mouse control
- Sign language recognition

---

## 📸 Example Output

- Hand landmarks drawn in real-time
- Finger count printed in console
- Smooth tracking with confidence filtering

---

## 💡 Learning Goals

This project demonstrates:

- Real-time computer vision
- Coordinate system understanding
- Landmark-based gesture logic
- Frame-by-frame data processing

---

## ⭐ If you like this project

Give it a star on GitHub!
