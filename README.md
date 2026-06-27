# Real-Time Firearms Detection System

A real-time computer vision system that detects firearms and faces in live video streams using OpenCV and Haar Cascade classifiers, with automated audio alerts on threat detection.

## Features

- Real-time firearm and face detection via webcam
- Bounding box annotation with live threat status overlay
- Audio alert on firearm detection using text-to-speech
- Timestamp display on each frame
- Auto-shutdown after 10 seconds of no detection

## Tech Stack

- Python, OpenCV, imutils
- Haar Cascade Classifiers (custom `cascade.xml` for guns, built-in for faces)
- pyttsx3 (text-to-speech)

## Setup

```bash
pip install opencv-python imutils pyttsx3 keyboard matplotlib
```

Place `cascade.xml` and `haarcascade_frontalface_default.xml` in the project root, then run:

```bash
python detection.py
```

Press `Enter` to dismiss an alert. Press `Q` to quit.

## How It Works

Each frame from the webcam is converted to grayscale and passed through two cascade classifiers — one for firearms, one for faces. If a firearm is detected, the system draws a bounding box, prints a threat warning, and triggers a looping voice alert until dismissed. If no firearm is detected for 10 consecutive seconds, the camera stops automatically.
