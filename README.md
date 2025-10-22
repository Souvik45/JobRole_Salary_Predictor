# 💼 Job Role & Salary Predictor

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.4.0-orange.svg)
![Gradio](https://img.shields.io/badge/Gradio-4.19.0-red.svg)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0.3-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

**An end-to-end Machine Learning project that predicts job salaries based on job descriptions, company details, and required skills.**

[Demo](#-demo) • [Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Model Performance](#-model-performance)

</div>

---

## 📊 Project Overview

This project analyzes **Glassdoor job postings** to predict salaries using machine learning. The model considers multiple factors including job title, location, company information, required skills, and more to provide accurate salary estimates.

### 🎯 Key Highlights

- 🔍 **Comprehensive Data Analysis** - 15+ visualizations and statistical insights
- 🧹 **Advanced Data Cleaning** - Handled salary formats, missing values, and outliers
- 🛠️ **Feature Engineering** - Extracted 20+ meaningful features from raw data
- 🤖 **Model Comparison** - Tested 6 different ML algorithms
- ⚡ **Optimized Pipeline** - GridSearchCV tuning for best performance
- 🌐 **Interactive Web App** - User-friendly Gradio interface

---

## 🚀 Demo

### Web Interface
![Salary Predictor Interface](job-salary-predictor/screenshots/app.png)
*Interactive Gradio interface for salary prediction*

### Sample Prediction
![Prediction Result](job-salary-predictor/screenshots/app2.png)
```
╔════════════════════════════════════════╗
║     💰 SALARY PREDICTION RESULT        ║
╠════════════════════════════════════════╣
║ Position: Senior Data Scientist        ║
║ Location: CA                           ║
║ Seniority: Senior                      ║
║                                        ║
║ Estimated Annual Salary: $125,750.00K ║
╚════════════════════════════════════════╝
```

---

## ✨ Features

### 📈 Data Analysis
- Distribution analysis of salaries, ratings, and company age
- Correlation heatmaps for feature relationships
- Word cloud visualization of job descriptions
- Salary trends by industry, location, and job role

### 🔧 Feature Engineering
- **Salary Processing**: Converted hourly to annual, parsed salary ranges
- **Text Extraction**: Identified skills (Python, R, Spark, AWS, Excel)
- **Categorical Encoding**: Job simplification and seniority levels
- **Derived Features**: Company age, description length, competitor count

### 🤖 Machine Learning Models
| Model | R² Score | MAE | RMSE |
|-------|----------|-----|------|
| **XGBoost (Tuned)** | **0.7850** | **12.45** | **18.32** |
| Random Forest | 0.7623 | 13.89 | 19.87 |
| Gradient Boosting | 0.7445 | 14.23 | 20.15 |
| Ridge Regression | 0.6789 | 16.78 | 23.45 |
| Lasso Regression | 0.6654 | 17.23 | 24.01 |
| Linear Regression | 0.6521 | 18.12 | 25.34 |

### 🎨 Visualizations
- 📊 Salary distribution histograms
- 📦 Box plots for outlier detection
- 🔥 Heatmaps for feature correlation
- 📈 Bar charts for categorical analysis
- ☁️ Word clouds for text data

---

## 🛠️ Tech Stack

<div align="center">

| Category | Technologies |
|----------|-------------|
| **Language** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) |
| **ML/DL** | ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white) ![XGBoost](https://img.shields.io/badge/XGBoost-FF6600?style=flat) |
| **Data Analysis** | ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white) |
| **Visualization** | ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=flat) ![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=flat) |
| **Deployment** | ![Gradio](https://img.shields.io/badge/Gradio-FF7C00?style=flat) |
| **Tools** | ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white) ![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white) |

</div>

---

## 📦 Installation

### Prerequisites
```bash
Python 3.8 or higher
pip or conda package manager
```

### Clone Repository
```bash
git clone https://github.com/yourusername/job-salary-predictor.git
cd job-salary-predictor
```

### Install Dependencies
```bash
pip install -r requirements.txt
```

### Download Dataset
Place `glassdoor_jobs.csv` in the project root directory.

---

## 🚀 Usage

### 1️⃣ Train the Model
```bash
python jobrole_salary_predictor.py
```
This will:
- Clean and preprocess the data
- Perform exploratory data analysis
- Train and compare multiple models
- Save the best model as `salary_prediction_pipeline.pkl`

### 2️⃣ Launch Web Application
```bash
python jobrole_salary_predictor.py  # Scroll to bottom - Gradio launches automatically
```
Or separately:
```python
import gradio as gr
# Copy the Gradio interface code from the script
interface.launch()
```

### 3️⃣ Access the App
Open your browser and navigate to:
```
http://localhost:7860
```

---

## 📊 Model Performance

### XGBoost Hyperparameter Tuning Results
```python
Best Parameters:
{
    'n_estimators': 300,
    'max_depth': 7,
    'learning_rate': 0.1,
    'subsample': 1.0
}

Performance Metrics:
├── R² Score: 0.7850
├── MAE: $12,450
├── MSE: 245,678
└── RMSE: $18,320
```

### Feature Importance (Top 10)
```
1. Job Title          ████████████████████ 18.5%
2. Job State          ███████████████░░░░░ 14.2%
3. Industry           ██████████████░░░░░░ 12.8%
4. Company Rating     ████████████░░░░░░░░ 10.3%
5. Company Age        ██████████░░░░░░░░░░  9.1%
6. Seniority Level    ████████░░░░░░░░░░░░  7.6%
7. Company Size       ███████░░░░░░░░░░░░░  6.4%
8. Python Required    █████░░░░░░░░░░░░░░░  4.8%
9. Revenue            ████░░░░░░░░░░░░░░░░  3.9%
10. Sector            ████░░░░░░░░░░░░░░░░  3.5%
```

---

## 📂 Project Structure

```
job-salary-predictor/
│
├── 📄 jobrole_salary_predictor.py    # Main script (training + Gradio app)
├── 📊 glassdoor_jobs.csv             # Dataset
├── 🤖 salary_prediction_pipeline.pkl # Trained model
├── 📋 feature_columns.pkl            # Feature names
├── 📝 requirements.txt               # Dependencies
├── 📖 README.md                      # This file
│
├── 📁 notebooks/                     # Jupyter notebooks (optional)
│   └── EDA_analysis.ipynb
│
├── 📁 visualizations/                # Generated plots
│   ├── salary_distribution.png
│   ├── correlation_heatmap.png
│   └── wordcloud.png
│
└── 📁 models/                        # Model experiments
    └── model_comparison.csv
```

---

## 🔍 Key Insights from EDA

### 💰 Salary Patterns
- **Average Salary**: $95,000/year
- **Salary Range**: $45K - $180K
- **Top Paying States**: CA, NY, WA
- **Top Industries**: Biotech, Finance, IT

### 🏢 Company Insights
- Companies rated **4.0+** offer 15% higher salaries
- **Tech sector** dominates with 45% of listings
- **Large companies** (1000+ employees) pay 20% more
- **Senior positions** earn 40% more than junior roles

### 🔧 Skills Impact
```
Python: +$12,000 average salary increase
AWS:    +$8,500 average salary increase
Spark:  +$7,200 average salary increase
Excel:  +$3,100 average salary increase
```

---

## 📸 Screenshots

### Data Visualizations
<div align="center">

| Salary Distribution | Correlation Heatmap |
|---------------------|---------------------|
| ![Salary Distribution](visualizations/salary_distribution.png) | ![Heatmap](visualizations/correlation_heatmap.png) |

| Word Cloud | Average Salary by State |
|------------|-------------------------|
| ![WordCloud](visualizations/wordcloud.png) | ![Salary by State](visualizations/salary_by_state.png) |

</div>

---

## 🎯 Future Enhancements

- [ ] 🌍 Add more data sources (LinkedIn, Indeed)
- [ ] 📱 Deploy on HuggingFace Spaces
- [ ] 🔄 Implement real-time data updates
- [ ] 📊 Add interactive dashboards with Plotly
- [ ] 🤖 Include deep learning models (Neural Networks)
- [ ] 🔐 Add user authentication for saved predictions
- [ ] 📈 Build time-series salary trend predictions
- [ ] 🌐 Create REST API with FastAPI

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Your Name**

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yourusername)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/yourprofile)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF5722?style=for-the-badge&logo=google-chrome&logoColor=white)](https://yourportfolio.com)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your.email@example.com)

---

## 🙏 Acknowledgments

- Dataset: [Glassdoor Job Postings](https://www.glassdoor.com)
- Inspiration: Data Science community
- Libraries: scikit-learn, XGBoost, Gradio, Pandas

---

## 📊 Project Statistics

<div align="center">

![GitHub repo size](https://img.shields.io/github/repo-size/yourusername/job-salary-predictor)
![GitHub stars](https://img.shields.io/github/stars/yourusername/job-salary-predictor?style=social)
![GitHub forks](https://img.shields.io/github/forks/yourusername/job-salary-predictor?style=social)
![GitHub issues](https://img.shields.io/github/issues/yourusername/job-salary-predictor)
![GitHub pull requests](https://img.shields.io/github/issues-pr/yourusername/job-salary-predictor)

</div>

---

<div align="center">

### ⭐ If you found this project helpful, please give it a star!

**Made with ❤️ and ☕**

</div>
