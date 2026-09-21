# Privacy-Preserving Federated OCT Retinal Disease Classification

### Using a Hybrid Residual-Attention Network

This repository contains my published research work on privacy-preserving
retinal disease classification from Optical Coherence Tomography (OCT)
images using a Hybrid Residual-Attention Network, Federated Learning,
Differential Privacy, and Grad-CAM explainability.

## 📄 Publication

**Title:**  
Privacy-Preserving Federated OCT Retinal Disease Classification using a Hybrid Residual-Attention Network

**Authors:**  
Swapnil Shetty, Puneeth R P

**Published in:**  
2026 6th International Conference on Inventive Computation and Information Technologies (ICICIT)

**Publisher:**  
IEEE

**Conference Location:**  
Salem, India

**Conference Dates:**  
06–08 July 2026

**Publication Year:**  
2026

**DOI:**  
10.1109/ICICIT69063.2026.11634247

**IEEE Xplore:**  
[View Publication on IEEE Xplore](https://doi.org/10.1109/ICICIT69063.2026.11634247)

## 🔬 Research Overview

This research proposes a privacy-preserving framework for multi-class
retinal disease classification using Optical Coherence Tomography (OCT)
images.

The framework combines:

- Hybrid Residual-Attention Network (ResAttnNet)
- Federated Learning (FL)
- Differential Privacy (DP)
- Grad-CAM Explainability

The proposed approach is designed to enable decentralized learning
without transmitting raw medical images between participating clients.

## 🧠 Methodology

The proposed framework consists of four major components:

### 1. Hybrid Residual-Attention Network

ResAttnNet combines residual learning with Squeeze-and-Excitation (SE)
attention to extract diagnostically relevant features from OCT images.

### 2. Federated Learning

Federated learning is used to train the model across simulated clients
while keeping the original OCT images local to each client.

FedAvg is used to aggregate model updates at the server.

### 3. Differential Privacy

Differential Privacy is incorporated through DP-SGD using gradient
clipping and Gaussian noise to provide a measurable privacy-utility
trade-off.

### 4. Grad-CAM Explainability

Grad-CAM is used to generate class-discriminative heatmaps that provide
visual explanations of the model's predictions.

## 🩺 Dataset

The experiments use the publicly available OCT2017 Retinal Image Dataset.

The classification task contains four classes:

- CNV — Choroidal Neovascularization
- DME — Diabetic Macular Edema
- DRUSEN
- NORMAL

Images were resized to **224 × 224 pixels**, converted from
single-channel to three-channel format, normalized, and augmented using
random horizontal flipping and rotation.

The data was distributed among three simulated clients using a
Dirichlet-based Non-IID distribution with **α = 0.1**.

## 🌐 Federated Learning Configuration

| Configuration | Value |
|---|---:|
| Number of Clients | 3 |
| FL Algorithm | FedAvg |
| Communication Rounds | 3 |
| Local Epochs | 1 |
| Batch Size | 32 |
| Optimizer | Adam |
| Learning Rate | 1 × 10⁻⁴ |
| Gradient Clipping Norm | 1.0 |
| δ | 10⁻⁵ |
| DP Noise σ | 0.02, 0.05 |

## 📊 Experimental Results

The paper reports the following classification accuracies:

| Method | Noise (σ) | Accuracy |
|---|---:|---:|
| Centralized Learning | 0 | **99.27%** |
| Federated Learning (IID) | 0 | **99.38%** |
| FL + DP (Non-IID) | 0.02 | **95.40%** |
| FL + DP (Non-IID) | 0.05 | **81.90%** |

The results demonstrate the reported privacy-utility trade-off as the
noise multiplier increases.

## 📈 Additional Evaluation

The reported per-class AUC-ROC values are:

| Class | AUC |
|---|---:|
| CNV | 0.9990 |
| DME | 0.9952 |
| DRUSEN | 0.9999 |
| NORMAL | 0.9996 |

Grad-CAM visualizations were also generated for the four disease
categories to examine the regions contributing to model predictions.

## 🔑 Research Areas

- Federated Learning
- Differential Privacy
- Medical Image Analysis
- Optical Coherence Tomography
- Deep Learning
- Computer Vision
- Residual Networks
- Attention Mechanisms
- Explainable AI
- Privacy-Preserving Machine Learning

## 📌 Key Contributions

- Hybrid Residual-Attention Network for OCT retinal disease classification.
- Federated training using FedAvg across simulated clients.
- Differential Privacy using DP-SGD.
- Non-IID data simulation using Dirichlet distribution.
- Grad-CAM-based visual interpretability.
- Evaluation of the privacy-utility trade-off under different noise levels.

## ⚠️ Scope and Limitations

The reported federated learning experiments use a simulation of
three clients rather than three real hospitals or healthcare
institutions.

The study also uses fixed differential privacy noise rather than
dynamically adjusting the noise multiplier during training.

Additionally, the Grad-CAM interpretations were not formally validated
by ophthalmologists.

Future work identified in the paper includes large-scale multi-hospital
federated learning, dynamically adjusted differential privacy, and
integration with clinical systems such as PACS and EMR.

## 📄 Full Paper

The published manuscript is available in the [`paper/`](paper/) directory.

**[Read the Full Research Paper](paper/privacy-preserving-federated-oct-paper.pdf)**

**[View the Publication on IEEE Xplore](https://doi.org/10.1109/ICICIT69063.2026.11634247)**

## 👤 Author

**Swapnil Shetty**

M.Tech – Computer Science and Engineering  
NMAM Institute of Technology, Nitte
