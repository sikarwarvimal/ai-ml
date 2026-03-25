# Exercise Posture Classification — Capstone Project

## Jupyter Notebook

**[View the full analysis notebook](notebooks/exercise-posture-detection.ipynb)**

## Summary of Findings

This project develops a hybrid machine learning system to classify exercise form (correct vs. incorrect) from single images. Three models were built and compared:

| Model | Approach | Key Strength |
|-------|----------|-------------|
| **Pose-based (Random Forest)** | 5 biomechanical joint angles extracted via MoveNet | Interpretable — can explain *which* joint is wrong |
| **CNN** | 3-layer convolutional neural network on raw images | Highest accuracy — learns complex visual patterns |
| **Fusion** | Average of CNN + Pose model probabilities | Combines both signal sources |

**Key results:**
- The **CNN model** achieved the highest performance, though its near-perfect accuracy warrants caution about potential dataset-specific shortcuts.
- **Knee angle** and **hip angle** are the most discriminative pose features, especially for squats and lunges.
- **F1 Score** was chosen as the primary metric because both false negatives (injury risk) and false positives (user frustration) carry real-world cost.

**Recommendation:** Deploy the CNN as the primary classifier with pose features as an explainability layer — when incorrect form is detected, report which specific joint angles deviate from expected ranges.

## Problem Statement

**Business Question:** Can a machine learning model accurately classify correct vs. incorrect exercise form from a single image, enabling real-time posture feedback in fitness applications?

**Business Value:** Democratizes access to form correction — personal trainers are expensive and not always available. An automated system could serve millions of users through fitness apps, gym kiosks, or physical therapy tools.

## Dataset

| Property | Value |
|----------|-------|
| **Total Images** | 3,205 |
| **Exercise Types** | 4 (Squat, Push-up, Plank, Lunge) |
| **Labels** | Binary (Correct / Incorrect) |
| **Image Resolution** | 640×480, resized to 224×224 |
| **Source** | Pexels stock photos + 12 augmentations per base image |

### Exercise Distribution
| Exercise | Correct | Incorrect | Total |
|----------|---------|-----------|-------|
| Squat    | 400     | 400       | 800   |
| Push-up  | 400     | 400       | 800   |
| Plank    | 400     | 400       | 800   |
| Lunge    | 405     | 400       | 805   |
| **Total**| **1,605** | **1,600** | **3,205** |

## Methodology

1. **Data Loading & Cleaning** — Images loaded via OpenCV, filtered for corrupted files, normalized to [0,1]
2. **EDA** — Class distribution, exercise distribution, sample image visualization, descriptive statistics
3. **Pose Feature Engineering** — MoveNet extracts 17 body keypoints → 5 joint angles (knee, hip, elbow, shoulder, spine)
4. **Modeling:**
   - Random Forest with GridSearchCV (27 hyperparameter combos, 5-fold CV, F1-optimized)
   - Custom 3-layer CNN with EarlyStopping and Dropout
   - Fusion ensemble (probability averaging)
   - Exercise type classifier (4-class CNN)
5. **Evaluation** — Accuracy, F1, Precision, Recall, confusion matrix, cross-validation

## Technologies

- **Python 3.13** | **TensorFlow / Keras** | **MoveNet (TF Hub)**
- **scikit-learn** (RandomForest, GridSearchCV, Pipeline, StandardScaler)
- **OpenCV** | **pandas** | **NumPy**
- **Matplotlib** | **Seaborn** | **Plotly**

## Project Structure

```
exercise-posture-detection/
├── README.md
├── requirements.txt
├── notebooks/
│   ├── exercise-posture-detection.ipynb    # Main analysis notebook
│   ├── input-poses/                        # Test images for prediction
│   │   ├── squat-correct.jpeg
│   │   └── squat-incorrect.jpg
│   └── exercise_training_dataset/          # Training dataset (3,205 images)
│       ├── squat/   (correct/ & incorrect/)
│       ├── pushup/  (correct/ & incorrect/)
│       ├── plank/   (correct/ & incorrect/)
│       └── lunge/   (correct/ & incorrect/)
```

## Installation & Usage

```bash
pip install -r requirements.txt
jupyter notebook notebooks/exercise-posture-detection.ipynb
```

## Next Steps

1. Collect more diverse base images (varied body types, lighting, camera angles)
2. Implement Grad-CAM to verify CNN attention regions
3. Add transfer learning (ResNet/EfficientNet) for stronger visual features
4. Extend to video-based temporal analysis for rep counting and fatigue detection
5. Expand to additional exercises (deadlift, overhead press, burpee)
6. Benchmark inference latency for mobile/edge deployment

## Author

**Vimal Kumar**
Data Science Capstone Project — Module 20
February 14, 2026
