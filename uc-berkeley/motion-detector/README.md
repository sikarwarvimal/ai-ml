# Exercise Form Classification - Capstone Project

## Project Overview

This project develops a machine learning solution to automatically classify exercise form as "correct" or "incorrect" for common bodyweight exercises. The system uses computer vision and pose estimation to provide instant feedback on workout form, enabling safer and more effective exercise without requiring a personal trainer.

## Problem Statement

**Research Question**: Can we build an accurate machine learning model that classifies exercise form (correct vs. incorrect) from single images of people performing bodyweight exercises?

**Business Value**: This solution enables fitness applications to provide real-time form feedback, improving workout safety, effectiveness, and user experience.

## Dataset

### Dataset Composition
- **Total Images**: 741
- **Exercise Types**: 4 (Squat, Push-up, Plank, Lunge)
- **Labels**: Binary (Correct, Incorrect)
- **Image Resolution**: 640x480 pixels
- **Data Augmentation**: Applied (12 augmentations per base image)

### Exercise Distribution
| Exercise | Correct Form | Incorrect Form | Total |
|----------|-------------|----------------|-------|
| Squat    | 130         | 65             | 195   |
| Push-up  | 130         | 65             | 195   |
| Plank    | 104         | 65             | 169   |
| Lunge    | 130         | 52             | 182   |
| **Total**| **494**     | **247**        | **741** |

### Data Augmentation Techniques
- Horizontal flips
- Rotation (±10°)
- Brightness adjustments
- Contrast variations
- Color saturation changes
- Sharpness & blur effects
- Random crops

## Methodology

### 1. Data Collection
- Downloaded exercise images from Pexels (free stock photos)
- Applied data augmentation to create 741 total images from 57 base images
- Organized images into structured folders by exercise and label

### 2. Feature Engineering
- **Pose Estimation**: MediaPipe Pose detection
- **Extracted Features** (12 total):
  - Joint angles: left/right knee, elbow, hip, shoulder (8 features)
  - Body alignment: torso position, shoulder width, hip width (3 features)
  - Pose confidence score (1 feature)

### 3. Exploratory Data Analysis
- Missing value analysis (0 missing values)
- Duplicate detection (0 duplicates)
- Outlier analysis using IQR method
- Distribution analysis (categorical and numerical)
- Correlation analysis
- Feature importance ranking

### 4. Baseline Modeling
- **Models Tested**:
  1. Logistic Regression
  2. Random Forest Classifier

- **Best Model**: Random Forest Classifier
- **Train-Test Split**: 80-20 with stratification
- **Feature Scaling**: StandardScaler

## Results

### Model Performance

**Best Baseline Model: Random Forest Classifier**

| Metric    | Score  | Interpretation |
|-----------|--------|---------------|
| Accuracy  | ~85-90%| Overall correctness rate |
| Precision | ~85-90%| Positive prediction reliability |
| Recall    | ~85-90%| True positive capture rate |
| F1-Score  | ~85-90%| Balanced precision-recall |

### Key Findings

#### Data Quality
✓ Clean dataset with no missing values or duplicates  
✓ 95% success rate in pose keypoint extraction  
✓ Well-structured data organization  
⚠ Class imbalance (2:1 correct:incorrect ratio)  

#### Pattern Discovery
- **Joint Angle Patterns**: Significant differences between correct/incorrect form
- **Feature Correlations**: Left-right symmetry as expected, minimal multicollinearity
- **Outliers**: Present but represent legitimate form variations

## Technologies Used

- **Python 3.11**
- **pandas, NumPy**: Data manipulation
- **Matplotlib, Seaborn, Plotly**: Visualizations
- **scikit-learn**: Machine learning
- **OpenCV, MediaPipe**: Computer vision & pose estimation
- **Jupyter Notebook**: Development environment

## Project Structure

```
exercise-form-classification/
├── exercise_training_dataset/              # Image dataset (741 images)
│   ├── squat/correct/ & incorrect/
│   ├── pushup/correct/ & incorrect/
│   ├── plank/correct/ & incorrect/
│   └── lunge/correct/ & incorrect/
├── Exercise_Form_Classification_EDA.ipynb  # Main analysis notebook
├── create_augmented_dataset.py             # Dataset creation script
└── README_CAPSTONE.md                      # This file
```

## Installation & Usage

```bash
# Install dependencies
pip install pandas numpy matplotlib seaborn plotly scikit-learn opencv-python mediapipe pillow jupyter

# Run Jupyter Notebook
jupyter notebook Exercise_Form_Classification_EDA.ipynb
```

## Future Improvements

- Increase dataset to 5,000+ images per exercise
- Implement deep learning CNN models (ResNet, EfficientNet)
- Add multi-class classification for specific error types
- Real-time pose detection API
- Mobile app integration

## Evaluation Metrics Rationale

**Primary Metric: F1-Score** - Balances precision and recall, critical for imbalanced datasets and equally important to avoid both false positives and false negatives.

## Author

**Vimal KUmar**  
Data Science Capstone Project - Module 20  
February 14, 2026

---
## Notebook Link
[Click here to open the notebook](http://localhost:8888/lab/tree/kaiserlocal/projects/ai-ml/uc-berkeley/motion-detector/notebooks/motion-detector.ipynb)


