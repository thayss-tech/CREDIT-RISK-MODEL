<div align="center">

<br />
  <h1>💰 Credit Risk Predictor: End-to-End ML Pipeline</h1>
  <p><strong>Predictive Modeling & Real-Time Decision Interface</strong></p>

<p>
  <a href="https://credit-risk-model-brdvrp5bbgmdfjtxnyzgcs.streamlit.app/" target="_blank">
    <img src="https://img.shields.io/badge/Streamlit-Live_App-ff4b4b?style=for-the-badge&logo=streamlit&logoColor=white" />
  </a>

  <a href="https://github.com/thayss-tech" target="_blank">
    <img src="https://img.shields.io/badge/Machine_Learning-Production_Ready-informational?style=for-the-badge&logo=python&logoColor=white" />
  </a>
</p>

<p>
  <a href="https://pandas.pydata.org/" target="_blank">
    <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" />
  </a>

  <a href="https://scikit-learn.org/" target="_blank">
    <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white" />
  </a>

  <a href="https://xgboost.readthedocs.io/" target="_blank">
    <img src="https://img.shields.io/badge/XGBoost-000000?style=flat-square&logo=xgboost&logoColor=white" />
  </a>

  <a href="https://streamlit.io/" target="_blank">
    <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" />
  </a>
</p>

</div>

---

## 📑 Table of Contents

| Section | Description |
| :--- | :--- |
| [**💡 Overview**](#overview) | Project mission and business context. |
| [**🏗️ Architecture**](#architecture) | Technical flow from Data to Live Prediction. |
| [**🧪 Modeling Strategy**](#modeling-strategy) | Algorithm tournament and optimization logic. |
| [**⚙️ Technical Engine**](#technical-engine) | Breakdown of the production-ready assets. |
| [**🗺️ Repository Map**](#repository-map) | Directory tree visualization. |
| [**🚀 Deployment**](#deployment) | Live access information. |
| [**📩 Contact**](#contact) | Professional links. |

---

## <a id="overview"></a>💡 Overview

Assessing credit risk is a cornerstone of retail banking. This project implements a supervised machine learning solution to predict whether a borrower represents a **'Good'** or **'Bad'** credit risk using the German Credit Dataset.

### Objective
The core development objective is to provide a **conservative risk evaluation tool** that prioritizes data certainty (Complete-Case Analysis) to minimize potential bank defaults while maintaining a streamlined approval process.

> *“From human interpretation to machine readability: translating financial profiles into actionable probability scores.”*

---

## <a id="architecture"></a>🏗️ Architectural Model

The system is designed as a modular pipeline that connects exploratory data science with a production-grade interface.

### Operational Flow

```mermaid
graph TD
    A[📊 German Credit Data] --> B[📓 Jupyter Notebook: EDA & Training]
    B -- Feature Engineering --> C[📦 Saved Encoders .pkl]
    B -- Model Selection --> D[🧠 Extra Trees Model .pkl]
    C & D --> E[🌐 Streamlit Web App]
    E -- User Input --> F{🔮 Prediction Engine}
    F -- Result --> G[✅/❌ Risk Decision Output]
````

#### Engineering Principles

  * **⚡ Efficiency:** Minimalist feature set (8 key predictors) for fast real-time inference.
  * **🛡️ Robustness:** Strict handling of categorical variables through persistent LabelEncoders.
  * **📊 Transparency:** Probability-based outputs (`predict_proba`) instead of simple binary classification.

-----

## \<a id="modeling-strategy"\>\</a\>🧪 Modeling Strategy

The analysis followed a rigorous "Algorithm Tournament" to identify the most stable classifier:

1.  **Data Quality:** Applied Complete-Case Analysis to ensure the model learns only from fully verified financial profiles.
2.  **Imbalance Management:** Implemented `scale_pos_weight` and `class_weight='balanced'` to handle the natural scarcity of 'Bad Risk' cases in banking data.
3.  **Algorithm Tournament:**
      * **Decision Trees (Baseline):** 58.1% Accuracy.
      * **Random Forest:** 61.9% Accuracy.
      * **Extra Trees (Winner):** 64.8% Accuracy - Selected for superior generalization.
      * **XGBoost:** 67.6% Accuracy - High performance via sequential error-correction.
4.  **Hyperparameter Tuning:** Executed **GridSearchCV with 5-Fold Cross-Validation** to optimize depth, estimators, and split criteria.

-----

## \<a id="technical-engine"\>\</a\>⚙️ Technical Engine: `Production Assets`

The system relies on serialized components to ensure consistency between the training environment and the live app:

| Subsystem | Icon | Component | Purpose |
| :--- | :---: | :--- | :--- |
| **Model Core** | 🧠 | `extra_trees_credit_model.pkl` | The trained decision engine. |
| **Data Translation** | 🔠 | `*_encoder.pkl` | Persistent LabelEncoders for Sex, Housing, etc. |
| **Interface Layer** | 💻 | `app.py` | Streamlit logic and custom CSS UI. |
| **Dependency Map** | 📋 | `requirements.txt` | Environment specification for cloud deployment. |

-----

## \<a id="repository-map"\>\</a\>🗺️ Repository Map

```text
CREDIT RISK MODEL FINAL/
 ┃
 ┣ 📄 analysis_model.ipynb     # Research, EDA & Training Pipeline
 ┣ 📄 app.py                   # Streamlit Web Application
 ┣ 📦 extra_trees_credit_model.pkl # Optimized Winning Model
 ┃
 ┣ 📄 Sex_encoder.pkl          # Persistent Categorical Encoders
 ┣ 📄 Housing_encoder.pkl
 ┣ 📄 Saving accounts_encoder.pkl
 ┣ 📄 Checking account_encoder.pkl
 ┃
 ┣ 📊 german_credit_data.csv   # Source Dataset
 ┣ 📋 requirements.txt         # Server-side Dependencies
 ┗ 📄 README.md                # Documentation
```

-----

## \<a id="deployment"\>\</a\>🚀 Deployment

The predictive engine is deployed via **Streamlit Community Cloud**, utilizing:

  * **Encrypted HTTPS communication.**
  * **Automated resource caching (`@st.cache_resource`)** for instant model loading.
  * **Continuous Deployment** directly from the GitHub repository.

| Type | Link |
| :--- | :--- |
| **🌐 Live App** | [https://credit-risk-model-brdvrp5bbgmdfjtxnyzgcs.streamlit.app/](https://credit-risk-model-brdvrp5bbgmdfjtxnyzgcs.streamlit.app/) |

-----

## \<a id="contact"\>\</a\>📩 Contact

\<div align="center"\>

| Platform | Profile | Action |
| :--- | :--- | :--- |
| **LinkedIn** | Milton Mamani | [View Profile](https://www.linkedin.com/in/milton-mamani-1369a537b) |
| **GitHub** | thayss-tech | [Explore Repos](https://github.com/thayss-tech) |

\<br /\>

> *Engineered with precision as a structured technical gateway for risk-sensitive environments.*

\</div\>
