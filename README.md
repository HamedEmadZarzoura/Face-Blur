# Face-Blur

A command-line script that detects faces with MediaPipe and blurs them.

## Usage
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

Tested versions: Python 3.10, mediapipe 0.10.14, numpy 1.26.4, OpenCV 4.9.0.80. With mediapipe 1.2.3 (the version pip installed by default in one test) the script failed with `AttributeError: module 'mediapipe' has no attribute 'solutions'`, so pin a working version:

```
pip install mediapipe==0.10.14 numpy==1.26.4 opencv-python==4.9.0.80
```

## Notes
- Face detection uses MediaPipe with model_selection=0 and a minimum confidence of 0.5.
- The blur is a simple 30x30 box blur applied to each detected face box.
- The file name contains a space, so quote it on the command line.
- The webcam loop has no quit key in the code.
- Tested image and video modes on a sample photo and a clip made from it. Webcam mode was not tested.
