Name: Narendran K
Register No: 212223230135.
EX. NO.1
Date:
Introduction to Kaggle and Data preprocessing
AIM:
To perform Data preprocessing in a data set downloaded from Kaggle

EQUIPMENTS REQUIRED:
Hardware – PCs Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook

RELATED THEORETICAL CONCEPT:
Kaggle : Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

Data Preprocessing:

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis. Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

Need of Data Preprocessing :

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set. Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.

ALGORITHM:
STEP 1:Importing the libraries
STEP 2:Importing the dataset
STEP 3:Taking care of missing data
STEP 4:Encoding categorical data
STEP 5:Normalizing the data
STEP 6:Splitting the data into test and train

PROGRAM:
Import packages:
import io
import pandas as pd
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split
Data preprocessing:
df=pd.read_csv("Churn_Modelling.csv",index_col="RowNumber")
df.head()
df.isnull().sum()
df.duplicated().sum()
df = df.drop(['Surname', 'Geography', 'Gender'], axis=1)
Scaling:
scaler=StandardScaler()
df=pd.DataFrame(scaler.fit_transform(df))
df.head()
training and testing splitting:
X,Y=df.iloc[:,:-1].values,df.iloc[:,-1].values
xtrain,xtest,ytrain,ytest=train_test_split(X,Y,test_size=0.5)
print("Full X:", X.shape)
print("Train X:", xtrain.shape)
print("Test X:", xtest.shape)
print("Full Y:", Y.shape)
print("Train Y:", ytrain.shape)
print("Test Y:", ytest.shape)
OUTPUT:
Original dataset:
image

Summation of null values:
image

Scaled dataset:
image

Train and test data comparison:
image

RESULT:
Thus, Implementation of Data Preprocessing is done in python using a data set downloaded from Kaggle
