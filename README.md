# 📷 Real-Time Face & Eye Detection using OpenCV

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green?logo=opencv&logoColor=white)](https://opencv.org)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.5%2B-orange)](https://matplotlib.org)

A computer vision pipeline built with Python and OpenCV designed for rapid object detection. This project demonstrates how to load static images, process real-time webcam video streams, convert color spaces, and apply trained Haar Cascade Classifiers to isolate and highlight human faces and eyes simultaneously.

---

## ✨ Key Features

- **Multi-Object Tracking:** Detects both the primary facial bounding region and up to two eyes in real-time.
- **Dynamic Graphical Overlays:** Draws automated bounding boxes (`cv2.rectangle`) with custom color coding (e.g., Green for face, Red for eyes) directly onto the output viewport.
- **Optimized Pre-processing:** Leverages grayscale conversions (`cv2.COLOR_BGR2GRAY`) and multi-scale tuning parameters (`scaleFactor=1.1`, `minNeighbors=5`) to balance precision and performance.
- **Custom Display Wrapper:** Contains built-in modular functions (`ishow`) for quick image debugging and window management using OpenCV's window lifecycles.

---

## 🛠️ Tech Stack & Dependencies

* **Language:** Python
* **Computer Vision Core:** `OpenCV (cv2)`
* **Visualization:** `Matplotlib (pyplot)`

---

## ⚙️ Installation & Setup

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name

Install Required Packages
Bash
pip install opencv-python matplotlib
3. Cascade Requirements
Make sure the standard pre-trained cascade files from OpenCV are placed in your working directory:

haarcascade_frontalface_default.xml

haarcascade_eye.xml

🚀 How It Works
The execution flow inside OpenCV.ipynb structured as follows:

Image Read & Helper: Loads an asset (e.g., 20.jpg) via cv2.imread and creates a controlled display loop that waits for user interaction (cv2.waitKey(0)).

Region Isolation: Processes the face coordinates first to extract a localized "Region of Interest" (ROI).

Sub-Features Analysis: Limits the eye searching cascade strictly inside the detected face ROI to reduce false positives and speed up computation.

Stream Escape: In the live tracking version, pressing the 0 key safely terminates the window loop and releases the runtime assets.

📊 Detection Logic Parameters
To prevent noise and false detections, the cascade uses optimized multi-scale configurations:

scaleFactor=1.1: Specifies how much the image size is reduced at each image scale layer.

minNeighbors=5: Specifies how many neighbors each candidate rectangle should have to retain it.

📝 Roadmap / Next Steps
[ ] Add real-time counting to track the total number of faces present in a single frame.

[ ] Implement a snapshot feature that saves cropped faces into a local directory when a key is pressed.

[ ] Optimize the pipeline using Local Binary Patterns (LBP) cascades for lower CPU usage on edge devices.

Developed by Amirali Afshariyan
