# Prediction-of-Knee-Osteoarthritis-
Prediction of Knee Osteoarthritis on X-ray Images using Densenet 121 deep learning architecture


# Medical Knee X-Ray Classifier

# Dataset :
The model is trained on the dataset, containing X-ray images of knee joints labeled with different grades of osteoarthritis.
Link - https://data.mendeley.com/datasets/t9ndx37v5h/1
Data Classes : Normal, Doubtful, Mild, Moderate, Severe
Format : X-ray images .png format

## Installation

1. Clone the repository:
```
git clone https://github.com/your-username/medical-knee-xray-classifier.git
```
2. Install the required dependencies:
```
pip install -r requirements.txt
```

## Usage

1. Prepare your dataset:
   - Place your knee X-ray images in the appropriate directories (e.g., "Normal", "Mild", "Moderate", "Severe", "Doubtful").
   - Modify the `expert1_dir` and `output_directory` variables in the code to match your file paths.
2. Run the data preprocessing and augmentation script:
```python
python medical_new_koa.py
```
3. Train the DenseNet121-based model:
```python
python train_model.py
```
4. Evaluate the model on the test set:
```python
python evaluate_model.py
```

## API

The main functions and classes used in this project are:

- `augment_image(image)`: Performs basic image augmentation (horizontal flip, vertical flip, rotation).
- `extra_augment_image(image)`: Applies additional augmentation techniques (Gaussian blur, contrast adjustment) for the "Mild" and "Doubtful" classes.
- `process_images(source_dir, prefix)`: Processes the images, applies augmentation, and saves the results to the output directory.
- `train_model.py`: Trains the DenseNet121-based model on the preprocessed dataset.
- `evaluate_model.py`: Evaluates the trained model on the test set and generates a confusion matrix and classification report.


Result

(https://github.com/user-attachments/assets/85eb314a-e36e-497b-be52-1bbadb84b11b)

1. Performance Metrics (Per Class)
Class	Precision	Recall	F1-Score
0 Normal	94.68%	80.95%	87.28%
1 Doubtful	76.99%	87.91%	82.08%
2 Mild	83.94%	77.51%	80.60%
3 Moderate	89.57%	94.97%	92.19%
4 Severe	86.15%	90.81%	88.42%


2. Interpretation of Results
High Precision in "0 Normal" (94.68%): The model rarely misclassifies other classes as "Normal," but its recall (80.95%) indicates that some normal cases are misclassified.
"3 Moderate" Has the Best Recall (94.97%): The model correctly identifies most moderate cases but has some false positives (precision = 89.57%).
"1 Doubtful" is Slightly Challenging: While recall is high (87.91%), the precision is lower (76.99%), meaning many other classes are wrongly classified as "Doubtful."
Balanced Performance on "4 Severe": With precision at 86.15% and recall at 90.81%, the model does well on severe cases.


