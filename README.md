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

* There are no null values in the data set.



### 4. DATA VISUALIZATION
On applying pair plot for the categorical values looks this way:-

![pairplot](/images/pairplot.png)





