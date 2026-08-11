# MNIST Handwritten Digit Classification

## 📌 Project Overview

This project focuses on **classifying handwritten digits (0–9)** using the **MNIST dataset** and a neural network built with **TensorFlow/Keras**.

The model takes a **28×28 grayscale image** of a handwritten digit as input and predicts which digit it represents.

The project covers the complete machine learning workflow:

* Data loading and exploration
* Image preprocessing
* Neural network architecture
* Model training
* Validation
* Model evaluation
* Confusion matrix and classification report
* Incorrect prediction analysis
* Model saving and loading
* Digit prediction/inference

---

## 📊 Dataset

The project uses the **MNIST handwritten digits dataset**.

| Property          | Details                      |
| ----------------- | ---------------------------- |
| Dataset           | MNIST                        |
| Training Images   | 60,000                       |
| Testing Images    | 10,000                       |
| Image Size        | 28 × 28 pixels               |
| Image Type        | Grayscale                    |
| Number of Classes | 10                           |
| Classes           | 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 |

Each image represents one handwritten digit.

---

## 🔧 Data Preprocessing

The pixel values in the MNIST dataset range from **0 to 255**.

To make the input suitable for neural network training, the pixel values were normalized to a range between **0 and 1**.

```python
x_train = x_train / 255.0
x_test = x_test / 255.0
```

The 28 × 28 images were then flattened before being passed to the dense neural network.

```text
28 × 28 Image
      ↓
   Flatten
      ↓
784 Input Features
```

---

## 🧠 Model Architecture

A feed-forward neural network was developed using Keras.

```text
Input Image
     ↓
28 × 28 Pixels
     ↓
Flatten
     ↓
Dense Layer - 128 Neurons
     ↓
Dense Layer - 64 Neurons
     ↓
Output Layer - 10 Neurons
     ↓
Predicted Digit (0–9)
```

### Architecture Details

| Layer        | Configuration                    |
| ------------ | -------------------------------- |
| Input        | 28 × 28 grayscale image          |
| Flatten      | Converts image into 784 features |
| Dense        | 128 neurons                      |
| Dense        | 64 neurons                       |
| Output Dense | 10 neurons                       |
| Output       | Probability for each digit       |

The final layer contains **10 neurons**, corresponding to the ten possible digit classes.

---

## ⚙️ Model Compilation

The model was compiled using:

* **Optimizer:** Adam
* **Loss Function:** Sparse Categorical Crossentropy
* **Metric:** Accuracy

Sparse categorical crossentropy was used because the target labels are integer values representing the digit classes.

---

## 🏋️ Model Training

The model was trained using:

* **Epochs:** 10
* **Batch Size:** 32
* **Validation Split:** 20%

During training, the dataset was divided into training and validation portions so that the model's performance could be monitored on unseen validation data.

---

## 📈 Model Performance

The trained neural network achieved approximately:

### **Test Accuracy: 97.67%**

This means the model correctly classified approximately **97.67% of the handwritten digit images in the test dataset**.

---

## 📊 Model Evaluation

The model was evaluated using multiple techniques rather than relying only on accuracy.

### Confusion Matrix

A confusion matrix was used to understand how predictions were distributed across the ten digit classes.

It helps identify which digits the model commonly confuses with one another.

### Classification Report

A classification report was generated to examine:

* Precision
* Recall
* F1-score
* Support

for each digit class.

### Incorrect Predictions

Incorrectly classified images were also analyzed to understand the types of handwritten digits that were difficult for the model to recognize.

---

## 💾 Model Saving

After training, the model was saved in Keras format:

```text
mnist_model.keras
```

This allows the trained model to be reused without training it again.

---

## 🔄 Model Loading and Inference

The saved model can be loaded using:

```python
from tensorflow.keras.models import load_model

model = load_model("mnist_model.keras")
```

The loaded model can then be used to make predictions on new handwritten digit images.

The prediction process is:

```text
New Handwritten Image
        ↓
Resize to 28 × 28
        ↓
Convert to Grayscale
        ↓
Normalize Pixel Values
        ↓
Model Prediction
        ↓
Predicted Digit
```

---

## 🛠️ Technologies Used

* **Python**
* **TensorFlow**
* **Keras**
* **NumPy**
* **Matplotlib**
* **Scikit-learn**
* **Jupyter Notebook**

---

## 📦 Requirements

Install the required libraries using:

```bash
pip install tensorflow numpy matplotlib scikit-learn
```

---

## 📁 Project Structure

```text
MNIST-Handwritten-Digits/
│
├── mnist.ipynb
├── mnist_model.keras
├── README.md
└── requirements.txt
```

---

## ▶️ How to Run the Project

### 1. Clone the Repository

```bash
git clone <repository-url>
```

### 2. Navigate to the Project Directory

```bash
cd MNIST-Handwritten-Digits
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Open the Notebook

```bash
jupyter notebook
```

Open:

```text
mnist.ipynb
```

### 5. Run the Notebook

Execute the cells sequentially to:

1. Load the MNIST dataset
2. Explore the images
3. Preprocess the data
4. Build the neural network
5. Train the model
6. Validate the model
7. Evaluate performance
8. Analyze incorrect predictions
9. Save the trained model

---

## 🧠 Concepts Covered

This project demonstrates practical understanding of:

* Image Classification
* Neural Networks
* Artificial Neurons
* Dense Layers
* Flattening Image Data
* Forward Propagation
* Model Training
* Loss Functions
* Optimizers
* Backpropagation
* Epochs and Batch Size
* Training and Validation Data
* Classification Accuracy
* Confusion Matrix
* Precision, Recall and F1-score
* Model Saving and Loading
* Inference

---

## 🚀 Future Improvements

Possible improvements to the project include:

* Using **Convolutional Neural Networks (CNNs)**
* Adding **Dropout and Regularization**
* Performing **Hyperparameter Tuning**
* Comparing different neural network architectures
* Building an interactive handwritten-digit prediction application
* Deploying the trained model

---

## 👩‍💻 Author

**Aishwari Bambale**

B.Tech — Artificial Intelligence & Data Science
