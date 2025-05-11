# Advanced Self Driving - A Low Cost Driver Assistance Software

An interactive Python/Tkinter application demonstrating real‑time lane detection, object detection, driver assistance features, and developer/learner modes with audio feedback and dataset recording.

## Features

- **Lane Detection & Smoothing**  
  - Perspective transform, color thresholding (white & yellow), sliding-window search  
  - Exponential smoothing of polynomial fits  
  - Automatic mode switching between straight and curved segments  

- **Lane Departure Warning**  
  - Calculates vehicle offset from lane center  
  - Audio and visual warnings when drifting too far  

- **Object Detection (YOLOv8)**  
  - Real‑time bounding boxes and counts for people, cars, motorcycles, etc.  
  - Developer log of object counts  

- **Driver Assistance Mode**  
  - Combines lane detection and object detection  
  - Unified toggle for full assistance  

- **Developer Mode**  
  - Live FPS counter  
  - Matplotlib plots of lane indicators and object counts  
  - Live map view (requires internet) via `tkintermapview`  
  - Developer log widget  

- **Learner Mode**  
  - Simplified object detection with placeholder for custom learner warnings  

- **Dataset Recording**  
  - Save frames, lane fits, and object counts to `./recorded_dataset/metadata.csv`  
  - Timestamped image captures  

- **Text‑to‑Speech Notifications**  
  - Uses `pyttsx3` for audible status updates and warnings  

## Requirements

- Python 3.7+  
- [OpenCV](https://pypi.org/project/opencv-python/)  
- [Pillow](https://pypi.org/project/Pillow/)  
- [NumPy](https://pypi.org/project/numpy/)  
- [Ultralytics YOLO](https://pypi.org/project/ultralytics/) (for YOLOv8)  
- [tkintermapview](https://pypi.org/project/tkintermapview/)  
- [Matplotlib](https://pypi.org/project/matplotlib/)  
- [scikit-learn](https://pypi.org/project/scikit-learn/)  
- [pyttsx3](https://pypi.org/project/pyttsx3/)

## Versions

- 1.0: Baseline implementation featuring discrete lane detection algorithms (Canny, Sobel, Hough, Kalman) accessible via separate GUI buttons.

Below is the Version 1.0 prototype - 
![Version 1.0](<Version 1.0 (Example 1).png>)

- 1.1: User interface enhancements and integration of fail safe mechanisms (e.g., threshold hysteresis).

- 1.2: Algorithmic refinements aimed at improving detection accuracy; encountered intermittent failures under low contrast conditions. 

- 2.0: Addition of a YOLO based object detection module, introduced via a dedicated “box” control.

- 2.1: Consolidation of lane detection into a unified interface, decluttering the GUI while retaining object detection functionality.

- 2.2: Comprehensive overhaul of the lane detection pipeline—incorporating inverse perspective mapping, sliding window search, polynomial fitting, and exponential smoothing—and the introduction of Learner and Developer modes, an FPS counter, and preliminary live map integration.

Below is the Version 2.2 prototype (example 1)- 
![Version 2.2](<Version 2.2 (Example 1).png>)

Below is the Version 2.2 prototype (example 2)- 
![Version 2.2](<Version 2.2 (Example 2).png>)

- 2.3: Addition of dataset recording; Save frames, lane fits, and object counts to `./recorded_dataset/metadata.csv`and Timestamped image captures 

Below is the Version 2.3 prototype - 
![Version 2.3](<Version 2.3 (Example 1).png>)
