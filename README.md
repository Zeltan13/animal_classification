# CNN-Based Image Classification with MobileNetV2

## 📌 Project Overview
This project is a deep learning-based image classification model using a **CNN with MobileNetV2 as a feature extractor**. The model classifies images into three categories: **Cat, Dog, and Spider**. The dataset consists of **14.115 images** with varying resolutions.

## 📂 Dataset
- **Total Images:** 14.115
- **Classes:** Cat, Dog, Spider
- **Train-Validation-Test Split:** 80:10:10
- **Image Resolution:** Varies (without preprocessing for uniformity)

## 🏗️ Model Architecture
- **Base Model:** MobileNetV2 (Pretrained on ImageNet)
- **Additional Layers:**
  - Conv2D (128, 256, 512, 1024 filters) + BatchNormalization + ReLU Activation
  - MaxPooling Layers
  - Fully Connected Layers (1024 Dense, Dropout 0.3)
  - Softmax for classification
- **Optimizer:** Adam (`learning_rate=0.0005`)
- **Loss Function:** Categorical Crossentropy
- **Performance:** Achieved **95%+ accuracy** on test set.

## 📊 Training & Callbacks
- **Epochs:** 50
- **Callbacks:**
  - **Learning Rate Scheduler** (ReduceLROnPlateau)

## 📈 Results
- **Train Accuracy:** 97.73%
- **Validation Accuracy:** 98.58%
- **Test Accuracy:** 98.16%
- **Loss & Accuracy Plots:** Included in the notebook.

## 🚀 Model Deployment
The trained model is saved in **three formats**:
1. **SavedModel** (`saved_model/`)
2. **TF-Lite** (`tflite/model.tflite`)
3. **TensorFlow.js** (`tfjs_model/`)

## 📦 Installation & Requirements
Install dependencies using:
```
pip install -r requirements.txt
```

## 🚀 Running Inference  
You can test the model by running the provided inference code blocks inside the Jupyter Notebook.  
If you want to use different images, simply update the `image_paths` variable with the correct file paths.  

### 🏷️ 1️⃣ TF-Lite Inference  
To run inference using the **TF-Lite model**, execute the **TF-Lite inference code block** in the Jupyter Notebook.  

- Ensure the `tflite/model.tflite` file is present.  
- If needed, update the `image_paths` list to include the images you want to test.  

### 🏷️ 2️⃣ SavedModel Inference  
To run inference using the **SavedModel**, execute the **SavedModel inference code block** in the Jupyter Notebook.  

- Make sure the `saved_model/` directory exists.  
- Update the `image_paths` list if you want to use different images.  

> 📌 **Note:** Both inference scripts will display the image and print the predicted class with confidence scores.
