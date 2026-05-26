# OpenCV & Computer Vision Course

A comprehensive collection of computer vision modules and learning materials based on OpenCV and advanced deep learning frameworks. This repository contains practical implementations of various computer vision techniques including face detection, hand tracking, pose estimation, and more.

## Overview

This project is designed as a learning resource for understanding and implementing computer vision algorithms. It combines classic OpenCV techniques with modern AI models powered by MediaPipe, YOLO, and PyTorch for state-of-the-art results.

## Features

- **Face Detection**: Multi-face detection and facial feature extraction
- **Hand Tracking**: Real-time hand gesture recognition and tracking using MediaPipe
- **Pose Estimation**: Human pose detection with joint and skeleton tracking
- **Object Detection**: YOLO-based object detection capabilities
- **Image Processing**: Foundational computer vision techniques and filters
- **Video Processing**: Frame-by-frame video analysis and real-time processing

## Project Structure

```
├── src/
│   ├── computer_vision_modules/       # Core OpenCV-based modules
│   ├── mediapipe_modules/             # MediaPipe-based implementations
│   └── test/                          # Module testing
├── training/
│   ├── basic_codes/                   # Fundamental computer vision code examples
│   ├── face_detection/                # Face detection implementations
│   ├── hand_tracking/                 # Hand tracking code
│   └── pose_estimation/               # Pose estimation code
├── tests/
│   ├── hand_tracking_main.py          # Hand tracking test script
│   └── pose_detection_main.py         # Pose detection test script
├── resources/
│   ├── faces/                         # Sample face images
│   ├── photos/                        # Sample photos for testing
│   ├── videos/                        # Sample video files
│   └── gesture_recognizer.task        # Pre-trained gesture model
└── requirements.txt                   # Project dependencies
```

## Requirements

- Python 3.8+
- OpenCV 4.13.0
- MediaPipe 0.10.21
- PyTorch 2.10.0
- NumPy 2.4.3
- Matplotlib 3.10.8
- YOLO (Ultralytics) 8.4.22

All dependencies are listed in `requirements.txt`

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/pedrocorsini/opencv-course.git
cd computer-vision-codes
```

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv .venv
# On Windows:
.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Install the Package (Optional)

```bash
pip install -e .
```

## Usage

### Hand Tracking Example

Run the hand tracking test:

```bash
python tests/hand_tracking_main.py
```

This will use your webcam to detect and track hand landmarks in real-time.

### Pose Estimation Example

Run the pose detection test:

```bash
python tests/pose_detection_main.py
```

Detect and visualize human body poses from webcam or video input.

### Training Modules

Explore individual training modules in the `training/` directory:

```bash
# Run basic computer vision examples
python training/basic_codes/example.py

# Run face detection
python training/face_detection/example.py

# Run hand tracking
python training/hand_tracking/example.py

# Run pose estimation
python training/pose_estimation/example.py
```

## Module Overview

### Computer Vision Modules (`src/computer_vision_modules/`)

Core implementations using OpenCV for:
- Image filtering and enhancement
- Feature detection and matching
- Contour detection and analysis
- Image transformation and warping

### MediaPipe Modules (`src/mediapipe_modules/`)

Pre-trained models for:
- Hand gesture recognition
- Pose estimation
- Face detection
- Face mesh and landmarks

## Key Technologies

| Technology | Version | Purpose |
|-----------|---------|---------|
| OpenCV | 4.13.0 | Computer vision algorithms |
| MediaPipe | 0.10.21 | Pre-trained vision models |
| PyTorch | 2.10.0 | Deep learning framework |
| YOLO | 8.4.22 | Object detection |
| NumPy | 2.4.3 | Numerical computing |
| Matplotlib | 3.10.8 | Data visualization |

## Quick Start

1. **Install dependencies**: `pip install -r requirements.txt`
2. **Run a test**: `python tests/hand_tracking_main.py` (requires webcam)
3. **Explore modules**: Check `training/` directory for code examples
4. **Integrate into your project**: Import from `computer_vision_modules` or `mediapipe_modules`

## Examples

### Basic Face Detection

```python
import cv2
from src.computer_vision_modules import FaceDetector

detector = FaceDetector()
frame = cv2.imread('image.jpg')
faces = detector.detect(frame)
```

### Hand Tracking with MediaPipe

```python
import cv2
from src.mediapipe_modules import HandTracker

tracker = HandTracker()
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    if not ret:
        break
    
    results = tracker.track(frame)
    frame = tracker.draw(frame, results)
    
    cv2.imshow('Hand Tracking', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

## Resources

The `resources/` directory contains:
- **faces/**: Sample images for face detection testing
- **photos/**: General-purpose test images
- **videos/**: Video files for testing video processing modules
- **gesture_recognizer.task**: Pre-trained MediaPipe gesture recognition model

## Tips for Getting Started

1. **For beginners**: Start with `training/basic_codes/` to understand fundamental OpenCV concepts
2. **For real-time processing**: Check the hand tracking and pose estimation examples
3. **For face detection**: See `training/face_detection/` directory
4. **For advanced users**: Explore the modular implementations in `src/`

## Performance Notes

- Real-time processing (30+ FPS) on modern CPUs for most modules
- GPU acceleration recommended for large-scale video processing
- MediaPipe models are optimized for edge devices and mobile platforms

## Troubleshooting

### Webcam not detected
- Ensure your device has camera access permissions
- Check that the camera index (usually 0) is correct

### Import errors
- Verify all dependencies are installed: `pip install -r requirements.txt`
- Ensure the package is installed in development mode: `pip install -e .`

### Slow performance
- Try using GPU acceleration (CUDA for NVIDIA GPUs)
- Reduce input resolution for faster processing

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Copyright (c) 2026 Pedro Corsini

## Contributing

Contributions are welcome! Feel free to submit issues and enhancement requests.

## References

- [OpenCV Documentation](https://docs.opencv.org/)
- [MediaPipe](https://mediapipe.dev/)
- [PyTorch](https://pytorch.org/)
- [Ultralytics YOLO](https://github.com/ultralytics/ultralytics)

## Acknowledgments

This course builds upon the OpenCV learning path and incorporates modern deep learning approaches for enhanced accuracy and real-time performance.

---

**Happy learning!** 🎥📸🎯

For more information or questions, please refer to the code documentation and examples in the repository.
