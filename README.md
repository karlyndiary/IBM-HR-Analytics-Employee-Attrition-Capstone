# IBM HR Analytics Employee Attrition Capstone

## Summary

IBM is an American MNC operating in around 170 countries with major business vertical as computing, software, and hardware. Attrition is a major risk to service-providing organizations where trained and experienced people are the assets of the company. The organization would like to identify the factors which influence the attrition of employees.

Data analysis for the case study follows the following steps:

* [1. Prepare](#1-prepare)
* [2. Process](#2-process)
* [3. Analyze and Share](#3-analyze-and-share)

## 1. Prepare
The data used is stored in Kaggle under the IBM Employee Dataset. The dataset contains information about their education, department, and more.

## 2. Process

### 2.1 Installing the necessary packages needed for cleaning and analysis.

```bash
#Installing the packages
import pandas as pd
import numpy as np

#Data Viz
import matplotlib.pyplot as plt
from matplotlib import style
import seaborn as sns
```

### 2.2 Loading the dataset
```bash
attrition_dataset = pd.read_csv('/kaggle/input/employee/train.csv')
```

### 2.3 Exploring the dataframe
```bash
attrition_dataset.head() 
  ```

 ## 3. Analyze and Share
 ## 3.1 Age Distribution

```bash
plt.figure(figsize=(10,10))
plt.hist(attrition_dataset['Age'],bins=70)
plt.title("Age Distribution of Employees")
plt.xlabel("Age of Employees")
plt.ylabel("No of Employees")
plt.show()
  ```
![download (1)](https://user-images.githubusercontent.com/116041695/215382975-beaf2c09-0215-426c-8895-4e6315aa1646.png)

## 3.2 Explore attrition by age
```
plt.figure(figsize=(5,5))
plt.bar(attrition_dataset.Attrition,attrition_dataset.Age, alpha=.55)
plt.title("Attrition by Age")
plt.ylabel("Age of the Employees")
plt.show()  
```
![download](https://user-images.githubusercontent.com/116041695/215382886-28d156c1-10b8-42fc-88d0-a0d319f89204.png)

## 3.3 Explore data for left employees

```
plt.figure(figsize=(8,8))
attrition_dataset.Attrition.value_counts().plot(kind='barh', color='r', alpha = 0.6)
plt.title("Employees Attrition Distribution")
plt.ylabel("Attrition Level")
plt.show()
  ```
![download (2)](https://user-images.githubusercontent.com/116041695/215383006-5c31e363-0946-444a-8dab-cdccdbb7bdf1.png)

## 3.4 Distribution of employees by the education field
```
plt.figure(figsize=(8,8))
attrition_dataset.EducationField.value_counts().plot(kind='barh', color='r', alpha = 0.6)
plt.title("Employees Education Distribution")
plt.ylabel("Education Fields")
plt.show()
```
![download (3)](https://user-images.githubusercontent.com/116041695/215383035-608713b2-aaeb-41a2-ad80-ef5b8c55deeb.png)

## 3.5 Distribution of marital status of employees

```
plt.figure(figsize=(8,8))
attrition_dataset.MaritalStatus.value_counts().plot(kind='barh', color='r', alpha = 0.6)
plt.title("Marital Status")
plt.show()```
```
![download (4)](https://user-images.githubusercontent.com/116041695/215383072-1b5ee2c9-04c4-437a-ad96-75f9d8f394ab.png)
