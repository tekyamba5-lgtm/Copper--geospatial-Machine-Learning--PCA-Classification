Geospatial Machine Learning for Copper Exploration

Project Overview

This project applies Machine Learning and geospatial data analysis to identify patterns associated with copper presence in a mining environment.

The project combines three complementary techniques:

- Random Forest → predicts the presence or absence of copper.
- K-Means Clustering → groups mining points according to similarities in their characteristics.
- PCA (Principal Component Analysis) → reduces the dimensionality of the data and visualizes the clusters.

The objective is to demonstrate how AI and geospatial data can support mineral exploration and mining decision-making.

Objective

The main objective is to build a Machine Learning workflow capable of:

1. Analyzing geospatial and geological-related variables.
2. Predicting copper presence at mining points.
3. Identifying groups of similar points using unsupervised learning.
4. Visualizing spatial patterns.
5. Combining prediction and clustering to better understand the dataset.

Dataset

The dataset contains 500 mining points.

The model uses the following features:

Feature| Description
"latitude"| Geographic latitude
"longitude"| Geographic longitude
"elevation"| Elevation of the point
"magnetic_anomaly"| Magnetic anomaly measurement
"distance_fault"| Distance to a geological fault
"copper_indicator"| Indicator associated with copper
"mineral_presence"| Target variable indicating mineral presence

The dataset is loaded from:

mineral_data.csv

Machine Learning Approach

1. Random Forest

A Random Forest Classifier is trained to predict:

0 → Absence of copper
1 → Presence of copper

The model uses:

- 300 decision trees
- "random_state = 42"
- Balanced class weights
- 80% training data
- 20% testing data

The model also calculates a probability of copper presence for every point.

This makes it possible to move beyond a simple classification and estimate how strongly the model associates a point with copper presence.

2. K-Means Clustering

The project also applies K-Means clustering with:

3 clusters

Before clustering, the features are standardized using "StandardScaler".

K-Means groups points according to similarities across the input variables.

Important clarification

Cluster 1, Cluster 2 and Cluster 3 do not directly mean low, medium and high copper concentration.

They are simply groups of points that share similar characteristics according to the variables provided to the algorithm.

The relationship between each cluster and copper presence is then examined separately.

3. PCA Visualization

Principal Component Analysis (PCA) is used to transform the standardized dataset into two principal components:

PCA 1
PCA 2

These two components allow the three-dimensional-or-higher feature space to be represented visually in two dimensions.

The PCA visualization helps identify whether the clusters form visible groups or overlap.

The percentage of explained variance is also calculated by the program.

Geospatial Analysis

The project produces several spatial visualizations using:

Latitude
Longitude

These visualizations make it possible to observe where predicted copper-presence points and different K-Means clusters are located geographically.

Visualizations

The project generates the following static visualizations:

1. K-Means + PCA

kmeans_pca_clusters.png

Shows the three K-Means clusters in the PCA-reduced feature space.

2. K-Means Geospatial Map

kmeans_clusters.png

Shows the geographical distribution of the three clusters.

3. Random Forest Classification

random_forest_classification.png

Shows the predicted:

- Absence of copper
- Presence of copper

4. Combined K-Means + Random Forest

kmeans_random_forest_combined.png

Combines clustering and copper prediction in the same geographical visualization.

Animated GIF Visualization

The project also generates an animated visualization of the progressive analysis of the mining points.

random_forest_500_points.gif

The animation progressively displays the 500 points and their Random Forest predictions.

The GIF helps illustrate how the classification appears as more points are analyzed.

Model Evaluation

The Random Forest model is evaluated using:

accuracy_score()
classification_report()

The program reports:

- Accuracy
- Precision
- Recall
- F1-score

The final accuracy is printed automatically when the program runs.

Feature Importance

Random Forest provides an estimate of the importance of each input variable.

The project calculates:

model.feature_importances_

The results are sorted from the most important variable to the least important variable.

This helps identify which features contribute most to the model's predictions.

Output Data

The project exports the complete dataset with the Machine Learning results to:

random_forest_kmeans_500_points.csv

The exported file contains the original information together with:

prediction
probability
cluster
PCA1
PCA2

This allows further analysis in Python, Excel, Power BI or other data-analysis tools.

Installation

1. Install Python

Make sure Python 3.9 or later is installed.

Check your Python version:

python --version

or:

python3 --version

2. Clone the repository

Clone the GitHub repository:

git clone https://github.com/tekyamba5-lgtm/machine---learning---geospatial---mineraux.git

Move into the project directory:

cd machine---learning---geospatial---mineraux

3. Install the required libraries

Install the dependencies with:

pip install pandas numpy matplotlib scikit-learn pillow

If your system uses "pip3":

pip3 install pandas numpy matplotlib scikit-learn pillow

Required libraries

- "pandas" → data manipulation
- "numpy" → numerical calculations
- "matplotlib" → visualizations
- "scikit-learn" → Random Forest, K-Means, PCA and evaluation
- "Pillow" → GIF generation

Running the Project

1. Prepare the dataset

Place the dataset file:

mineral_data.csv

in the location expected by the Python script.

The current script uses:

/storage/emulated/0/Documents/mineral_data.csv

This path is suitable for an Android environment such as Pydroid 3.

If you are running the project on Windows, Linux or macOS, modify the dataset path in the Python script to match the location of your CSV file.

2. Run the Python script

For example:

python main.py

or:

python3 main.py

The script will automatically:

1. Load the 500 mining points.
2. Clean missing and infinite values.
3. Train the Random Forest model.
4. Evaluate model accuracy.
5. Predict copper presence.
6. Calculate prediction probabilities.
7. Apply K-Means clustering.
8. Apply PCA.
9. Generate geospatial visualizations.
10. Generate the Random Forest GIF.
11. Calculate feature importance.
12. Export the results to CSV.

Technologies Used

The project was developed using Python and the following libraries:

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Pillow

Main algorithms

Random Forest
K-Means
PCA
StandardScaler

Project Workflow

Mining Dataset
      ↓
Data Cleaning
      ↓
Feature Selection
      ↓
Random Forest
      ↓
Copper Prediction
      ↓
Feature Importance
      ↓
Standardization
      ↓
K-Means Clustering
      ↓
PCA
      ↓
Geospatial Visualization
      ↓
Combined Analysis
      ↓
Animated Visualization
      ↓
CSV Export

Why This Project Matters

Copper exploration generates large amounts of geological, geospatial and environmental data.

Machine Learning can help transform these datasets into useful information for exploration teams.

Instead of examining every point manually, a Machine Learning workflow can help:

- identify patterns,
- classify locations,
- detect groups of similar areas,
- estimate copper presence,
- visualize spatial relationships,
- and support data-driven exploration decisions.

This project demonstrates a practical example of how AI + geospatial data + mining knowledge can be combined.

Future Improvements

Possible future developments include:

- Integration of satellite imagery.
- Interactive GIS maps.
- Remote sensing data.
- Comparison with XGBoost and other ML algorithms.
- Spatial cross-validation.
- Interactive dashboards.
- Integration of additional geological variables.
- Deep Learning for geological pattern recognition.
- Deployment on Google Cloud.
- Development of a copper prospectivity prediction map.

Author

Ekyamba Trésor Ababel

Maintenance & Reliability Engineer | Machine Learning | Geospatial Data | Mining Technology

Interested in the application of Artificial Intelligence, Machine Learning and geospatial data to mining and mineral exploration.

Project Goal

«Using Machine Learning to transform mining data into actionable insights for copper exploration.»

If you find this project interesting, feel free to explore the code, results and visualizations in this repository.
