# GHOULS, GOBLINS AND GHOSTS

![ghost](/images/front_page.png)
                                                                                     
                                            
                                            
## TABLE OF CONTENTS    



### 1. OBJECTIVE

### 2. DATA LOADING AND VISUALIZATION

### 3. EXPLORATING DATA ANALYSIS

### 4. DATA VISUALIZATION
 
### 5. MODEL EVALUATION

### 6. CONCLUSION


### 1. OBJECTIVE
To use **bone length measurements**, **severity of rot**, **extent of soullessness**, and **other characteristics** to distinguish (and extinguish) the intruders.



### 2. DATA LOADING AND VISUALIZATION
Import the necessary packages and load the data set from the following repository:
1. Train_data=pd.read_csv('https://raw.githubusercontent.com/insaid2018/Term-4/master/Projects/Ghouls_train.csv')
2. Test_data=pd.read_csv('https://raw.githubusercontent.com/insaid2018/Term-4/master/Projects/Ghouls_test.csv')



### 3. EXPLORATING DATA ANALYSIS
The training data set has 371 values and 7 features
The testing data set has 529 values and 6 features

The description of the data set is as follows:-


Feature       |  Description
--------------|-------------------------------------------------------------------------------
id            |		id of the creature
bone_length   | 	average length of bone in the creature, normalized between 0 and 1
rotting_flesh |   percentage of rotting flesh in the creature
hair_length   |   average hair length, normalized between 0 and 1
has_soul      |   percentage of soul in the creature
color         |   dominant color of the creature: 'white','black','clear','blue','green','blood'
type          |   target variable: 'Ghost', 'Goblin', and 'Ghoul'

*There are no null values in the data set.*



### 4. DATA VISUALIZATION
__Pair Plot__

On applying pair plot for the categorical values looks this way:-

![pairplot](/images/pairplot.png)

![pairplot1](/images/pairplot1.png)


*Upon observing the above plot we can see that there is no features isolated. All the features are correlated with each other.*


__Heat Map__
![heatmap](/images/heatmap.png)

*Observation:- The features bone_length, hair_length and has_soul have positive values and the rotting_flesh has negative values.*

The column rotting_flesh is not dropped because we cannot afford to miss any features.


__Facet Grid__
![facetgrid](/images/facetgrid.png)

*There are not many outlier except for rotting flesh.



### 5. MODEL EVALUATION

__Model 1: Linear Discriminant Analysis (LDA)__

Chosen Linear Discriminant Analysis (LDA) algorithm to evaluate the model. The LDA algorithm is best suited for data sets with more than 2 categorical values. The confusion matrix and classification metrics is give below

precision | recall | f1-score | support
-----------------------|----------|-----------|----------
Ghost            0.86  |  0.94  | 0.90 | 33
Ghoul            0.71  |  0.89  | 0.79 | 27
Goblin           0.78  |  0.55  | 0.64 | 33
avg / total      0.79  |  0.78  | 0.78 | 93



__Model 2: Logistic Regression__

Then Logistic Regression algorithm is application and report is -

precision | recall | f1-score | support
-----------------------|----------|-----------|----------
Ghost            0.86  |  0.94  | 0.90 | 33
Ghoul            0.71  |  0.89  | 0.79 | 27
Goblin           0.78  |  0.55  | 0.64 | 33
avg / total      0.79  |  0.78  | 0.78 | 93

***Applying LDA and then performing Logistic Regression gives the same accuracy score of 79%.*** 



__Model 3: K Nearest Neighbour__

precision | recall | f1-score | support
-----------------------|----------|-----------|----------
Ghost       0.89     | 0.83    |  0.86 |       29
Ghoul       0.76    |  0.86 |     0.81       | 22
Goblin       0.70    |  0.67     | 0.68    |    24
avg / total    0.79   |   0.79   |   0.79   |     75


***The accuracy score is 78.66%***


__Model 4: Support Vector Machine (SVM)__

precision | recall | f1-score | support
-----------------------|----------|-----------|----------
Ghost       0.92 |     0.79 |     0.85  |      29
Ghoul       0.83 |     0.68   |   0.75  |    22
Goblin       0.59   |   0.79   |   0.68  |      24
avg / total       0.79     | 0.76   |   0.77  |      75


***The accuracy score is 76%***



__Model 5: Decision Tree__

precision | recall | f1-score | support
-----------------------|----------|-----------|----------
Ghost       0.89 |     0.86|      0.88|        29
Ghoul       0.61  |    0.86 |     0.72 |       22
Goblin       0.62   |   0.42  |    0.50     |   24
avg / total       0.73  |    0.72 |     0.71    |    75


***The accuracy score is 72%***



### 6. CONCLUSION

From this we can see that the best algorithm to classify whether it is a ghoul, goblin or ghost is **LDA** followed by **Logistic Regression** and **KNN**.







