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

        - and by those numbers i can make all possiple models and choose the best K-neighbors with good cross validation score, which here K-neighbors = 23 

        - Model results:

                train score =  0.7945425361155698
                train score =  0.8246268656716418

        #### 3) R-Nearest Neighbors
        - The worst model among them, i will ignore it

        #### 4) Decision Tree Classifier
        - Decision Tree one of the best models, but it has a problem, which is overfitting problem

        - i usally use  post-pruning technique to avoid overfitting, all you need to compute cost complexity pruning path, then use cross validation score, to get mean score for each alpha and then choose alpha that prune the tree good without overfitting train data, in my case i choose 
        
                ccp_alpha=0.001713
        
        - check Decision Tree part in code to see how pruning effects on the size of tree

        #### 5) Random Forest Classifier
        - This model is based on a decision tree in the first place. It basically improves the output of the decision tree, so all you need is just to buil it and make the same thing you do in Decision Tree Classifier

    4. Votting System

        after creating all models and define the best parameters for each model, create a soft vot system to get better result