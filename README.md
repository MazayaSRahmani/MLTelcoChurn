# MLTelcoChurn

# Telco Customer Churn Prediction

## **Problem Statement**

Customer churn, or customer attrition, is a critical metric for businesses, especially in the telecommunications industry. It measures the percentage of customers who end their relationship with a company during a specific period.

### **What is Churn Rate?**

According to Jill Avery on [Harvard Business Review](https://hbr.org/2014/10/the-value-of-keeping-the-right-customers), customer churn rate is a metric that measures the percentage of customers who end their relationship with a company in a particular period.

### **How to Calculate Churn Rate?**

Calculating churn rate is straightforward. It is the total number of customers who left your company during a period divided by the total number of customers at the beginning of that period.

\[ \text{Churn Rate} = \frac{\text{Number of Customers Who Left}}{\text{Total Number of Customers at the Beginning}} \]

While this metric provides valuable insights, it is a lagging indicator, meaning it only reflects past events.

### **How Can a Machine Learning Model Help?**

Machine learning can proactively address the issue of customer churn by predicting which customers are likely to leave before they actually do. This allows companies to take preemptive actions to retain these customers, thereby reducing churn and associated costs.

The key advantage of using a machine learning model for churn prediction is its ability to transform churn from a lagging indicator into a leading one. Even with some prediction errors, the focus should be on minimizing the cost of churn by correctly identifying customers at risk of leaving. This proactive approach can help in retaining customers more affordably, providing a financial cushion and improving overall customer satisfaction and loyalty.

## **Dataset**

The dataset used for this project consists of various features related to customer demographics, account information, and service usage patterns. The features are as follows:

| Feature             | Data Type | Null | Negative | Unique | Sample Unique Values                              |
|---------------------|-----------|------|----------|--------|---------------------------------------------------|
| Dependents          | object    | 0.0  | False    | 2      | [Yes, No]                                         |
| tenure              | int64     | 0.0  | False    | 73     | [9, 14, 64, 72, 3, 40, 17, 11, 8, 47, 18, 5, 1...]|
| OnlineSecurity      | object    | 0.0  | False    | 3      | [No, Yes, No internet service]                    |
| OnlineBackup        | object    | 0.0  | False    | 3      | [No, Yes, No internet service]                    |
| InternetService     | object    | 0.0  | False    | 3      | [DSL, Fiber optic, No]                            |
| DeviceProtection    | object    | 0.0  | False    | 3      | [Yes, No internet service, No]                    |
| TechSupport         | object    | 0.0  | False    | 3      | [Yes, No, No internet service]                    |
| Contract            | object    | 0.0  | False    | 3      | [Month-to-month, Two year, One year]              |
| PaperlessBilling    | object    | 0.0  | False    | 2      | [Yes, No]                                         |
| MonthlyCharges      | float64   | 0.0  | False    | 1422   | [72.9, 82.65, 47.85, 69.65, 23.6, 74.55, 19.7,...]|
| Churn               | object    | 0.0  | False    | 2      | [Yes, No]                                         |


## **Modeling**

The modeling process involves:

1. **Feature Selection**: Selecting relevant features that contribute to predicting churn.
2. **Data Splitting**: Dividing the data into training and testing sets.
3. **Preprocessing Pipeline**: Creating a preprocessing pipeline to handle different types of data.
4. **Model Training**: Training a Decision Tree classifier, which was selected as the final model.
5. **Hyperparameter Tuning**: Optimizing model parameters using techniques like Grid Search and Cross-Validation.

## **Evaluation Metrics**

To evaluate the performance of the model, the F2 score is used. The F2 score is a weighted harmonic mean of precision and recall, giving more weight to recall. This is particularly useful in the context of churn prediction, where correctly identifying customers who are at risk of leaving is more critical.

\[ \text{F2 Score} = \left(1 + 2^2\right) \cdot \frac{\text{Precision} \cdot \text{Recall}}{\left(2^2 \cdot \text{Precision}\right) + \text{Recall}} \]

## **Model Deployment**

After training and validating the model, it is saved using `pickle` or `joblib` for later use. The model can then be deployed in a production environment to predict churn in real-time.

```

