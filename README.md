# ???? Pet Image Segmentation and Detection with TensorFlow

This project explores **computer vision techniques** using deep learning to localize pets in images from the **Oxford-IIIT Pet Dataset**. It covers two related but distinct tasks:

1. **Semantic Segmentation** (pixel-level prediction)
2. **Object Detection** (bounding box regression)

The models are implemented and trained using **TensorFlow / Keras** and **TensorFlow Datasets**.

---

## ?? Dataset

* **Oxford-IIIT Pet Dataset**
* Contains images of cats and dogs with:

  * Class labels
  * Pixel-wise segmentation masks

Loaded directly via:

```
tensorflow_datasets.load("oxford_iiit_pet")
```

---

## ?? Project Structure

### Question 1 — Semantic Segmentation

**Goal:**
Predict a binary mask indicating which pixels belong to the pet.

**Input:**

* RGB image (128×128)

**Output:**

* Binary segmentation mask (128×128)

**Models implemented:**

* Simple CNN-based encoder–decoder
* **U-Net** architecture with skip connections

**Techniques:**

* Image resizing and normalization
* Binary mask generation
* Pixel-wise binary cross-entropy loss

**Visualization:**

* Original image
* Ground truth mask
* Predicted mask

---

### Question 2 — Object Detection (Bounding Box Regression)

**Goal:**
Predict a bounding box tightly enclosing the pet.

**Input:**

* RGB image (128×128)

**Output:**

* Bounding box coordinates:

```
[x_min, y_min, x_max, y_max] ? [0,1]
```

**Key idea:**
Bounding boxes are automatically extracted from segmentation masks and used as training labels.

**Model:**

* CNN regression network

**Loss & Metrics:**

* Mean Squared Error (MSE)
* Mean Absolute Error (MAE)
* **Intersection over Union (IoU)** (custom metric)

---

## ?? Evaluation

* Training and validation curves for:

  * Loss
  * Accuracy (segmentation)
  * MAE and IoU (detection)
* Visual inspection of predicted masks and bounding boxes

---

## ??? Technologies Used

* Python
* TensorFlow / Keras
* TensorFlow Datasets
* NumPy
* Matplotlib

---

## ?? How to Run

1. Install dependencies:

```bash
pip install tensorflow tensorflow-datasets matplotlib
```

2. Run the script:

```bash
python andres_ghersi_sayan_20539425_hw4.py
```

> The code was originally developed in Google Colab and later exported as a Python script.

---

## ?? Key Takeaways

* Demonstrates the difference between **segmentation** and **detection**
* Shows how segmentation masks can be reused to generate bounding boxes
* Compares a simple CNN with a U-Net architecture
* Implements a custom IoU metric from scratch

---

## ?? Author

**Andres Ghersi Sayan**
Master’s Program in Computer Science
Student ID: 20539425