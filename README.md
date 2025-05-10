<p align="center">
  <img src="docs/banner.png" alt="Advanced Self Driving" width="700"/>
</p>

<p align="center">
  <a href="https://github.com/yourusername/advanced-self-driving/actions"><img src="https://img.shields.io/github/actions/workflow/status/yourusername/advanced-self-driving/ci.yml?branch=main" alt="CI Status"></a>
  <a href="https://pypi.org/project/advanced-self-driving/"><img src="https://img.shields.io/pypi/v/advanced-self-driving" alt="PyPI Version"></a>
  <a href="#license"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License"></a>
  <a href="#requirements"><img src="https://img.shields.io/badge/python-3.7%2B-blue" alt="Python 3.7+"></a>
</p>

---

## 📋 Table of Contents

* [✨ Features](#-features)
* [🖼️ Demo](#️-demo)
* [⚙️ Requirements](#️-requirements)
* [🚀 Quick Start](#-quick-start)
* [🛠️ Usage & Modes](#️-usage--modes)

  * [▶️ Live Preview](#️-live-preview)
  * [🔧 Developer Mode](#️-developer-mode)
  * [🎓 Learner Mode](#️-learner-mode)
* [🗃️ Dataset Recording](#️-dataset-recording)
* [❓ Troubleshooting](#-troubleshooting)
* [🤝 Contributing](#-contributing)
* [📄 License](#-license)
* [🙏 Acknowledgments](#-acknowledgments)

---

## ✨ Features

<p align="center">
  <img src="docs/icons/lane.png" alt="Lane" width="48"/>  
  <img src="docs/icons/object.png" alt="Object" width="48"/>  
  <img src="docs/icons/assistant.png" alt="Assistant" width="48"/>  
  <img src="docs/icons/developer.png" alt="Developer" width="48"/>  
  <img src="docs/icons/learner.png" alt="Learner" width="48"/>  
  <img src="docs/icons/tts.png" alt="TTS" width="48"/>  
</p>

* **🚧 Lane Detection & Smoothing**

  * Perspective transform, white & yellow thresholding
  * Sliding-window search + RANSAC for robust fits
  * Exponential smoothing of lane curves
  * Auto mode-switching: *straight* ↔ *curved*

* **⚠️ Lane Departure Warning**

  * Calculates offset from lane center
  * On-screen & audio alerts via **pyttsx3**

* **🎯 Object Detection (YOLOv8)**

  * Realtime bounding boxes & counts (cars, people, bikes…)
  * Developer log of detection counts

* **🛡️ Driver Assistance Mode**

  * Unified lane + object detection
  * Single toggle for full driving aid

* **👨‍💻 Developer Mode**

  <details>
    <summary>Click to expand 🚀</summary>

  * Live FPS counter
  * Matplotlib plots of lane & object stats
  * Embedded interactive map (via `tkintermapview`)
  * Scrollable developer log widget

  </details>

* **🎓 Learner Mode**

  * Simplified detection + custom learner alerts

* **📦 Dataset Recording**

  * Save frames, lane fits & object counts
  * Timestamped CSV & image dumps

* **🔊 Text‑to‑Speech**

  * Audible status updates & warnings

---

## 🖼️ Demo

<p align="center">
  <!-- Replace with actual GIF/demo -->
  <img src="docs/demo.gif" alt="Demo" width="800"/>
</p>

---

## ⚙️ Requirements

Install via pip:

```bash
pip install -r requirements.txt
```

<details>
  <summary>Python Packages</summary>

```
opencv-python
Pillow
numpy
ultralytics      # YOLOv8
tkintermapview
matplotlib
scikit-learn
pyttsx3
```

</details>

---

## 🚀 Quick Start

1. **Clone the repo**

   ```bash
   git clone https://github.com/yourusername/advanced-self-driving.git
   cd advanced-self-driving
   ```

2. **Download the YOLOv8 model**

   ```bash
   # Place yolov8n.pt here, or update path in main.py
   wget https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8n.pt
   ```

3. **Run the application**

   ```bash
   python main.py
   ```

---

## 🛠️ Usage & Modes

### ▶️ Live Preview

| Button                         | Action                          |
| ------------------------------ | ------------------------------- |
| **Start Camera**               | Begin video capture             |
| **Activate Lane Assistance**   | Show lanes & departure warnings |
| **Activate Object Detection**  | Show YOLO boxes & counts        |
| **Activate Driver Assistance** | Combined lane + object mode     |

### 🔧 Developer Mode

Toggle **Activate Developer Mode** to display:

* **FPS** counter
* **Plots** of lane indicator & counts
* **Interactive Map** centered on Hyderabad
* **Console Log** of detection stats

<details>
  <summary>Sample Plot</summary>
  <img src="docs/screenshots/plot.png" alt="Developer Plot" width="600"/>
</details>

### 🎓 Learner Mode

Toggle **Activate Learner Mode** for a simplified interface. Customize learner alerts by editing the placeholder in `main.py`.

---

## 🗃️ Dataset Recording

Click **Start Recording** to:

* Save each frame as `frame_YYYYMMDD_HHMMSS.png` in `./recorded_dataset/`
* Append metadata (timestamp, mode, lane fits, object counts) to `metadata.csv`

<details>
  <summary>Sample Metadata</summary>

| timestamp        | filename                    | mode   | left\_fit              | right\_fit              | obj\_counts       |
| ---------------- | --------------------------- | ------ | ---------------------- | ----------------------- | ----------------- |
| 20250511\_153022 | frame\_20250511\_153022.png | driver | `[1.2e-4, -0.35, 250]` | `[1.1e-4, -0.33, 1020]` | `{0:2, 2:1, 3:3}` |

</details>

---

## ❓ Troubleshooting

* **Camera not detected?**

  * Ensure no other app uses the webcam.
  * Test with simple OpenCV capture script.

* **Map tiles not loading?**

  * Check internet connectivity.
  * Verify `tkintermapview` tile server settings.

* **No audio on warnings?**

  * Confirm `pyttsx3` voices installed (e.g., `espeak` on Linux).

---

## 🤝 Contributing

We ❤️ contributions!

1. Fork the repo
2. Create a feature branch
3. Submit a PR with clear description

Please follow the [Code of Conduct](CODE_OF_CONDUCT.md).

---

## 📄 License

Distributed under the MIT License. See [LICENSE](LICENSE) for details.

---

## 🙏 Acknowledgments

* Lane detection inspired by **Udacity Self‑Driving Car Nanodegree**
* Object detection courtesy of **Ultralytics YOLOv8**
* Map widget by **tkintermapview**
* TTS powered by **pyttsx3**

---

<p align="center">
  Made with ❤️ by Your Name
</p>
