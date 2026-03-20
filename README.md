# Description
## Introduction
The goal of the data challenge is to learn how to implement machine learning algorithms, gain understanding about them and adapt them to structural data. For this reason, we have chosen a simple image classification task. There are specific rules that are described below.

What is expected
Two days after the deadline of the data challenge, you will have to provide

a small report on what you did (in pdf format, 11pt, 2 pages A4 max, with your team name and member names written under the title). You will need to upload it on gradescope.
your source code (zip archive), with a simple script "start" (that may be called from Matlab, Python, R, or Julia) which will reproduce your submission and saves it in Yte.csv
Rules
You need to implement kernel methods for this challenge.
You can form teams of at most 2 persons.
You can submit results up to twice per day during the challenge.
A leader board will be available during the challenge, which shows the best results per team, as measured on a subset of the test set. A different part of the test set will be used after the challenge to evaluate the results.
The most important rule is: DO IT YOURSELF. The goal of the data challenge is not get the best recognition rate on this data set at all costs, but instead to learn how to implement things in practice, and gain practical experience with the machine learning techniques involved.
For this reason, the use of external machine learning libraries is forbidden. For instance, this includes, but is not limited to, libsvm, liblinear, scikit-learn, …

On the other hand, you are welcome to use general purpose libraries, such as library for linear algebra (e.g., svd, eigenvalue decompositions), optimization libraries (e.g., for solving linear or quadratic programs).

Evaluation
The evaluation pages describes how submissions will be scored and how students should format their submissions. The metric is the classification accuracy. The data contains 10 classes. ##Submission Format Submission files should contain two columns: Id and Prediction. The file should contain a header and have the format described below. Id represents the number of the test example, ranging from 1 to 2000. The prediction is the corresponding label, from 0 to 9. Ex: ``` Id,Prediction 1,4 2,8 3,8 4,1 5,9 6,0 7,8 ``` Below, you will also find a piece of code for reading/writing the data. ```python import numpy as np import pandas as pd Xtr = np.array(pd.read_csv('Xtr.csv',header=None,sep=',',usecols=range(3072))) Xte = np.array(pd.read_csv('Xte.csv',header=None,sep=',',usecols=range(3072))) Ytr = np.array(pd.read_csv('Ytr.csv',sep=',',usecols=[1])).squeeze() # define your learning algorithm here # for instance, define an object called ``classifier'' # classifier.train(Ytr,Xtr) # predict on the test data # for instance, Yte = classifier.fit(Xte) Yte = {'Prediction' : Yte} dataframe = pd.DataFrame(Yte) dataframe.index += 1 dataframe.to_csv('Yte_pred.csv',index_label='Id') ```
Citation
Michael Arbel. Data Challenge - Kernel methods (2025-2026). https://kaggle.com/competitions/data-challenge-kernel-methods-2025-2026, 2026. Kaggle.


