# Pose Flappy Bird

Flappy Bird clone controlled by your lateral raises using MediaPipe pose tracking.
Two windows run in parallel:
- OpenCV webcam feed with pose landmarks and arm level debug text
- Pygame game window

## Requirements
- Python 3.10
- Webcam

## Install
```bash
pip install opencv-python mediapipe pygame
```

## Run
```bash
python main.py
```

## How control works
- MediaPipe tracks shoulder/elbow/wrist and hip landmarks.
- Arm level is computed from the arm-to-torso angle (lateral raises score higher).
- When `arm_level` reaches the threshold (default 0.8), it triggers a single flap.
- You must lower your arms below the reset threshold (default 0.6) to arm the next flap.

## Tuning
Open `main.py` and adjust:
- `flap_threshold` and `flap_reset` in `main()` for easier/harder triggering.
- `gravity`, `flap_strength`, `pipe_gap`, `pipe_speed`, `pipe_spacing` in `FlappyGame.reset()`.

## Notes
- Make sure your shoulders and wrists are visible in the webcam frame.
- Good lighting helps pose detection.
- Press ESC in the webcam window or close the game window to exit.
