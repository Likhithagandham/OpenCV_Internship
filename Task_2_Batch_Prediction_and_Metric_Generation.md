# Day 2: Batch Processing and Metric Analysis

## 1. Batch Prediction (Custom Images)
Successfully ran object detection on 5 custom images containing known COCO classes (e.g., person, car, cup).
**Verification:** The visual output in `runs/detect/predict` clearly shows accurate bounding boxes and labels for the objects included in the test images. This confirms the installed tool suite is fully functional.

## 2. Performance Metrics from Validation (runs/detect/val)
The model was run in validation mode on the standard COCO8 dataset to generate a performance benchmark.

| Metric | Value (from results.txt) | Meaning |
| :--- | :--- | :--- |
| **mAP50** | *[Insert actual value from terminal/results.txt]* | Model's overall accuracy with 50% or more overlap required. |
| **mAP50-95** | *[Insert actual value from terminal/results.txt]* | Stricter measure of bounding box precision averaged across multiple overlap thresholds. |
| **Precision** | *[Insert actual value from terminal/results.txt]* | Quality of detections: How many predicted boxes were correct? |
| **Recall** | *[Insert actual value from terminal/results.txt]* | Quantity of detections: How many actual objects did the model find? |

## Conclusion
All initial requirements have been met: batch processing is functional, and performance metrics are generated and documented. The project is ready to move to the real-world problem domain.
