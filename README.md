# KNN-Matched Green Bond Pricing Analysis

## Overview
This project explores whether **green bonds** exhibit a **pricing premium** (greenium) compared to **common bonds** in the primary market. Using financial and bond characteristics data, I conduct a systematic analysis to determine if there is a statistically significant difference in bond yields at issuance.

## Key Challenges & Considerations
- **Unbalanced Dataset:** The dataset contains significantly more common bonds than green bonds, making direct comparison problematic. This imbalance necessitates **matching techniques** to ensure a fair comparison.
- **Limitations of Linear Models:** Initial analysis showed that key bond characteristics, such as yield, duration, and coupon rate, did not exhibit strong **linear relationships**. This suggests that simple **Ordinary Least Squares (OLS) regression** may not be a suitable approach for this study.
- **Matching-Based Approach:** Given these challenges, I employ **Propensity Score Matching (PSM) with K-Nearest Neighbors (KNN)** to construct a comparable dataset of green and common bonds.

## Key Findings
- **Exploratory Data Analysis (EDA):**  
  - Green and common bonds differ in issuance amount and sector distribution.
  - Yield distributions for green and common bonds appear similar, suggesting no obvious pricing premium.
  - No strong linear correlations were found between yield and other bond characteristics.
- **After Matching with KNN:**  
  - Green bonds and common bonds were successfully matched on key financial characteristics.
  - Statistical tests show **no significant difference in yield at issuance** between green and common bonds.
  - This suggests that, in the primary market, green bonds do not systematically trade at a higher or lower yield than comparable common bonds.

## Methodology
1. **Data Preprocessing & EDA:**  
   - Investigate the distribution of key bond characteristics.  
   - Identify potential biases in the dataset.  
   
2. **Matching Green and Common Bonds:**  
   - Apply **Propensity Score Matching (PSM)** using **K-Nearest Neighbors (KNN)** to address dataset imbalance.  
   - Ensure that matches occur **within the same currency** to avoid cross-currency distortions.  

3. **Statistical Testing:**  
   - Conduct **T-tests** to compare mean bond yields before and after matching.  
   - Analyze **distributional differences** using density plots.  

## Conclusion
The results indicate that **green bonds do not show a statistically significant pricing premium compared to common bonds at issuance**. The findings suggest that, in the primary market, investors do not consistently pay more (or receive less yield) for green bonds relative to similar conventional bonds.

## Files in This Repository
- `Greenbond_Premium_KNN.ipynb`: Jupyter Notebook containing the full analysis, including data preprocessing, matching, and statistical testing.
- `matched_bond_dataset_n1.csv`: The dataset after applying PSM, containing matched green and common bonds.

## Requirements
To run this project, install the following Python libraries:
```bash
pip install pandas numpy seaborn matplotlib scikit-learn
