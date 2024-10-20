# AI-Hackflow-2024
group submission for the 2024 AI Hackflow organized by DeepFlow

# Xception-ResNeXt Ensemble for Deepfake Detection (Fine-tuned with UADFV Dataset)
Project Overview
This project implements an ensemble inference pipeline for detecting deepfakes in video data using two powerful deep learning models: Xception and ResNeXt. It focuses on enhancing deepfake detection accuracy by leveraging the strengths of both models, with face detection integrated using BlazeFace to focus on facial regions in the videos.

Key Features
Deepfake Detection Ensemble: Combines predictions from both Xception and ResNeXt models for robust video analysis.
BlazeFace Integration: Efficient face detection that preprocesses video frames to extract facial regions for deepfake analysis.
Frame-per-Video Technique: Analyzes a fixed number of frames (e.g., 64) per video, reducing computational costs while maintaining accuracy.
Weighted Averaging for Ensemble: Final prediction is a weighted combination of Xception and ResNeXt results, fine-tuned to optimize performance.
Use Cases
The project is particularly useful for:

Real-time deepfake detection: Applied in areas such as political media analysis, national security, and social media monitoring.
Video authenticity verification: Especially in domains like journalism, media, and law enforcement to flag manipulated videos before they spread.
Dataset and Pretrained Models
Deepfake Detection Challenge (DFDC) Dataset: A large dataset used for training deepfake detection models.
Pretrained Xception Model: Fine-tuned on deepfake datasets such as FaceForensics++ and DFDC, designed specifically for facial anomaly detection.
Available here: Deepfake Xception Trained Model on Kaggle
ResNeXt: A grouped convolution-based deep learning model used for efficient and scalable deepfake detection.

Pipeline Overview
Video Frame Extraction: The system selects a specific number of frames (e.g., 64) from each video using OpenCV.
Face Detection (BlazeFace): The BlazeFace model detects faces in the extracted frames, which are then cropped and resized to focus on facial regions.
Deepfake Inference:
ResNeXt and Xception models perform inference on the facial frames.
Both models are pretrained on large deepfake datasets.
Ensemble Prediction:
The pipeline combines the predictions of ResNeXt and Xception using a weighted averaging approach (r1 = 0.46441 for ResNeXt and r2 = 0.52189 for Xception).
![image](https://github.com/user-attachments/assets/ed1d9630-605a-402f-ab11-6b37610bb43c)

Final Output: The results for each video (real or fake) are saved in a CSV file.
![image](https://github.com/user-attachments/assets/4854801f-def2-44be-bef3-5a146288471b)
![image](https://github.com/user-attachments/assets/230815c3-c04a-44de-beeb-94d12cc59054)



Datasets:
FaceForensics++ and DFDC (DeepFake Detection Challenge): Other datasets used for model pretraining.
UADFV Dataset
The UADFV (Deepfake Videos) dataset contains a collection of deepfake videos primarily used for research on detecting manipulated videos. The dataset includes both real and fake videos, focusing on face-swapped manipulations. Fine-tuning the model on this dataset enhances its sensitivity to the types of manipulations seen in political or media videos.

Dataset Link:
UADFV Dataset: [UADFV on Kaggle](https://www.kaggle.com/datasets/ahmadawad732/uadfv-dataset-new/data)

Performance Improvements
Increased Sensitivity: Fine-tuning on UADFV has made the model more adept at detecting subtle manipulations in face-swapped videos.
Lower False Positives: The additional training data reduces the risk of falsely classifying real videos as fake, ensuring more reliable predictions.

Conclusion
This project provides a robust deepfake detection pipeline that has been enhanced by fine-tuning on the UADFV dataset. It offers a high-performance solution for applications such as real-time media monitoring, political video authentication, and national security. The combination of Xception and ResNeXt models with face detection makes it highly accurate and versatile
