# Phishing Website Detection using Support Vector Machine (SVM)

<div align="center">

### Intelligent Machine Learning System for Detecting Phishing Websites
*Classifying websites as Legitimate or Phishing using Support Vector Machine (SVM) and feature-based analysis.*

</div>

---

## 1. Project Title & Overview

The **Phishing Website Detection System** is a Machine Learning-based cybersecurity project designed to identify whether a website is **Legitimate** or **Phishing** based on its extracted website features.

* **What it does:** The system analyzes website-related attributes such as URL details, server information, WHOIS records, and traffic-based features, then predicts whether the website is safe or malicious.
* **Why it exists:** Phishing websites are one of the most common cyber threats used to steal passwords, banking credentials, and personal information.
* **The Problem it Solves:** This system helps automate phishing website detection using Machine Learning, reducing the risk of users interacting with harmful websites.

---

## 2. System Workflow

### Input → Processing → Output Pipeline

1. **Dataset Input:** The system accepts a phishing website dataset (`phishing_data.csv`) containing website-related features.
2. **Data Preprocessing:** Raw website data is cleaned, encoded, and transformed into machine-readable numerical format.
3. **Feature Engineering:** Categorical values such as URL, server, and WHOIS details are converted into numerical labels.
4. **Model Training:** A Support Vector Machine (SVM) model is trained using historical website records.
5. **Prediction Engine:** The trained model predicts whether a website is phishing or legitimate.
6. **Performance Evaluation:** The model is evaluated using accuracy score, confusion matrix, and classification report.
7. **Visualization:** A heatmap is generated to visually represent prediction performance.

---

## 3. Technology Stack

### Development Environment
* **Google Colab:** Used for project development, dataset upload, and model execution.

### Programming Language
* **Python:** Used for data processing, Machine Learning, and prediction.

### Libraries & Tools
* **Pandas:** Used for loading and processing the dataset.
* **NumPy:** Used for numerical operations.
* **Scikit-learn:** Used for preprocessing, model building, training, and evaluation.
* **Matplotlib:** Used for plotting graphs.
* **Seaborn:** Used for heatmap visualization.

---

## 4. Machine Learning Model

### Support Vector Machine (SVM)

The core of this project is the **Support Vector Machine (SVM)** algorithm.

* **What is SVM?**  
  Support Vector Machine is a supervised Machine Learning algorithm used for classification tasks.

* **How it works in this project:**  
  SVM learns patterns from website data and separates them into two classes:
  * **Legitimate Website** → Safe website
  * **Phishing Website** → Malicious website

* **Why SVM is used:**  
  SVM is effective for binary classification problems and performs well on structured datasets like phishing detection.

---

## 5. Dataset Information

### Dataset Used
**File Name:** `phishing_data.csv`

The dataset contains website-related features used to classify websites.

### Input Features
The model uses the following features:

* URL
* CHARSET
* SERVER
* WHOIS_COUNTRY
* WHOIS_STATEPRO
* WHOIS_REGDATE
* WHOIS_UPDATED_DATE
* URL_LENGTH
* NUMBER_SPECIAL_CHARACTERS
* TCP_CONVERSATION_EXCHANGE
* DIST_REMOTE_TCP_PORT
* REMOTE_IPS
* APP_BYTES
* SOURCE_APP_PACKETS
* REMOTE_APP_PACKETS
* SOURCE_APP_BYTES
* REMOTE_APP_BYTES
* APP_PACKETS
* DNS_QUERY_TIMES

### Target Output
* **Type**
  * `0` → Legitimate Website
  * `1` → Phishing Website

---

## 6. Data Preprocessing

Before training the model, the raw dataset is preprocessed.

### Steps Performed

1. **Dataset Copying:**  
   A duplicate copy of the original dataset is created for safe preprocessing.

2. **Label Encoding:**  
   Categorical text values are converted into numeric values using `LabelEncoder`.

   Example:
   * `"Apache"` → `3`
   * `"US"` → `7`

3. **Missing Value Handling:**  
   Missing values are filled using `SimpleImputer` with median strategy.

4. **Feature Separation:**  
   The dataset is split into:
   * **X** → Input features
   * **y** → Target output

---

## 7. Model Training Process

### Step 1: Train-Test Split
The dataset is divided into:

* **80% Training Data**
* **20% Testing Data**

Training data is used to teach the model, while testing data is used to evaluate it.

### Step 2: Feature Scaling
The numerical values are normalized using `StandardScaler`.

This ensures all features are in a similar range and improves model performance.

### Step 3: Model Training
The SVM model is trained using:

```python
model = SVC(kernel='rbf')
model.fit(X_train, y_train)

---

## 8. Output & Results Overview

After training, the model produces the following outputs:

### 1. Accuracy Score
The model calculates overall prediction accuracy.

* **What it shows:**  
  The percentage of correctly predicted websites.

Example:
```python
Accuracy: 0.95
2. Confusion Matrix

The confusion matrix shows detailed prediction results.

Example:

[[120  10]
 [  8 110]]

It shows:

Correct Legitimate predictions
Incorrect Legitimate predictions
Correct Phishing predictions
Incorrect Phishing predictions

This gives a complete breakdown of prediction quality.

3. Classification Report

The classification report shows:

Precision → How many predicted phishing websites were actually phishing
Recall → How many real phishing websites were correctly identified
F1-Score → Overall balance between precision and recall

This provides deeper insight into model performance.

4. Heatmap Visualization

The confusion matrix is displayed as a heatmap.

What it shows:
A visual representation of prediction results using colored cells.

This makes model performance easier to understand.

5. Sample Prediction

The model predicts one test sample and compares:

Predicted result
Actual result

This helps verify real prediction behavior.

6. Custom Website Prediction

The system also allows manual website prediction by entering custom feature values.

Example Output:

Custom Website Prediction: Phishing Website

This allows real-time phishing testing for new websites.

9. Advantages of the Project

Detects phishing websites automatically
Improves cybersecurity awareness
Reduces risk of malicious website access
Fast and efficient binary classification
Can be extended for real-time detection systems

10. Future Improvements

Deploy as a web application
Add real-time URL scanning
Improve performance using advanced ML models
Integrate browser-based phishing alerts
Build live phishing detection dashboard

11. Conclusion

The Phishing Website Detection System is a simple and effective Machine Learning project for identifying phishing websites.

By using Support Vector Machine (SVM), the system learns from website features and predicts whether a website is:

Legitimate Website
Phishing Website

This project demonstrates how Machine Learning can be applied in cybersecurity to protect users from malicious websites.

12. Files Included
Phishing_Detection.ipynb
phishing_data.csv
README.md
