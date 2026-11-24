# Face-Blur

A command-line script that detects faces with MediaPipe and blurs them.

## Usage (from the script's arguments, not tested)
Image (saves output/output.png):

```
python "FACE BLUR.py" --mode image --filePath path/to/image.jpg
```

Video (saves output/output.mp4, written at a fixed 25 fps, frames only):

```
python "FACE BLUR.py" --mode video --filePath path/to/video.mp4
```

Webcam (live preview, and the default mode):

```
python "FACE BLUR.py" --mode webcam
```

The ./output folder is created in the folder you run the script from.

## Dependencies (from the imports)
opencv-python, mediapipe

## Notes
- Face detection uses MediaPipe with model_selection=0 and a minimum confidence of 0.5.
- The blur is a simple 30x30 box blur applied to each detected face box.
- The file name contains a space, so quote it on the command line.
- The webcam loop has no quit key in the code.
