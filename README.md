# 🛡️ Network Intrusion Detection using Stacked Ensemble Learning

> **Optimizing Network Security via Ensemble Learning**

A Machine Learning-based **Network Intrusion Detection System (NIDS)** that identifies malicious network traffic using a **Stacked Ensemble Learning** architecture. This project combines the strengths of multiple machine learning algorithms to improve intrusion detection accuracy while reducing false positives.

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Features](#-features)
- [Dataset](#-dataset)
- [Project Workflow](#-project-workflow)
- [Machine Learning Models](#-machine-learning-models)
- [Stacked Ensemble Learning](#-stacked-ensemble-learning)
- [Evaluation Metrics](#-evaluation-metrics)
- [Results](#-results)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Future Enhancements](#-future-enhancements)
- [References](#-references)
- [Authors](#-authors)

---

# 📌 Overview

Cyber attacks continue to grow in frequency and sophistication, making automated intrusion detection essential for modern networks. Traditional signature-based Intrusion Detection Systems (IDS) are limited to identifying previously known attacks and often fail to detect new or evolving threats.

This project presents a **Machine Learning-based Network Intrusion Detection System (NIDS)** capable of classifying network traffic as either **Normal** or **Anomalous**. Instead of relying on a single algorithm, it implements a **Stacked Ensemble Learning** architecture that combines multiple machine learning models to improve prediction accuracy, reduce false positives, and provide a more robust detection system.

---

# 🎯 Problem Statement

Network intrusions involve unauthorized access or malicious activities that compromise the confidentiality, integrity, or availability of computer networks.

Common objectives of attackers include:

- Unauthorized access
- Data theft
- Service disruption
- Malware deployment
- Network exploitation

Traditional IDS solutions suffer from several limitations:

- Detection limited to known attack signatures
- High false positive rates
- Difficulty identifying zero-day attacks
- Limited adaptability to changing network behavior

This project aims to overcome these challenges using ensemble machine learning techniques capable of learning complex traffic patterns and improving intrusion detection performance.

---

# 🚀 Features

- Binary classification of network traffic
- Data preprocessing pipeline
- Feature engineering
- Multiple machine learning algorithms
- Stacked Ensemble Learning architecture
- Cross-validation
- Performance evaluation using multiple metrics
- Scalable and extensible design

---

# 📊 Dataset

The project utilizes the **Network Intrusion Detection Dataset** obtained from Kaggle.

## Dataset Statistics

| Property | Value |
|----------|-------|
| Total Samples | **50,384** |
| Features | **42** |
| Classes | Normal / Anomaly |

### Class Distribution

| Class | Samples |
|--------|---------|
| Normal | 26,898 |
| Anomaly | 23,486 |

Each network connection contains multiple traffic-related attributes including:

- Protocol Type
- Service
- Source Bytes
- Destination Bytes
- Login Information
- Error Rates
- Connection Statistics
- Host Statistics

These features enable machine learning models to distinguish between legitimate and malicious network traffic.

---

# ⚙️ Project Workflow

```text
                Dataset
                   │
                   ▼
        Data Preprocessing
                   │
                   ▼
         Feature Engineering
                   │
                   ▼
          Train/Test Split
                   │
                   ▼
            Base Learners
      ┌────────┬────────┬────────┬────────┐
      │  MLP   │  KNN   │ Naïve  │Decision│
      │        │        │ Bayes  │  Tree  │
      └────────┴────────┴────────┴────────┘
                   │
                   ▼
        Stacked Ensemble Model
                   │
                   ▼
          Final Predictions
                   │
                   ▼
        Performance Evaluation
```

---

# 🤖 Machine Learning Models

## Multi-Layer Perceptron (MLP)

- Neural network with multiple hidden layers
- Learns complex nonlinear relationships
- Trained using backpropagation

### Advantages

- High predictive capability
- Captures complex patterns
- Suitable for nonlinear classification

---

## K-Nearest Neighbors (KNN)

- Distance-based classification algorithm
- Predicts class using nearest neighboring samples

### Advantages

- Simple implementation
- Effective on structured datasets
- No explicit training phase

---

## Naïve Bayes

A probabilistic classifier based on Bayes' Theorem assuming conditional independence among features.

### Advantages

- Extremely fast
- Memory efficient
- Excellent baseline classifier

---

## Decision Tree

A tree-based classifier that recursively partitions data into homogeneous groups.

### Advantages

- Highly interpretable
- Easy visualization
- Captures nonlinear decision boundaries

---

# 🧠 Stacked Ensemble Learning

Rather than relying on a single classifier, this project combines multiple learning algorithms into a **Stacked Ensemble**.

### Base Models

- Multi-Layer Perceptron (MLP)
- K-Nearest Neighbors (KNN)
- Naïve Bayes
- Decision Tree

Each base learner independently predicts the network traffic class.

Their predictions become inputs for a **Meta Model**, which learns the optimal way to combine them and generate the final prediction.

## Benefits

- Higher classification accuracy
- Reduced overfitting
- Lower false positives
- Better generalization
- Improved robustness
- Increased reliability

Cross-validation is employed while training the stacking model to prevent information leakage and improve generalization.

---

# 📈 Evaluation Metrics

The models are evaluated using standard classification metrics:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

These metrics provide a balanced evaluation of both detection capability and false alarm rates.

---

# 📊 Results

The Stacked Ensemble model demonstrated strong predictive performance in detecting network intrusions.

### Highlights

- High overall classification accuracy
- Excellent balance between Precision and Recall
- Reduced false positive rate
- Reliable anomaly detection
- Improved performance over individual classifiers

The confusion matrix indicates that the ensemble successfully classifies the majority of network traffic while minimizing classification errors.

---

# 💻 Tech Stack

| Category | Technologies |
|-----------|-------------|
| Programming Language | Python |
| Machine Learning | Scikit-learn |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib |
| Development | Jupyter Notebook |

---

# 📁 Project Structure

```text
Network-Intrusion-Detection/
│
├── data/
│   ├── train.csv
│   └── test.csv
│
├── notebooks/
│   └── Network_Intrusion_Detection.ipynb
│
├── models/
│
├── images/
│
├── requirements.txt
│
├── README.md
│
└── LICENSE
```

---

# 📌 Key Takeaways

- Ensemble learning significantly improves intrusion detection performance.
- Combining multiple classifiers enhances prediction reliability.
- Feature engineering contributes substantially to model accuracy.
- Cross-validation helps prevent overfitting.
- The proposed framework is scalable for real-world cybersecurity applications.

---

# 🔮 Future Enhancements

Future improvements may include:

- Deep Learning-based IDS
- GAN-generated synthetic attack traffic
- Real-time intrusion detection
- Explainable AI (XAI)
- Cloud deployment (AWS/Azure)
- Docker containerization
- REST API using Flask or FastAPI
- SIEM integration
- Multi-class attack classification

---

# 📚 References

- Kaggle Network Intrusion Detection Dataset
- Sinclair, C., Pierce, L., & Matzner, S. (1999). *An Application of Machine Learning to Network Intrusion Detection.*
- Shone, N., Ngoc, T. N., Phai, V. D., & Shi, Q. (2018). *A Deep Learning Approach to Network Intrusion Detection.*
- Ennaji, S., El Akkad, N., & Haddouch, K. (2021). *A Powerful Ensemble Learning Approach for Improving Network Intrusion Detection Systems.*

---

# 👥 Authors

**Anu Baluguri**

**Vasudha Pasumarthy**

**Course:** CSC 691 – Machine Learning in Cyber Security

**Project Title:** Optimizing Network Security via Ensemble Learning: A Nexus with Intrusion Detection

---

# ⭐ If you found this project useful, consider giving it a star!

```
⭐ Star this repository if you found it helpful!
```
