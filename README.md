#Knee Osteoarthritis Classification using Deep Learning
Overview
This repository contains a deep learning model for classifying knee osteoarthritis (KOA) severity from X-ray images. The model is based on DenseNet121 with attention mechanisms (CBAM, SE blocks) and Grad-CAM visualization to interpret predictions. It uses Focal Loss, data augmentation, and class balancing techniques to improve accuracy.

Dataset
The model is trained on a dataset of knee X-ray images categorized into five severity levels based on the Kellgren-Lawrence (KL) grading system:

0 - Normal
1 - Doubtful
2 - Mild
3 - Moderate
4 - Severe
The dataset is split into train, validation, and test sets.

Model Architecture
Base Model: DenseNet121 (pretrained on ImageNet)
Input Size: 224x224 pixels
Attention Mechanisms: CBAM (Convolutional Block Attention Module) and SE (Squeeze-and-Excitation) blocks
Loss Function: Focal Loss (handles class imbalance)
Optimization: Adam optimizer
Output: Softmax activation for multi-class classification
Key Features
✅ Automatic ROI Cropping – Focuses on the knee joint area before classification
✅ Data Augmentation – Tailored transformations for underrepresented classes
✅ Class Imbalance Handling – Oversampling, undersampling, and weighted loss
✅ Grad-CAM Visualization – Heatmaps to interpret model decisions
✅ Performance Metrics – Computes accuracy, precision, recall, and F1-score

Installation
Clone the repository:
```
git clone https://github.com/yourusername/knee-osteoarthritis-classification.git
cd knee-osteoarthritis-classification
```

Install dependencies:
```
pip install -r requirements.txt
```

Usage
Training the Model
Run the training script:
```
python train.py --epochs 50 --batch_size 32 --lr 0.0001

```
Evaluating the Model
To test the model on the validation/test set:
```
python evaluate.py --model_path best_model.h5
```
Grad-CAM Visualization
To visualize heatmaps:
```
python gradcam.py --image_path sample_xray.jpg --model_path best_model.h5
```

Training Configuration
![image](https://github.com/user-attachments/assets/96f446dc-0624-4dce-84f7-5b6f12858a8f)

Results
![image](https://github.com/user-attachments/assets/8222fee3-0492-4f58-8d27-b823a3e8a2dc)


