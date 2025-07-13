# face_anonymizer_opencv
# Face Blur Tool with OpenCV and MediaPipe

A Python tool to **detect and blur faces** in images, videos, or live webcam streams using OpenCV and MediaPipe.

---

## Features

- **Automatic face detection** using MediaPipe's pre-trained models
- **Face blurring** for privacy or anonymization
- Supports processing:
  - Images (`--mode image`)
  - Videos (`--mode video`)
  - Webcam streams (`--mode webcam`)
- Saves processed files to an `output/` directory or displays live results

---

## Requirements

pip install -r requirements.txt


---

## Usage

### Command-Line Arguments

- `--mode`: Choose `"image"`, `"video"`, or `"webcam"` (default: `"webcam"`)
- `--filePath`: Path to the image or video file (required for `"image"` and `"video"` modes)

### Examples

**Blur faces in an image:**


_Output saved to `./output/output.png`_

**Blur faces in a video:**


_Output saved to `./output/output.mp4`_

**Blur faces in real-time from webcam:**

_Live preview window opens. Press `Q` or close the window to exit._

---

## How It Works

1. **Face Detection:**  
   MediaPipe detects faces in each frame, returning bounding boxes as relative coordinates.

2. **Bounding Box Conversion:**  
   Relative coordinates are converted to pixel values using the image/frame dimensions.

3. **Blurring:**  
   Each detected face region is extracted and blurred using OpenCV's `cv2.blur` with a kernel size of `(30, 30)`, then placed back into the frame.

4. **Saving/Displaying:**  
   - For images: The processed image is saved.
   - For videos: Each processed frame is written to an output video file.
   - For webcam: The processed frames are shown in a window in real time.

---





---

## Notes

- The blurring kernel size can be adjusted in the code (`(30, 30)`) for stronger or weaker blur.
- The script automatically creates an `output` directory if it doesn't exist.
- The webcam mode displays video in real time; to stop, close the window or interrupt the script.

---

## License

This project is open-source and free to use for educational and non-commercial purposes.
