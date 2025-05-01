# A Data-Driven Approach to Mobile App Rating Prediction

## Project Overview

This project explores how metadata and version-specific features from the App Store can be used to predict app ratings. We evaluated six machine learning algorithms — including Random Forest, SVM, Neural Networks, and more — on a dataset of over 7,000 apps.

- **Best Model:** Random Forest  
- **Lowest RMSE:** 0.465  
- **Key Predictors:** Version-specific user ratings and update frequency

## Dataset

- **Source:** [Kaggle - Mobile App Store Dataset](https://www.kaggle.com/datasets/ramamet4/app-store-apple-data-set-10k-apps/data)
- **Size:** 7,197 iOS apps (2017 snapshot)
- **Features:** App metadata (size, price, category), version-specific metrics, and engineered features like `rating_ratio` and `major_ver`.

## Preprocessing Steps

- Removed irrelevant columns and anomalies
- Engineered features (`is_free`, `rating_ratio`, `major_ver`)
- Handled skewed data with Box-Cox transformations
- Encoded categorical variables using label encoding and one-hot encoding

## Models Used

| Model | Reason |
|-------|-------|
| **Linear Regression, Ridge, Lasso** | Baseline model |
| **PCA + Ridge** | Dimensionality reduction |
| **Decision Tree, Random Forest** | Nonlinear tree-based model |
| **KNN Regression + Classification** | Instance-based learning |
| **Support Vector Regression (SVR)** | RBF kernel optimized for nonlinearity |
| **Neural Network (MLP)** | Single hidden layer with ReLU |

## Performance Highlights

| Model            | RMSE   | R²     |
|------------------|--------|--------|
| Random Forest    | 0.465  | 0.556  |
| SVM (RBF)        | 0.493  | 0.502  |
| Neural Network   | 0.514  | 0.459  |
| KNN Regression   | 0.432 (MAE) | 0.262  |
| Linear Models    | 0.611  | 0.236  |

Random Forest was the top performer in both accuracy and interpretability.

## Key Insights

- Version-specific ratings (`user_rating_ver`) and version-to-total ratios were the most influential features.
- Linear models lacked the power to capture complex feature interactions.
- Tree-based methods provided a useful balance between accuracy and explainability.
- KNN worked well for mid-range ratings but struggled with edge cases due to class imbalance.
- SVM offered strong performance with relatively fast training times.

## Future Directions

- Incorporate temporal dynamics and review text analysis
- Explore hybrid models (e.g., interpretable neural nets or boosted ensembles)
- Evaluate generalizability on newer datasets

## Authors

- Gia Kim — sk185@rice.edu  
- Shieun Lee — sl203@rice.edu  
- Wiley Liou — wl76@rice.edu  

Project completed for **Spring 2025 DSCI 303: Machine Learning for Data Science** at **Rice University**.
