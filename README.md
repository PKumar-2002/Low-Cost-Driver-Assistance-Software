**1. Description**

This project is an **Advanced Self-Driving** demonstration application built with Python and Tkinter. It integrates real‑time video capture, lane detection, object detection (using YOLOv8), developer and learner modes, text‑to‑speech warnings, and an interactive map widget. Key features include:

* **Lane Detection & Smoothing**: Detects lane lines via perspective warp, color thresholding, sliding windows, RANSAC for robust fitting, and applies exponential smoothing to reduce jitter.
* **Lane Departure Warnings**: Calculates vehicle offset from lane center and issues audio/visual warnings when crossing lane boundaries.
* **Object Detection**: Runs a YOLOv8 model on each frame to detect and count classes like cars, persons, motorbikes, etc., drawing bounding boxes and labels.
* **Driver Assistance Mode**: Combines lane detection and object detection for a comprehensive assistance mode.
* **Developer Mode**: Displays real‑time FPS, developer logs, and matplotlib plots of lane indicators and object counts, alongside a live-updating map (TkinterMapView).
* **Learner Mode**: A simplified mode (placeholder for customized learner warnings).
* **Dataset Recording**: Optionally records frames, fitted lane coefficients, and object counts to a timestamped CSV and saves images for offline analysis.
* **Text‑to‑Speech**: Uses `pyttsx3` to announce status changes and warnings aloud.
* **Customizable UI**: Fully interactive Tkinter interface with buttons to toggle each feature.

---

**2. README.md**

````markdown
# Advanced Self Driving

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

## Installation

1. **Clone the repository**  
   ```bash
   git clone https://github.com/yourusername/advanced-self-driving.git
   cd advanced-self-driving
````

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Download YOLOv8 model**
   Place `yolov8n.pt` in the project root directory, or update the path in the script:

   ```python
   yolo_model = YOLO("path/to/yolov8n.pt")
   ```

## Usage

```bash
python main.py
```

* **Start/Stop Camera**: Click **Start Camera** to begin video capture.
* **Lane Assistance**: Toggle **Activate Lane Assistance** to see lane overlays and warnings.
* **Object Detection**: Toggle **Activate Object Detection** for YOLOv8 bounding boxes.
* **Driver Assistance**: Toggle **Activate Driver Assistance** to run both lane and object detection together.
* **Developer Mode**: Toggle **Activate Developer Mode** to view FPS, logs, plots, and map.
* **Learner Mode**: Toggle **Activate Learner Mode** for a learner‑focused interface.
* **Recording**: Toggle **Start Recording** to save frames and metadata in `./recorded_dataset`.

## Project Structure

```
advanced-self-driving/
├── main.py
├── yolov8n.pt
├── requirements.txt
├── background.png
├── road.png
├── smart-car.png
├── recorded_dataset/
│   └── metadata.csv
└── README.md
```

## Troubleshooting

* **Camera not found**: Ensure your webcam is accessible and not in use by another application.
* **Map not loading**: `tkintermapview` requires internet access and valid tile server URLs.
* **TTS issues**: Verify `pyttsx3` is installed and your system has a speech engine.

## License

This project is released under the [MIT License](LICENSE).

## Acknowledgments

* Lane detection inspired by Udacity Self‐Driving Car Nanodegree projects
* YOLOv8 by Ultralytics
* Map widget by `tkintermapview`

```

This README provides an overview, setup instructions, usage guide, and project structure to help you get started quickly.
```
