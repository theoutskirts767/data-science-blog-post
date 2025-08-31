# Titanic data analysis 
A data science project about the Titanic and who was on board the vessel.

The grand voyage of the RMS Titanic began from Southampton, England on April 10 1912. It was a floating palace bound for New York City. Everyone called it "unsinkable" and the lavish ship was a masterpiece of the Gilded Age, a testament to human innovation.  Aboard were some of the richest and most famous people in the world. John Jacob Astor IV, a millionaire magnate, was there with his much younger wife, Madeleine. Industrialist Benjamin Guggenheim, whose last moments were spent in his finest evening clothes, and Isidor Straus, the co-owner of Macy's, with his devoted wife Ida, who refused to leave his side. The ship’s short journey across the icy Atlantic was a series of grand balls and lavish meals, a world of privilege sailing on the surface of danger. But on the night of April 14, a massive iceberg appeared in the darkness. The unimaginable happened. The great ship struck the ice and sank in the frigid waters in just a few hours. Over 2,200 souls on board, the final death toll was more than 1,500.

# Data Science Blog Post on Titanic Dataset

## Motivation
This project aims to analyze the Titanic dataset to uncover insights about who the passengers were. The findings will be communicated through a blog post to make the results accessible to a broader audience.

## Libraries Used
- **pandas**: For data manipulation and analysis.
- **numpy**: For numerical operations.
- **scikit-learn**: For machine learning algorithms.
- **matplotlib**: For data visualization.
- **seaborn**: For enhanced visualizations.

## File Descriptions
- `your_dataset.csv`: The dataset used for analysis.
- `data_analysis.ipynb`: Jupyter Notebook containing the data analysis code.

## Summary of Results
The analysis revealed that more men died than women. The model achieved an accuracy of the data is about 70% accurate and provided valuable insights into the people aboard the ship.

# Import necessary libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error

# Load the dataset
data = pd.read_csv('data/your_dataset.csv')

# Explore the data
print(data.head())
print(data.info())
print(data.describe())

# Visualize the data
sns.scatterplot(data=data, x='feature1', y='target')
plt.title('Feature 1 vs Target')
plt.show()

# Clean the data (if necessary)
data.dropna(inplace=True)  # Example: drop missing values

# Split the data into features and target
X = data[['feature1', 'feature2']]  # Replace with your actual features
y = data['target']  # Replace with your actual target variable

# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train the model
model = LinearRegression()
model.fit(X_train, y_train)

# Make predictions
predictions = model.predict(X_test)

# Evaluate the model
mse = mean_squared_error(y_test, predictions)
print(f'Mean Squared Error: {mse}')

# Scenario Prediction
new_data = [[value1, value2]]  # Replace with new input values
prediction = model.predict(new_data)
print(f'Prediction for new data: {prediction}')


