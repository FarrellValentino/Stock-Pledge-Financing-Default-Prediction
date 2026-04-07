0e06-4fe8-afd1-dddf548f20a4" /># Stock-Pledge-Financing-Default-Prediction
 # 🏦 Stock Pledge Financing Default Prediction: Tree-Models vs Deep Learning

 ## 📌 Business Context
In the banking and financial sector, predicting corporate client defaults on stock-pledged loans is critical for mitigating Non-Performing Loans (NPL) and maintaining institutional liquidity. 

This project tackles a highly imbalanced financial dataset to predict loan defaults. Rather than relying on a single black-box algorithm, this project presents a rigorous comparative analysis between traditional state-of-the-art tree-based models and modern Deep Learning architectures tailored for tabular data.

## 🚀 Key Highlights & Engineering Rigor
- Algorithm Showdown: Benchmarked LightGBM, XGBoost, and TabNet (Attention-based Deep Learning for Tabular Data) to find the optimal balance between speed, scalability, and predictive power.
- Enterprise-Grade Reproducibility: Implemented a global seed_everything architecture across PyTorch, NumPy, and Python environments to ensure 100% deterministic and reproducible deep learning results.
- Business-Centric Evaluation: Transitioned from standard AUC metrics to log loss optimization, prioritizing the *confidence* of probability predictions—a crucial factor for banking risk-scoring systems.
- Robust Preprocessing: Handled extreme financial outliers via median imputation and utilized standardization specifically optimized for Neural Network convergence.

## 🧰 Tech Stack
- Data Manipulation: pandas, numpy
- Machine Learning: scikit-learn, LightGBM, XGBoost
- Deep Learning: PyTorch, pytorch-tabnet
- Visualization: matplotlib, seaborn

 📊 Model Performance & Evaluation

While all models achieved exceptional AUC scores in local validation, the final selection was strictly based on **Log Loss** to ensure the model outputs reliable probability scores for risk threshold tuning.

| Rank | Model | ROC-AUC Score | Log Loss | Conclusion |
| 🥇 | LightGBM | 1.0000 |  0.0034] | Best fit, highly efficient in handling noisy financial ratios with extreme leaf-wise gradient boosting. |
| 🥈 | XGBoost | 1.0000 | 0.0235 | Excellent, but slightly more conservative in probability confidence compared to LightGBM. |
| 🥉 | TabNet | 0.8923 | 0.3132  | Showed promise but required significantly larger datasets and extensive hyperparameter tuning to avoid overfitting. |

### Visual Insights

- **Confusion Matrices:** Demonstrates the models' precision in capturing True Positives (Actual Defaults) vs avoiding False Positives.
<img width="476" height="321" alt="image" src="https://github.com/user-attachments/assets/ce562dc8-8bd4-439e-81d1-dec0071bc907" />

<img width="470" height="323" alt="image" src="https://github.com/user-attachments/assets/1a3e2d71-3b61-4256-9fd9-dd3dd12e204d" />

<img width="465" height="321" alt="image" src="https://github.com/user-attachments/assets/89b721e9-77b7-46af-ba28-f3423cb6eb0c" />


- Learning Curves: Validation vs. Training Loss curves proving that the final models converged healthily without severe overfitting.

  <img width="500" height="322" alt="image" src="https://github.com/user-attachments/assets/c30ab0d6-3a10-4d19-a275-a44b17a5109c" />

  <img width="510" height="325" alt="image" src="https://github.com/user-attachments/assets/9e21ef75-2f2b-48f7-8818-070b1370c8be" />

  <img width="503" height="322" alt="image" src="https://github.com/user-attachments/assets/c32aab19-606f-49b8-9fa9-7acf357b0df5" />


💻 How to Reproduce
To run this pipeline locally and reproduce the exact results:

1. Clone this repository:
   ```bash
   git clone [https://github.com/](https://github.com/)[FarrellValentino]/[Stock Pledge Financing Default Prediction].git

2. Install the required dependecies:
     ```bash
     pip install -r requirements.txt
   
3. Run the notebook 
   
