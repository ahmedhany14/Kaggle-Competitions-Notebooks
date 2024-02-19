# Kaggle-Competitions-Notebooks
### This repo will contain notebooks for solving ML problems, and each problem will have a simple tutorial for it.

## 1) Titanic Problem

* [Competition Link](https://www.kaggle.com/competitions/titanic/overview)
* Toturial

    this problem is a classification problem, to solve it we will follow the following steps:
    1. EDA

        you will try to find a relations between columns and Survived column

        you need to define the columns you will drop, and the columns that need cleaning and transforming

    2. Data Cleaning

        you will fill the missing values, and apply OneHotEncode for the Categorical data.

    3. ML Models 
        i used those models to solve the problem:
        - Logistic Regression
        - k-Nearest Neighbors
        - R-Nearest Neighbors
        - Decision Tree Classifier
        - Random Forest Classifier

        #### 1) Logistic Regression
        - This is a basic model in which all you to train your data and calcaulte the score of the model.

        #### 2) k-Nearest Neighbors
        - in general i prefer to make K-neighbors = sqrt(n_samples), and then try K-neighbors less or greater than this number

            num_neighbors = int(np.sqrt(len(x_train)))

            neighbors = [num_neighbors]
            for i in range(9):
                neighbors.append(num_neighbors + i + 1)
            for i in range(9):
                neighbors.append(num_neighbors - (i + 1))
        - and by those numbers i can make all possiple models and choose the best K-neighbors with good cross validation score.

        ![Cross Validation](KNvalidation.png)

