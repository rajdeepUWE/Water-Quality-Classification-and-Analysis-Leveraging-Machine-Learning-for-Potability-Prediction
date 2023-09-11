# Water-Quality-Classification-and-Analysis-Leveraging-Machine-Learning-for-Potability-Prediction


View the complete code in the .ipynb file. Load the .csv file and run the code.

Data Loading and Exploration:
I began by loading the water quality dataset into a Pandas DataFrame and took a closer look at the data to understand its characteristics. This dataset contains various features related to water quality, and our main goal is to predict whether the water is potable or not based on these features.

Data Visualization and Analysis:
To gain insights into the dataset, I used visualizations and analysis techniques. Firstly, I created a pie chart to visualize the distribution of potable and non-potable water samples. This chart showed that we have a somewhat balanced dataset, with a similar number of potable and non-potable samples.

Next, I generated a correlation matrix to explore the relationships between different features. This helped me identify potential correlations between these features and the target variable, which could be useful for modeling.

To get a more visual representation of the correlations, I created a clustered heatmap. This heatmap provided valuable insights into which features are strongly correlated or negatively correlated with each other, aiding in feature selection.

Additionally, I used KDE (Kernel Density Estimation) plots to visualize the distribution of various features for both potable and non-potable water samples. These plots revealed how each feature's distribution varies between the two classes.

Data Preprocessing:
Before diving into modeling, I checked for missing values using the missingno library and visualized the missing value matrix. This step was crucial to identify any gaps in our data. We found that "ph," "Sulfate," and "Trihalomethanes" had missing values. To address this, I decided to fill those missing values with the mean of their respective features, ensuring that our dataset was complete.

Train-Test Split:
To assess the performance of our models accurately, I split the dataset into training and testing sets. I allocated 70% of the data for training and kept 30% for testing. This allowed me to evaluate how well our models generalize to unseen data.

Data Modeling:
I selected two classification models: the Decision Tree Classifier and the Random Forest Classifier. After training both models on the training data, I made predictions on the test data. To measure their performance, I calculated precision scores for each model. Precision is a crucial metric because it tells us how well the model is at correctly classifying potable water samples.

I also created confusion matrices for each model, which provided a visual representation of their predictions, including true positives, true negatives, false positives, and false negatives.

Decision Tree Visualization:
To gain a deeper understanding of the Decision Tree Classifier, I visualized the decision tree itself. This allowed me to see how the model makes decisions based on the input features, providing insights into its decision-making process.

Random Forest Classifier and Hyperparameter Tuning:
I then moved on to the Random Forest Classifier, which is an ensemble method. I conducted hyperparameter tuning using Randomized Search CV. This process involved testing different combinations of hyperparameters to find the best configuration for our model. The best parameters, including the number of estimators, max features, and max depth, were displayed alongside the best score achieved during tuning.

Re-Modelling:
Using the best hyperparameters identified during hyperparameter tuning, I created a new Random Forest Classifier. This new model was trained on the training data, and I calculated its precision score on the test data. This step allowed us to assess how well the tuned model performed compared to the initial Random Forest Classifier.

Bonus Decision Trees Visualization:
As a bonus, I extracted individual decision trees from the Random Forest Classifier and calculated precision scores for each tree. This exercise helped us understand the diversity of decision trees within the ensemble. I then visualized the top two decision trees with the highest precision scores, offering insights into their structure and decision logic.

Comparing Scores:
In terms of model performance, the precision scores were as follows:

Decision Tree Classifier: Precision = 0.5652
Random Forest Classifier (before tuning): Precision = 0.6313
Random Forest Classifier (Tuned): Precision = 0.6211
Concluding Findings:
Comparing the models, the Random Forest Classifier outperformed the Decision Tree Classifier in terms of precision, indicating its better ability to correctly classify potable water samples.

Hyperparameter tuning slightly improved the Random Forest Classifier's performance, but the difference in precision was not substantial. This suggests that the initial model was already performing quite well.

Overall, our models showed promise in classifying water samples as potable or non-potable. However, further evaluation using additional metrics such as recall, F1-score, and accuracy is needed to provide a comprehensive assessment of model performance.

In conclusion, our project provides a solid foundation for water quality classification. Further optimization and evaluation are recommended for practical applications, including potential feature engineering and more complex modeling approaches.
