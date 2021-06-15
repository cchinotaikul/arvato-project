# Customer Segmentation Report and Outcome Predictor for Arvato Financial Services
This repository contains files including the Jupyter Notebook which explored the demographics data of the general population of Germany and information on customers and mailing list of a German mail order company, provided by Arvato Financial Services, with the goal to generate segmentation reports and a prediction model for people who will respond to the company's mailing campaign.

![Header image](https://miro.medium.com/max/3836/1*V0jlPx_cdKvplBBFj3V7Ag.png)

A companion blog post for this analysis can be found at https://chinnaporn-chinotaikul.medium.com/finding-customers-among-population-data-with-machine-learning-a8aaeb047f42

Created as part of my project for the Udacity Data Science Nanodegree course

# Installation
The Jupyter Notebook was created using version 6.1.5 of the server and using Python version 3.8.5
Other libraries include:
- pandas (1.1.5)
- numpy (1.19.2)
- matplotlib (3.3.2)
- seaborn (0.11.0)
- scikit-learn (0.24.2)
- jupyterthemes (0.20.0)
- yellowbrick (1.3.post1)
- imbalanced-learn (0.8.0)

However, it should be noted that the project was created using data provided by Arvato, under the licence that the data cannot be shared to other 3rd parties, therefore the data cannot be uploaded here and unfortunately the Notebook cannot be re-run without the provided data.

# Project Motivation
Tools that allows a business to perform accurate customer segmentation are invaluable and allow the optimisation of marketing budgets and resources. Rather than sending out mass marketing campaigns, it allows businesses to focus on the highest potential, most profitable customers.

Furthermore, segmentation would allow the business to tailor its marketing strategies towards different segments of its potential customers in order to achieve the best responses.

# File Descriptions
Files in this repository include:
- Arvato Project Workbook.ipynb - the main Jupyter Notebook includes importing of the data, exploration, modelling, analysis and visualisation

# Project Summary
The key goals for the project are as follows:
<ol>
    <li>Identifying customer segments and how likely people from each segment of the population are to be customers of the company — this will use the population data and customers data</li>
    <li>Predict the outcomes of the mailing order campaign for the unknown outcome dataset by training a model using the known dataset — this will be evaluated using a Kaggle competition</li>
</ol>
For the first goal, I used K-means clustering to separate the population and customers data into 6 separate clusters. Before applying the K-means, data cleaning, data dimension reduction using PCA and a K-means elbow analysis to determine the appropriate amount of clusters to use was performed. The distributions of the cluster are as follows:

<br>

![Comparing Proportions between General Population and Customer Clusters](https://miro.medium.com/max/700/1*UZyk63kCiG--mm4rX017hQ.png)

It can be seen that 2 of the clusters showed significantly higher proportions of customers likely to be represented, 1 cluster where the proportions are similar, and 3 clusters where customers are under-represented.

For the second goal, I used a similar pipeline to the first problem, but adding in an oversampler due to the smaller amount of training data and the very low amount of positive outcomes. After trailing different model types and finding the best parameters using grid search, a logistic regressor is used to train the model and then applied to the testing data.

The predictions are submitted to be scored on a Kaggle competition created for this purpose (https://www.kaggle.com/c/udacity-arvato-identify-customers/overview), with a score of 0.63409 achieved by the model.


# Acknowledgement and Licensing
- Demographics data provided by https://finance.arvato.com/en/
- Libraries' documentations
- Udacity course materials
- All files in this repository are free to use
