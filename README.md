# Virtual Mouse - Hand Gesture Control

A computer vision-based virtual mouse that allows you to control your cursor using hand gestures captured through your webcam. No physical mouse needed!

## Overview

This project uses MediaPipe for hand tracking and PyAutoGUI for cursor control, enabling you to perform various mouse operations simply by showing different hand gestures to your camera.

## Features

- **Cursor Movement**: Move your cursor by showing a peace sign (index and middle fingers up)
- **Left Click**: Show only your index finger
- **Right Click**: Show only your middle finger
- **Double Click**: Show index, middle, and pinky fingers (ring finger closed)
- **Scroll Down**: Show middle, ring, and pinky fingers (index closed)
- **Scroll Up**: Show only ring and pinky fingers
- **Drag**: Close all fingers into a fist to drag items

## Hand Gestures Guide

| Gesture | Action | Fingers Position |
|---------|--------|------------------|
| ✌️ Peace Sign | Move Cursor | Index + Middle fingers up |
| ☝️ Index Only | Left Click | Only index finger up |
| 🖕 Middle Only | Right Click | Only middle finger up |
| 🤘 Rock Sign | Double Click | Index + Middle + Pinky up |
| Three Fingers | Scroll Down | Middle + Ring + Pinky up |
| Two Fingers | Scroll Up | Ring + Pinky up |
| ✊ Fist | Drag | All fingers closed |

## Requirements

### Python Libraries

Install the required libraries using pip:

```bash
pip install opencv-python
pip install mediapipe
pip install pyautogui
```

**Note**: The `time` module is part of Python's standard library and doesn't require separate installation.

### Hardware

- A working webcam
- Python 3.7 or higher

## Installation

1. Clone or download this repository
2. Install the required libraries (see Requirements section)
3. Run the script:

```bash
python virtual_mouse.py
```

## Usage

1. Run the script - a window will open showing your webcam feed
2. Position your **right hand** in front of the camera
3. Use the gestures listed above to control your mouse
4. Press 'q' to quit the application

## Important Notes

- **Only the right hand is tracked** - left hand gestures will be ignored
- **10-second cooldown** between clicks to prevent accidental multiple clicks
- **Failsafe enabled** - move your mouse to the top-left corner of the screen to stop PyAutoGUI if needed
- Ensure good lighting for better hand detection
- Keep your hand clearly visible to the camera

## Troubleshooting

**Camera not opening**: Make sure your webcam is connected and not being used by another application.

**Hand not detected**: Ensure good lighting and that your entire hand is visible in the frame.

**Cursor too sensitive/slow**: Adjust the smoothing formula in the code (currently set to `/5`).

**Clicks not registering**: Wait for the 10-second cooldown between clicks, or reduce the `click_delay` variable in the code.

## Customization

You can modify the following parameters in the code:

- `click_delay`: Change the cooldown time between clicks (default: 10 seconds)
- Smoothing factor: Adjust cursor movement sensitivity (line with `/ 5`)
- Scroll speed: Modify the scroll values (currently `120` and `-120`)

## License

Free to use and modify for personal and educational purposes.

## Credits

Built using:
- [MediaPipe](https://google.github.io/mediapipe/) for hand tracking
- [OpenCV](https://opencv.org/) for video capture
- [PyAutoGUI](https://pyautogui.readthedocs.io/) for mouse control
