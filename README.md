### Wind-Turbines
I built and tuned classification models using sensor data on wind turbine generators. The goal was to identify failures in advance, enabling repairs before breakdowns and reducing maintenance costs.


#### Skills & Tools Covered:
* Up and downsampling
* Regularization
* Hyperparameter tuning
  
#### Business Context

Renewable energy sources play an increasingly important role in the global energy mix, as the effort to reduce the environmental impact of energy production increases.

Out of all the renewable energy alternatives, wind energy is one of the most developed technologies worldwide. The U.S Department of Energy has put together a guide to achieving operational efficiency using predictive maintenance practices.

Predictive maintenance uses sensor information and analysis methods to measure and predict degradation and future component capability. The idea behind predictive maintenance is that failure patterns are predictable and if component failure can be predicted accurately and the component is replaced before it fails, the costs of operation and maintenance will be much lower.

The sensors fitted across different machines involved in the process of energy generation collect data related to various environmental factors (temperature, humidity, wind speed, etc.) and additional features related to various parts of the wind turbine (gearbox, tower, blades, break, etc.).



#### Objective
“ReneWind” is a company working on improving the machinery/processes involved in the production of wind energy using machine learning and has collected data of generator failure of wind turbines using sensors. They have shared a ciphered version of the data, as the data collected through sensors is confidential (the type of data collected varies with companies). Data has 40 predictors, 20000 observations in the training set and 5000 in the test set.

The objective is to build various classification models, tune them, and find the best one that will help identify failures so that the generators could be repaired before failing/breaking to reduce the overall maintenance cost.
The nature of predictions made by the classification model will translate as follows:

- True positives (TP) are failures correctly predicted by the model. These will result in repairing costs.
- False negatives (FN) are real failures where there is no detection by the model. These will result in replacement costs.
- False positives (FP) are detections where there is no failure. These will result in inspection costs.

It is given that the cost of repairing a generator is much less than the cost of replacing it, and the cost of inspection is less than the cost of repair.

“1” in the target variables should be considered as “failure” and “0” represents “No failure”.

#### Data Description
- The data provided is a transformed version of original data which was collected using sensors.
- Train.csv - To be used for training and tuning of models.
- Test.csv - To be used only for testing the performance of the final best model.
- Both the datasets consist of 40 predictor variables and 1 target variable

#### Installing the libraries with the specified version.
!pip install pandas==1.5.3 numpy==1.25.2 matplotlib==3.7.1 seaborn==0.13.1 scikit-learn==1.2.2 imbalanced-learn==0.10.1 xgboost==2.0.3 threadpoolctl==3.3.0 -q --user


#### Business Insights and Conclusions
* Implementing predictive maintenance can lower operational costs by preventing generator failures. By accurately predicting when maintenance is needed, "ReneWind" can use its resources more efficiently and reduce downtime.
* The Random Forest model, trained on undersampled data, achieved a strong recall score of 0.872. This means it effectively identifies true failures, which is crucial for timely repairs and cost savings.
* The analysis found V18, V36, and V39 to be the most significant predictors of failures. Focusing on these features in future data collection can improve accuracy and efficiency.
* The chosen model not only has high recall but also performs well across other metrics. This balance ensures accurate failure predictions while minimizing unnecessary inspections.
* The undersampling method proved successful in enhancing model performance, highlighting the importance of proper data techniques, especially with imbalanced datasets.

#### Recommendations
* Continuously update and retrain predictive maintenance models with new data to keep them effective as operational conditions may change.
* Invest in better sensors to capture more accurate data for key features (V18, V36, and V39) to improve model accuracy.
* Creating a dashboard that combines model predictions with daily operations, may allow maintenance teams to respond to predicted failures in timely manner.
* Provide training for staff on how to interpret model outputs and the importance of quick responses to predictions, which can improve the success of preventive maintenance.


