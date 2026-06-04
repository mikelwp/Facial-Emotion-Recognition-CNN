# Facial Emotion Recognition using Optimized CNN

Facial Emotion Recognition (FER) merupakan sistem Computer Vision yang digunakan untuk mengidentifikasi emosi manusia berdasarkan ekspresi wajah. Proyek ini menggunakan Convolutional Neural Network (CNN) yang telah dioptimasi dengan Batch Normalization, Dropout, Data Augmentation, dan Learning Rate Scheduling untuk meningkatkan performa klasifikasi emosi.

Dataset : https://www.kaggle.com/datasets/msambare/fer2013
## Features

- Klasifikasi ekspresi wajah menggunakan CNN
- Data Augmentation untuk meningkatkan generalisasi model
- Batch Normalization untuk stabilitas training
- Dropout untuk mengurangi overfitting
- Early Stopping dan ReduceLROnPlateau
- Evaluasi menggunakan:
  - Accuracy
  - Confusion Matrix
  - Classification Report
- Prediksi gambar wajah secara individual

## Emotion Classes

Dataset terdiri dari beberapa kategori emosi:

- Angry
- Disgust
- Fear
- Happy
- Neutral
- Sad
- Surprise

## Model Architecture

Model CNN menggunakan beberapa blok konvolusi:

### Block 1
- Conv2D (64 filters)
- Batch Normalization
- ReLU
- Conv2D (64 filters)
- Batch Normalization
- ReLU
- MaxPooling
- Dropout (0.25)

### Block 2
- Conv2D (128 filters)
- Batch Normalization
- ReLU
- Conv2D (128 filters)
- Batch Normalization
- ReLU
- MaxPooling
- Dropout (0.25)

### Block 3
- Conv2D (256 filters)
- Batch Normalization
- ReLU
- Conv2D (256 filters)
- Batch Normalization
- ReLU
- MaxPooling
- Dropout

### Fully Connected Layer
- Dense Layer
- Dropout
- Softmax Output

## Data Augmentation

Untuk meningkatkan kemampuan generalisasi model, digunakan:

```python
rotation_range=20
width_shift_range=0.2
height_shift_range=0.2
horizontal_flip=True
zoom_range=0.2
shear_range=0.2
```

## Technologies Used

- Python
- TensorFlow
- Keras
- OpenCV
- NumPy
- Matplotlib
- Scikit-Learn

## Project Structure

```
Facial-Emotion-Recognition-CNN/
│
├── Facial_Emotion_Recognition_Optimized.ipynb
├── README.md
├── model/
│   ├── modelcnn_optimized.keras
│   └── modelcnn_optimized.h5
│
└── dataset/
    ├── train/
    └── test/
```

## Installation

Clone repository:

```bash
git clone https://github.com/USERNAME/Facial-Emotion-Recognition-CNN.git
cd Facial-Emotion-Recognition-CNN
```

Install dependencies:

```bash
pip install tensorflow keras opencv-python numpy matplotlib scikit-learn seaborn pandas
```

## Dataset Preparation

Susun dataset dengan format berikut:

```
dataset/
├── train/
│   ├── Angry/
│   ├── Disgust/
│   ├── Fear/
│   ├── Happy/
│   ├── Neutral/
│   ├── Sad/
│   └── Surprise/
│
└── test/
    ├── Angry/
    ├── Disgust/
    ├── Fear/
    ├── Happy/
    ├── Neutral/
    ├── Sad/
    └── Surprise/
```

## Training

Jalankan notebook:

```bash
jupyter notebook Facial_Emotion_Recognition_Optimized.ipynb
```

Model akan dilatih menggunakan:

- Data Augmentation
- Early Stopping
- Model Checkpoint
- Reduce Learning Rate on Plateau

## Evaluation

Model dievaluasi menggunakan:

- Validation Accuracy
- Validation Loss
- Confusion Matrix
- Classification Report

## Prediction

Untuk melakukan prediksi gambar tunggal:

```python
result = model.predict(img_pred)
predicted_emotion = CATEGORIES[np.argmax(result)]
```

Output:

```
Predicted Emotion: Happy
Confidence: 0.97
```

## Future Improvements

- Transfer Learning (ResNet, EfficientNet, MobileNet)
- Real-time Webcam Detection
- Deployment menggunakan Streamlit
- Hyperparameter Optimization
- Model Quantization untuk perangkat mobile

## Author
Michael William

