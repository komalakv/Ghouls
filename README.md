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

The Data Set is divided in 70:30 ratio Train and Testing data which is the Standard Scalar.

__Model 1: Logistic Regression without Linear Discriminant Analysis (LDA)__

Logistic Regression is one of the best classification algorithm. The confusion matrix and classification metrics is give below

precision | recall | f1-score | support
-----------------------|----------|-----------|----------
Ghost         0.90 |     0.85 |    0.88 |       41
Ghoul         0.67 |     0.91 |    0.77 |      35
Goblin        0.68 |     0.47 |    0.56 |     36
avg / total   0.76 |     0.75 |    0.74 |       112

**The Logistic Regression Accuracy Score is 76%.**



__Model 2: Logistic Regression with Linear Discriminant Analysis(LDA)__

Chosen Linear Discriminant Analysis (LDA) algorithm to evaluate the model. The LDA algorithm is best suited for data sets with more than 2 categorical values. Then Logistic Regression algorithm is applied and the confusion matrix and classification metrics is give below -

precision | recall | f1-score | support
-----------------------|----------|-----------|----------
Ghost            0.90 |     0.88   |   0.89   |     41
Ghoul            0.67   |   0.91  |    0.77  |      35
Goblin           0.71   |   0.47  |    0.57   |     36
avg / total       0.77  |    0.76 |     0.75  |     112

***Applying LDA and then performing Logistic Regression gives the same accuracy score of 76%.*** 

#### Time Difference.
Only one column 'color' is dropped. All the other columns are correlated and not isolated. So there is _negligible_ Time difference recorded.

Logistic Regression without LDA | Logistic Regression with LDA | 
--------------------------------|-----------------------------------
0.015626907348632812            |      0.015621423721313477

**Time difference between the two models: 0.999649090687172(99.96%).**



__Model 3: K Nearest Neighbour__

precision | recall | f1-score | support
-----------------------|----------|-----------|----------
Ghost            0.94  |    0.73 |     0.82     |   41
Ghoul            0.63   |   0.77  |    0.69 |       35
Goblin           0.51  |    0.53  |    0.52   |     36
avg / total       0.70   |   0.68   |   0.68   |    112

***The accuracy score is 68%***



__Model 4: Support Vector Machine (SVM)__

precision | recall | f1-score | support
-----------------------|----------|-----------|----------
Ghost       	0.94   |   0.73   |   0.82 |       41
Ghoul      	 0.76  |    0.91  |    0.83   |     35
Goblin      	 0.63  |    0.67  |    0.65    |    36
avg / total       0.78    |  0.77      0.77    |   112

***The accuracy score is 77%***



__Model 5: Decision Tree__

precision | recall | f1-score | support
-----------------------|----------|-----------|----------
Ghost       	0.93  |    0.61 |     0.74 |       41
Ghoul       	0.61  |    0.57   |   0.59   |     35
Goblin       	0.44  |    0.64  |    0.52  |      36
avg / total       0.67  |    0.61   |   0.62     |  112

***The accuracy score is 61%***



### 6. CONCLUSION

From this we can see that the best algorithm to classify whether it is a ghoul, goblin or ghost is **LDA** followed by **Logistic Regression** and **SVM**.







