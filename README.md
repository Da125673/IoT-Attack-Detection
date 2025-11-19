#  IoT Attack Detection Using Random Forest  
A Machine Learning System for Classifying Network Traffic as Normal or Malicious

---

##  Overview  
This project implements a **binary IoT attack detection system** using machine learning.  
Given packet-level network traffic data, the program detects whether each entry represents:

✔ **Normal behavior**  
✔ **Attack traffic**

The model is trained on a Kaggle dataset:  
**Cyber Attacks on Real-Time Internet of Things (IoT)**  
which contains labeled IoT network data with features such as protocol flags, packet sizes, timestamps, and communication patterns.

---

##  ML Model Used  
This project intentionally uses a **different model** than the one used in the research paper so that the work is original and satisfies course requirements.

###  Random Forest Classifier  
Random Forests were chosen because:

- They are simple and fast to train  
- They work well with tabular IoT traffic data  
- They naturally handle noisy features  
- They offer high accuracy without deep learning  
- They are **NOT** used in the original paper as the main model  

The confusion matrix and classification report show the model achieves **~99.7% accuracy**, meaning it perfectly identifies most attack flows.

---

##  Project Structure

IoT-Attack-Detection/
│── attackdetection.py # Main ML script
│── RT_IOT2022.csv # IoT dataset (required for demo)
│── requirements.txt # Python dependencies
│── .gitignore # Excludes venv + temporary files

yaml
Copy code

---

## How to Run the Project

### **1️ Clone the repo**
```bash
git clone https://github.com/sajjadshamoosi/IoT-Attack-Detection.git
cd IoT-Attack-Detection
2️Create a virtual environment
bash
Copy code
python3 -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
3️Install dependencies
bash
Copy code
pip install -r requirements.txt
4️Run the detector
bash
Copy code
python attackdetection.py
This will:

Load the dataset

Encode categorical features

Train the Random Forest model

Test on unseen data

Print accuracy + classification report

Display a confusion matrix image

Results
Example output:

Accuracy: ~0.997

Normal traffic: detected with 98%–100% precision

Attack traffic: detected near 100%

Confusion Matrix: shows very low false positives and false negatives

A graphical confusion matrix is shown during execution.

 How This Connects to the Research Paper
The original paper used:

CNN

XGBoost

SHAP explainability

Deep feature extraction

Hybrid deep learning + boosting

This project is intentionally different, using a simpler model that still demonstrates:

IoT traffic preprocessing

Feature engineering

Classification of attack vs normal behavior

Evaluation metrics used in cybersecurity research

This satisfies the goal of implementing an idea inspired by the paper without copying the paper’s model.

References
Prior Foundational Paper
Bridging Explainability and Security: An XAI-Enhanced Hybrid Deep Learning Framework for IoT Device Identification and Attack Detection
IEEE Access, 2025.
(Used as the conceptual base for the project.)

Modern Follow-Up Work
Cyber Attacks on IoT Networks Using ML-Based Behavioral Classification (Kaggle dataset documentation & associated research).
Explores lightweight ML approaches for real-time IoT anomaly detection.

 Demo Data
The dataset RT_IOT2022.csv is included directly in this repository so instructors can:

Clone the repo

Install dependencies

Run the script

Reproduce the exact results shown in class

No external downloads are required for grading.

 Lessons Learned
Converting categorical network fields to numeric features is essential

IoT datasets are often imbalanced

RandomForest provides high accuracy with low computational cost

Data preprocessing had a larger impact than model complexity

GitHub repo organization + reproducibility is crucial for ML projects

Contributors
Sajjad Shamoosi
Daniel Alamanza
Yosselin Zavala
Zainab Khan
Victoria Castillo
