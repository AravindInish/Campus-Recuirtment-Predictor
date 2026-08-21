# 🎓 Campus Placement Prediction

<div align="center">

## 🤖 AI-Powered Campus Placement Prediction

### 🧠 Deep Learning-Based Student Placement Classification

**Predict whether a student is likely to be placed using academic, educational and career-related information.**

<br>

`🐍 Python 3.12`   `🧠 TensorFlow`   `📊 Scikit-Learn`   `🌐 Streamlit`   `🐼 Pandas`   `🔢 NumPy`

<br>

**🎯 Binary Classification • 🧠 Neural Network • 📈 Predictive Analytics • 🌐 Web Application**

⭐ **Star this repository if you find it useful!**

</div>

---

# 📖 Overview

**Campus Placement Prediction** is a Deep Learning project designed to predict a student's **placement status** based on academic performance, educational background, work experience and employability-related attributes.

The project follows a complete Machine Learning workflow:

```text
📊 Dataset
   ↓
🧹 Data Cleaning
   ↓
⚙️ Data Preprocessing
   ↓
🔢 Feature Transformation
   ↓
🧠 Neural Network
   ↓
📈 Model Evaluation
   ↓
💾 Model Saving
   ↓
🌐 Streamlit Application
```

The trained model can be used through an interactive **Streamlit Web Application** where users enter student information and receive a placement prediction.

---

# ✨ Key Highlights

| 🚀 Feature              | 📌 Description                                    |
| ----------------------- | ------------------------------------------------- |
| 🎓 Placement Prediction | Predict `Placed` / `Not Placed`                   |
| 🧠 Deep Learning        | TensorFlow/Keras Neural Network                   |
| 🧹 Data Cleaning        | Missing-value treatment & feature cleanup         |
| 🔢 Feature Scaling      | StandardScaler for numerical features             |
| 🔤 Encoding             | OneHotEncoder for categorical features            |
| 📊 Data Analysis        | Dataset inspection & model training visualization |
| 💾 Model Persistence    | Saved `.h5` model and `.pkl` preprocessor         |
| 🌐 Web App              | Interactive Streamlit prediction interface        |
| ⚡ Real-Time Prediction  | Enter details and generate prediction             |

---

# 📊 Dataset

The project uses the **Factors Affecting Campus Placement** dataset.

### 📌 Dataset Statistics

```text
📦 Total Records       : 215
📋 Original Columns    : 15
🧹 Final Columns       : 14
🎯 Target Variable     : status
🏷️ Classification      : Binary
```

### 🎯 Target

```text
✅ Placed       → 1
❌ Not Placed   → 0
```

---

# 🧩 Features

### 🔢 Numerical Features

```text
📌 ssc_p
📌 hsc_p
📌 degree_p
📌 etest_p
📌 mba_p
📌 salary
```

### 🔤 Categorical Features

```text
👤 gender
🏫 ssc_b
🏫 hsc_b
📚 hsc_s
🎓 degree_t
💼 workex
🎯 specialisation
```

---

# 🧹 Data Preprocessing

The dataset goes through a structured preprocessing pipeline.

### 🔧 Processing Steps

```text
📥 Load Dataset
      ↓
🔍 Inspect Dataset
      ↓
🧹 Handle Missing Values
      ↓
🗑️ Remove `sl_no`
      ↓
🎯 Encode Target
      ↓
✂️ Train / Test Split
      ↓
🔢 Scale Numerical Features
      ↓
🔤 Encode Categorical Features
```

### 🛠️ Preprocessing Configuration

* `salary` missing values → filled with `0`
* `sl_no` → removed as an identifier
* Numerical features → `StandardScaler`
* Categorical features → `OneHotEncoder`
* Unknown categorical values → safely ignored
* Train/Test split → **80% / 20%**
* Random state → **42**
* Stratification → enabled

### 📐 Dataset Split

```text
🟦 Training Samples : 172
🟧 Testing Samples  : 43

Before Processing : 13 Features
After Processing  : 22 Features
```

---

# 🧠 Deep Learning Model

The project uses a **Sequential Neural Network** built with TensorFlow/Keras.

### 🏗️ Architecture

```text
                ┌──────────────────────┐
                │     INPUT LAYER      │
                │      22 Features     │
                └──────────┬───────────┘
                           ↓
                ┌──────────────────────┐
                │     DENSE LAYER      │
                │      64 Neurons      │
                │        ReLU          │
                └──────────┬───────────┘
                           ↓
                ┌──────────────────────┐
                │     DENSE LAYER      │
                │      32 Neurons      │
                │        ReLU          │
                └──────────┬───────────┘
                           ↓
                ┌──────────────────────┐
                │    OUTPUT LAYER     │
                │       1 Neuron      │
                │      Sigmoid        │
                └──────────┬───────────┘
                           ↓
                  🎯 PLACED / NOT PLACED
```

### ⚙️ Model Configuration

| ⚙️ Parameter      | 🔧 Configuration    |
| ----------------- | ------------------- |
| Framework         | TensorFlow / Keras  |
| Architecture      | Sequential          |
| Hidden Layer 1    | 64 neurons          |
| Hidden Layer 2    | 32 neurons          |
| Activation        | ReLU                |
| Output            | 1 neuron            |
| Output Activation | Sigmoid             |
| Optimizer         | Adam                |
| Loss Function     | Binary Crossentropy |
| Epochs            | 50                  |
| Batch Size        | 32                  |
| Validation Split  | 20%                 |

---

# 📈 Model Training

The model is trained for **50 epochs** with a batch size of **32**.

Training and validation performance are tracked using:

```text
📈 Training Accuracy
📈 Validation Accuracy
📉 Training Loss
📉 Validation Loss
```

This helps visualize how the neural network learns throughout the training process.

---

# 💾 Model Deployment

After training, two important files are generated:

```text
📦 placement_model.h5
      └── 🧠 Trained Neural Network

📦 preprocessor.pkl
      └── ⚙️ Saved Data Preprocessing Pipeline
```

These files allow the Streamlit application to load the trained pipeline without retraining the model every time.

---

# 🌐 Streamlit Web Application

The project includes an interactive web application built with **Streamlit**.

### 🖥️ User Flow

```text
👤 Student
   ↓
📝 Enter Student Details
   ↓
🎓 Academic Information
   ↓
💼 Work Experience
   ↓
📚 Educational Background
   ↓
⚙️ Preprocessing
   ↓
🧠 Neural Network
   ↓
🎯 Placement Prediction
```

### 🎛️ Input Parameters

The application allows users to enter:

* 👤 Gender
* 📊 SSC Percentage
* 🏫 SSC Board
* 📊 HSC Percentage
* 🏫 HSC Board
* 📚 HSC Specialization
* 🎓 Degree Percentage
* 🎓 Degree Type
* 💼 Work Experience
* 📈 Employability Test Percentage
* 🎯 MBA Specialisation
* 📊 MBA Percentage

The application then generates a placement prediction.

---

# 🛠️ Tech Stack

```text
🐍 Python
│
├── 🐼 Pandas
├── 🔢 NumPy
├── 📊 Matplotlib
│
├── 🤖 Scikit-Learn
│   ├── StandardScaler
│   ├── OneHotEncoder
│   ├── ColumnTransformer
│   └── train_test_split
│
├── 🧠 TensorFlow / Keras
│   ├── Sequential
│   └── Dense
│
├── 🌐 Streamlit
├── 💾 Joblib
└── 🚇 Pyngrok
```

---

# 📂 Project Structure

```text
📦 Campus-Placement-Prediction
│
├── 📓 Campus_Recruitment.ipynb
│
├── 🌐 app.py
│
├── 🧠 placement_model.h5
│
├── ⚙️ preprocessor.pkl
│
├── 📊 Placement_Data_Full_Class.csv
│
└── 📖 README.md
```

---

# 🚀 Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/campus-placement-prediction.git
cd campus-placement-prediction
```

### 2️⃣ Install Dependencies

```bash
pip install pandas numpy matplotlib scikit-learn tensorflow streamlit joblib
```

### 3️⃣ Run the Streamlit Application

```bash
streamlit run app.py
```

### 4️⃣ Open in Browser

```text
🌐 Local URL
        ↓
http://localhost:8501
```

---

# 🔬 End-to-End Workflow

```text
        📊 RAW DATA
             │
             ▼
      🔍 DATA EXPLORATION
             │
             ▼
       🧹 DATA CLEANING
             │
             ▼
     ⚙️ PREPROCESSING
             │
      ┌──────┴──────┐
      ▼             ▼
 🔢 Numerical    🔤 Categorical
   Scaling          Encoding
      └──────┬──────┘
             ▼
       ✂️ DATA SPLIT
             │
             ▼
       🧠 MODEL TRAINING
             │
             ▼
        📈 EVALUATION
             │
             ▼
         💾 SAVE MODEL
             │
             ▼
       🌐 STREAMLIT APP
             │
             ▼
       🎯 PREDICTION
```

---

# 💡 What I Learned

Through this project, I worked with:

```text
🐍 Python Programming
        +
📊 Data Preprocessing
        +
🔢 Feature Engineering
        +
🧠 Neural Networks
        +
📈 Model Evaluation
        +
💾 Model Persistence
        +
🌐 Streamlit Deployment
```

The project demonstrates how a Deep Learning model can be transformed from a **Jupyter Notebook experiment** into a practical **interactive web application**.

---

# 🔮 Future Improvements

```text
🚀 Future Roadmap
│
├── 📊 Confusion Matrix
├── 📈 Classification Report
├── 🎯 Prediction Probability
├── 🔍 Model Explainability
├── 🧠 Compare ML Algorithms
│   ├── Random Forest
│   ├── Logistic Regression
│   └── XGBoost
│
├── 🎨 Advanced Streamlit UI
├── 📊 Placement Analytics Dashboard
├── ☁️ Cloud Deployment
└── 📱 Responsive Web Interface
```

---

# ⚠️ Disclaimer

> **This project is intended for educational and experimental purposes.**
>
> The prediction is generated from historical training data and should **not** be considered a guaranteed indicator of an individual's actual placement outcome.

---

# 👨‍💻 Author

<div align="center">

## 🚀 Aravind

🎓 **AI & Data Science Student**
🧠 **AI & Machine Learning Enthusiast**
💻 **Developer & Builder**

<br>

**"Turning Data → Intelligence → Real-World Applications."**

<br>

⭐ **If this project helped you, consider giving it a star!**

</div>

---

<div align="center">

### 🧠 Built with Python • TensorFlow • Scikit-Learn • Streamlit

**Made with ❤️ + ☕ + Code**

</div>
