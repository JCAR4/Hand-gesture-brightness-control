# Hand Gesture Brightness Control

A **real-time hand gesture-based brightness control system** that uses a webcam to detect your hand and adjusts your screen brightness dynamically based on the distance between your thumb and index finger. Implemented entirely in Python with **OpenCV** and **screen-brightness-control**, no MediaPipe or cvzone required, making it compatible with Python 3.13.

---

## Features

- Detects a single hand in real-time using OpenCV and skin color segmentation.
- Identifies fingertips using convex hull and convexity defects.
- Maps the distance between thumb and index finger to screen brightness (0–100%).
- Updates brightness smoothly to avoid sudden changes.
- Displays webcam feed with hand contour, fingertips, distance, and current brightness.
- Optional GUI dialog showing live brightness level.

---


## Installation

1. **Clone the repository**:
```bash
git clone https://github.com/yourusername/hand-gesture-brightness-control.git
cd hand-gesture-brightness-control

```

## Installation

Install dependencies:

```bash
pip install opencv-python numpy screen-brightness-control
```
Run the program:
```bash
python hand_brightness_control.py
```

Make sure your webcam is working and you are in a well-lit environment for accurate hand detection.

## Usage

- Open the program; a window will show the webcam feed.
- Place your hand in front of the camera.
- Move your thumb and index finger apart or closer to increase or decrease screen brightness.
- The GUI dialog or label (if included) will display the current brightness percentage.
- Press **Esc** to exit the program.

---

## Configuration

- **HSV Skin Color Range**: Adjust `lower` and `upper` in `get_skin_mask()` if detection is inaccurate in your lighting.
- **Distance Calibration**: Adjust `min_dist` and `max_dist` in `map_distance_to_brightness()` to match your hand size and camera distance.
- **Smoothing**: Modify the threshold in `prev_brightness` logic to reduce flickering.

---

## Dependencies

- Python 3.13+
- OpenCV
- NumPy
- screen-brightness-control

---

## License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

## Future Improvements

- Use more robust hand detection models for low-light conditions.
- Add support for multiple hands or gestures for advanced controls.
- Add visual feedback like a dynamic progress bar or color change based on brightness.
