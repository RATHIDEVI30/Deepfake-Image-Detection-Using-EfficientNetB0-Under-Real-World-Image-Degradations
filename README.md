Deepfake Image Detection Using EfficientNetB0 Under Real-World Image Degradations
Overview

Deepfake image generation has become increasingly sophisticated, making it difficult to distinguish manipulated images from authentic ones. Most existing deepfake detection models are trained and evaluated on clean, high-quality datasets, which do not accurately represent real-world conditions.

This project proposes a robust deepfake image detection framework using EfficientNetB0 and evaluates its performance under various real-world image degradations such as:

Gaussian Blur
Motion Blur
Low-Light Conditions
Image Noise

The goal is to analyze how image quality degradation affects deepfake detection accuracy and improve model robustness for practical deployment.

Objectives
Develop a deepfake image detection model using EfficientNetB0.
Simulate real-world image degradations on deepfake datasets.
Evaluate model performance under different degradation scenarios.
Analyze robustness using visualization techniques such as Grad-CAM.
Compare performance between clean and degraded images.
Dataset

The project uses publicly available deepfake datasets containing both:

Real Images
Fake (Deepfake) Images
Dataset Structure
dataset/
│
├── train/
│   ├── real/
│   └── fake/
│
├── validation/
│   ├── real/
│   └── fake/
│
└── test/
    ├── real/
    └── fake/
Real-World Image Degradations

To mimic practical image capture conditions, the following degradations are applied:

1. Gaussian Blur

Simulates out-of-focus camera images.

2. Motion Blur

Represents camera shake or moving subjects.

3. Low-Light Images

Simulates poor illumination environments.

4. Gaussian Noise

Represents sensor noise and compression artifacts.

Examples:

Original Image
     ↓
Gaussian Blur
     ↓
Motion Blur
     ↓
Low Light
     ↓
Gaussian Noise
Methodology
Step 1: Data Collection

Collect real and deepfake images from benchmark datasets.

Step 2: Data Preprocessing
Resize images to 224 × 224
Normalize pixel values
Apply augmentation techniques
Step 3: Image Degradation Generation

Generate degraded versions of images:

Blur
Motion blur
Low-light
Noise
Step 4: Model Training

Train EfficientNetB0 on:

Clean Images
Degraded Images
Step 5: Performance Evaluation

Evaluate using:

Accuracy
Precision
Recall
F1-Score
Confusion Matrix
ROC-AUC
Step 6: Explainability

Use Grad-CAM to visualize regions influencing model predictions.

Model Architecture
EfficientNetB0

EfficientNetB0 is chosen because:

High accuracy
Lightweight architecture
Low computational cost
Suitable for real-world deployment

Architecture Flow:

Input Image
      ↓
EfficientNetB0 Feature Extractor
      ↓
Global Average Pooling
      ↓
Dense Layer
      ↓
Dropout
      ↓
Output Layer (Real / Fake)
Technologies Used
Component	Technology
Programming Language	Python
Deep Learning Framework	PyTorch
Model	EfficientNetB0
Visualization	Grad-CAM
Image Processing	OpenCV
Data Handling	NumPy, Pandas
Evaluation	Scikit-Learn
Plotting	Matplotlib, Seaborn
Installation

Clone the repository:

git clone https://github.com/yourusername/Deepfake-Image-Detection-Using-EfficientNetB0-Under-Real-World-Image-Degradations.git

cd Deepfake-Image-Detection-Using-EfficientNetB0-Under-Real-World-Image-Degradations

Install dependencies:

pip install -r requirements.txt
Project Structure
Deepfake-Image-Detection/
│
├── dataset/
│
├── degradations/
│   ├── gaussian_blur.py
│   ├── motion_blur.py
│   ├── low_light.py
│   └── gaussian_noise.py
│
├── models/
│   └── efficientnetb0.py
│
├── training/
│   └── train.py
│
├── testing/
│   └── test.py
│
├── gradcam/
│   └── gradcam_visualization.py
│
├── results/
│
├── requirements.txt
│
└── README.md
Training

Run model training:

python train.py
Testing

Evaluate the trained model:

python test.py
Performance Metrics

The model is evaluated using:

Accuracy
Precision
Recall
F1-Score
ROC-AUC Score

Example Results:

Condition	Accuracy
Clean Images	98.5%
Gaussian Blur	95.7%
Motion Blur	94.8%
Low Light	93.6%
Gaussian Noise	92.9%

Results are sample values and may vary depending on the dataset and training configuration.

Grad-CAM Visualization

Grad-CAM helps explain model decisions by highlighting image regions responsible for classification.

Benefits
Improves model interpretability
Detects manipulated facial regions
Supports trustworthiness of predictions
Applications
Social Media Content Verification
Fake News Detection
Digital Forensics
Cybersecurity
Media Authentication
Identity Protection
Future Work
Extend to deepfake video detection.
Evaluate on larger and more diverse datasets.
Explore Vision Transformers (ViT) and hybrid models.
Improve robustness against unseen degradations.
Deploy as a web-based detection system.
Conclusion

This project demonstrates the effectiveness of EfficientNetB0 for deepfake image detection under challenging real-world image degradations. By evaluating performance on blurred, noisy, and low-light images, the study provides insights into the robustness and practical applicability of deepfake detection systems.
