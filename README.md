# Traffic Police Hand Gesture Recognition

This project recognizes traffic police hand gestures in real-time using a webcam. It leverages [MediaPipe](https://google.github.io/mediapipe/) for pose estimation and uses rule-based logic to classify gestures such as STOP, WAIT, TURN LEFT, TURN RIGHT, MOVE STRAIGHT, and VIP SALUTE.

## Features

- Real-time hand gesture recognition using a webcam
- Uses MediaPipe for pose detection
- Rule-based classification (no ML model training required)
- Easily extendable for more gestures



## Setup Instructions

### 1. Clone the Repository

```bash
git clone <repository-url>
cd Traffic-Hand-gesture
```

### 2. Install Dependencies and Download Models

Run the setup script (Linux/Mac):

```bash
bash setup.sh
```

Or manually install dependencies:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

> **Note:** The `setup.sh` script will also download required TFLite models into the `models/` directory.

### 3. Run the Application

```bash
python detect.py
```

This will open your webcam and start recognizing hand gestures.

## Customization options

*  Here is the full list of parameters supported by the sample:
```python3 pose_classification.py```
  *   `model`: Name of the TFLite pose estimation model to be used.
    *   One of these values: `posenet`, `movenet_lightning`, `movenet_thunder`, `movenet_multipose`
    *   Default value is `movenet_lightning`.
  *   `tracker`: Type of tracker to track poses across frames.
    *   One of these values: `bounding_box`, `keypoint`
    *   Only supported in multi-poses models.
    *   Default value is `bounding_box`.
  *   `classifier`: Name of the TFLite pose classification model to be used.
    *   Default value is empty.
    *   If no classification model specified, the sample will only run the pose
        estimation step.
  *   `camera_id`: Specify the camera for OpenCV to capture images from.
    *   Default value is `0`.
  *   `frameWidth`, `frameHeight`: Resolution of the image to be captured from
      the camera.
    *   Default value is `(640, 480)`.

## Visualize pose estimation result of test data

*  Run this script to visualize the pose estimation on test data

```python3 visualizer.py```
