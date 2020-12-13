# Introduction

The goal of this machine learning algorithm is to predict the Wilks Coefficient (see description here: https://en.wikipedia.org/wiki/Wilks_Coefficient) by feeding the algorithm info about the name, age, weight, sex, date, birth year, whether the competitor was tested or not, what equipment was used (we are only looking at single-ply or raw competitions).

# Data preparation

1) Only the following columns were selected:
 * Name
 * Sex
 * Event
 * Equipment
 * Age
 * Wilks
 * Tested
 * Date
 
2) Tested column contained only values 'Yes' or NaN. The NaN values were changed to 0. The 'Yes' values were changed to 1.
3) The column Sex values were changed from 'M' and 'F' to 0 and 1 respectively.
4) All rows where Event value was not 'SBD' were dropped and Event column was dropped after that.
5) Any row where age value was NaN was removed.
6) Any row where equipment wasn't raw or single ply was dropped, raw was changed to 0 and single ply to 1. 
7) Column BirthYear was created by subtracting age from competition date (note that there is a margin of error of 1 year).
8) Unique identifier based on sex, birth year, name was added to each person.
9) The name column was dropped.
10) The amount of competitions the person has participated in previously was added as a column.
11) Created column WilksRangeCat where categories are separated by 50 wilks.

# Modeling

* Tested 10 machine learning models, 5 of which were somewhat successful at predicting the wilks of a given competitior.
* The successful models, sorted by accuracy (ascendingly) were:
1) Random Forest Classifier (n = 500)
2) Extra Trees Classifier (n = 500)
3) K-Nearest Neighbours (n = 500)
4) Decision Tree
5) Logistic Regression

* The best performing model was Random Forest Classifier, which was to be expected as it is the best fitting model for multi classification problems. The random forest classifier predicted the category accurately 36% of the times and if considering a margin of error of +-1 category, it had an accuracy score of 80%.

# Descriptions of uploaded files

* Clean data explore.ipynb - After cleaning the data, we explored the correlations of features and label.
* D18_POSTER.pdf - Poster created for IDS course.
* D18_report.pdf - Report created for IDS course.
* Data explore.ipynb - Explored the characteristics of features of the unchanged dataset.
* Data preparation.ipynb - Used for cleaning the data.
* ids_d18_robert_tiit.7z - Zipped file of quick introductory video to our project.
* model.ipynb - Implementation of machine learning models.

# Analysis of powerlifting meet results

Slides link: https://docs.google.com/presentation/d/1p5AruemwHJht2R7oy1kXl_Ge10rQTo49TdyiNRUrvmE/edit?usp=sharing

Google drive link: https://drive.google.com/drive/folders/1m7UdXe4uQyvVMOy3wm7Od8xL6WlUmpbu?usp=sharing

CRISP-DM: https://courses.cs.ut.ee/MTAT.03.183/2017_fall/uploads/Main/crisp_dm.pdf

Kaggle: https://www.kaggle.com/open-powerlifting/powerlifting-database?fbclid=IwAR3L-NNbuKvnXG1MZBf8pwwcYt89uAQ2g1RAfiyZVn_evC21Ly9F7svm5lM

IDS2020 project information: https://docs.google.com/presentation/d/1Ldl_UVf3-GZkpof0rr3E-C5n8q1pDN4PSK4InFVq7wE/edit#slide=id.g2b7c3c841b_0_188

Project intro wed.: https://docs.google.com/presentation/d/1fRqAWlIpUAKgAECPALabtxUP3LKDCB6Dc3iyZyBRXP8/edit#slide=id.g5405b9959a_4_5

Project poster: https://docs.google.com/presentation/d/1GwUD-EzZ2yqFVkimAJurYM4YRoSDHs2iFdknpAsI7bM/edit?usp=sharing
