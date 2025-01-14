# Face Emotion Detection System

A YOLOv8-based AI solution for detecting facial emotions in real-time. This system is designed for applications like monitoring, video processing, and emotional data analysis.

## Features
- Real-time detection of facial emotions in images and videos.
- Dataset augmentation for diverse scenarios, ensuring robust performance.
- Scalable design for integration into larger systems.

## Setup Instructions
1. **Open the Notebook**: Download and open the notebook on Google Colab.
2. **Connect to GPU Runtime**: Ensure GPU runtime is enabled in Google Colab for faster performance.
3. **Upload Input Files**:
   - Go to the file section in Colab and upload a video or image you want to test the model on.
   - Move the uploaded file to the `/content/ManualTestingData` folder.
4. **Update Prediction Command**:
   - Modify the following code snippet in the notebook:
     ```python
     weightsPath="/content/FaceEmotionSystem/Face_Emotion-1/runs/detect/train2/weights"
     !yolo task=detect mode=predict model={weightsPath}/best.pt conf=0.5 source='/content/ManualTestingData/InputVideo.mp4' save=True
     ```
   - Replace `InputVideo.mp4` with the name of your uploaded video or image.
5. **Run Predictions**:
   - Execute the code to generate predictions on your test files.
6. **Download Output**:
   - Use the final code cell in the notebook to download the annotated video.

## Technologies Used
- Python
- YOLOv8
- Roboflow
- OpenCV
- Google Colab

## Results
- Example detections are saved as videos with annotated bounding boxes.
- Performance metrics (e.g., confusion matrix and results.csv) are generated after training.

## Prediction Accuracy
The model achieved an accuracy of approximately 81.4% based on the confusion matrix. The accuracy for each emotion is as follows:
- Angry: 77%
- Disgust: 62%
- Fear: 82%
- Happy: 93%
- Neutral: 89%
- Sad: 80%
- Surprise: 87%

## Tested Video Result
View an example of the tested video output here:  
[Download Tested Video]()

## Requirements
- **Google Colab**: GPU-enabled runtime for training and testing.
- **Dataset**: Use Roboflow or upload a pre-labeled face emotion detection dataset.
- **YOLOv8 Framework**: For training and predictions.

## License
This project is licensed under the [MIT License](LICENSE).

## Acknowledgments
- [YOLOv8](https://ultralytics.com/yolov8)
- [Roboflow](https://roboflow.com/)
- Google Colab
