# Horizon-Airlines-project



Horizon Airlines aims to launch a budget-conscious passenger loyalty program targeting brand ambassadors. This pipeline prioritizes High Precision Target: ≥ 90% 

to eliminate costly "False Positives" (inviting unsatisfied passengers).



Key EDA Findings

Target Profile: Returning business travelers in Business Class cabins hold the highest baseline satisfaction.

Core Drivers: High survey ratings in \*\*Online Boarding, In-flight Entertainment, and Seat Comfort\*\* serve as strong, reliable indicators of total satisfaction.



Preprocessing Workflow

1\. Data Leakage Prevention: Split the data into stratified training (80%) and testing (20%) sets before applying any data transformations.

2\. Missing Value Imputation: Handled missing elements in the `Arrival Delay` feature by calculating and applying the median value of the training split.

3\. Feature Scaling: Applied `StandardScaler` to handle continuous travel metrics and prevent distance distortion during modeling.



\## 🤖 Modeling \& Optimization Strategy

Because precision was selected as our primary evaluation metric to respect strict budget limitations, standard default thresholds (`0.5`) were modified:

Baseline Performance:Baseline K-Nearest Neighbors (KNN) Precision: 73.85%

Baseline Logistic Regression Precision: 87.29%

Hyperparameter Tuning \& Threshold Shifting: Using `GridSearchCV` paired with decision threshold tuning, classification cut-offs were raised. This forced the final model to only classify a passenger as "satisfied" when it possessed maximum prediction confidence.

Final Selected Model: An optimized K-Nearest Neighbors (KNN) model was selected as it successfully surpassed the corporate requirement of ≥ 90% precision.

