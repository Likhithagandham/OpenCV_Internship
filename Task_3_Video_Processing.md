# Task 3: Video Processing with FFmpeg and Object Detection

## 1. Objective
To demonstrate competence in video processing by using FFmpeg to break a video clip into sequential frames, processing those frames using the Ultralytics YOLOv8 model, and then stitching the processed frames back into a final output video.

## 2. Process and Commands

### A. Video Acquisition and Frame Extraction
* **Input File:** input_clip.mp4
* **Command Used:**
    ```bash
    ffmpeg -i input_clip.mp4 -vf fps=10 video_frames/frame_%04d.jpg
    ```
* **Observation:** The command successfully extracted 10 frames per second, creating hundreds of sequential JPG images in the 'video_frames' folder.

### B. Object Detection on Frames
* **Tool:** Ultralytics YOLOv8n (pretrained model)
* **Command Used:**
    ```bash
    yolo predict model=yolov8n.pt source='video_frames' save
    ```
* **Output Location:** The processed frames were saved to the 'runs/detect/predict[X]' folder.

### C. Video Stitching (Re-creation)
* **Input:** Processed frames from the output folder.
* **Command Used:** (Adjust 'predict' folder name if needed)
    ```bash
    ffmpeg -framerate 10 -i runs/detect/predict[X]/frame_%04d.jpg -c:v libx264 -pix_fmt yuv420p output_clip_processed.mp4
    ```
* **Final Output:** output_clip_processed.mp4

## 3. Results and Conclusion
* **Visual Observation:** The original video was successfully converted to a processed video showing real-time object detection and bounding boxes around objects like [List 2-3 detected objects, e.g., 'cars' and 'people'].
* **File Status:** The final processed video file ('output_clip_processed.mp4') was created and is ready for submission/upload.
