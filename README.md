#  Yoga Pose Classification with MobileNetV2 (Transfer Learning)

This project classifies **five yoga poses** using a deep learning model. We used a dataset sourced from **Kaggle**, applied **data augmentation**, and compared a custom **CNN model** with a **MobileNetV2 transfer learning approach**.

---

## 📂 Dataset

The dataset was downloaded from Kaggle and contains labeled images for the following 5 yoga poses:

- 🐶 **Adho Mukha Svanasana** (Downward Dog)
- 🧒 **Balasana** (Child's Pose)
- 🧍‍♀️ **Utkata Konasana** (Goddess Pose)
- 🧘 **Virabhadrasana** (Warrior Pose)
- 🌳 **Vrikshasana** (Tree Pose)

---

## 📊 Results

| Model         | Training Accuracy | Validation Accuracy |
|---------------|-------------------|---------------------|
| Custom CNN    | 66.4%             | 45.9%               |
| MobileNetV2   | **96.17%**        | **91.51%**          |

The MobileNetV2-based model significantly outperformed the CNN in both accuracy and stability.

---

## 🔧 Model Architecture

### ✅ MobileNetV2 (Transfer Learning)
- Base: `MobileNetV2` with `imagenet` weights
- Global Average Pooling
- Dense (128, ReLU) + Dropout(0.3)
- Output: Dense (5 units, softmax)

### ❌ CNN (from scratch)
- Multiple Conv2D + MaxPooling2D layers
- Flatten → Dense → Dropout
- Performance limited due to small dataset size

---

## 🚀 Training Details
- Input size: 224x224 RGB images
- Optimizer: Adam (lr = 0.0005, then fine-tuned with 1e-5)
- Loss: Categorical Crossentropy
- Data Augmentation: Rotation, flip, zoom, shift
- Early stopping applied to avoid overfitting

---

## XAI on Yogasana dataset
- When applied XAI algorithms such as LIME and SHAP, I realised that the given accuracy was actually not worth it.
- The model seems to learn only the background ad not actually the pose.
<img width="432" height="435" alt="LIME" src="https://github.com/user-attachments/assets/cfe24b12-d14b-4264-a0b3-5e39d82313d7" />
<img width="890" height="445" alt="SHAP" src="https://github.com/user-attachments/assets/396ade89-e13f-46a1-bc6f-3b4588ecdbda" />


