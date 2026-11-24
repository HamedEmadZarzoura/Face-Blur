# Face-Blur

A command-line script that detects faces with MediaPipe and blurs them.

## Usage (from the script's arguments, not tested)
Image: python "FACE BLUR.py" --mode image --filePath path/to/image.jpg
  Saves output/output.png
Video: python "FACE BLUR.py" --mode video --filePath path/to/video.mp4
  Saves output/output.mp4 (written at a fixed 25 fps, frames only)
Webcam: python "FACE BLUR.py" --mode webcam
  Live preview. Webcam is the default mode.

The ./output folder is created in the folder you run the script from.

## Dependencies (from the imports)
opencv-python, mediapipe

## Notes
- Face detection uses MediaPipe with model_selection=0 and a minimum confidence of 0.5.
- The blur is a simple 30x30 box blur applied to each detected face box.
- The file name contains a space, so quote it on the command line.
- The webcam loop has no quit key in the code.
