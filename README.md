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
  **Age Distribution**

```bash
plt.figure(figsize=(10,10))
plt.hist(attrition_dataset['Age'],bins=70)
plt.title("Age Distribution of Employees")
plt.xlabel("Age of Employees")
plt.ylabel("No of Employees")
plt.show()
  ```
  ![__results___8_0 (1)](https://user-images.githubusercontent.com/116041695/215379406-97e986c1-113f-4fc9-be0e-5efc96b8a597.png)

 **Explore attrition by age**
```
plt.figure(figsize=(5,5))
plt.bar(attrition_dataset.Attrition,attrition_dataset.Age, alpha=.55)
plt.title("Attrition by Age")
plt.ylabel("Age of the Employees")
plt.show()  
```
![download](https://user-images.githubusercontent.com/116041695/215382886-28d156c1-10b8-42fc-88d0-a0d319f89204.png)

**Explore data for left employees**

```
plt.figure(figsize=(8,8))
attrition_dataset.Attrition.value_counts().plot(kind='barh', color='r', alpha = 0.6)
plt.title("Employees Attrition Distribution")
plt.ylabel("Attrition Level")
plt.show()
  ```
![__results___12_0](https://user-images.githubusercontent.com/116041695/215379501-029e3c96-482a-481b-a1c1-69bbc9f90f9b.png)

**Distribution of employees by the education field**
```
plt.figure(figsize=(8,8))
attrition_dataset.EducationField.value_counts().plot(kind='barh', color='r', alpha = 0.6)
plt.title("Employees Education Distribution")
plt.ylabel("Education Fields")
plt.show()
```
![__results___14_0](https://user-images.githubusercontent.com/116041695/215379532-74933a7d-bb43-40a9-9d57-00b5f4fcd05e.png)

**Distribution of marital status of employees**

```
plt.figure(figsize=(8,8))
attrition_dataset.MaritalStatus.value_counts().plot(kind='barh', color='r', alpha = 0.6)
plt.title("Marital Status")
plt.show()```
```
![__results___16_0](https://user-images.githubusercontent.com/116041695/215379559-92e5d8aa-ab57-4abf-a255-00dce1eeccad.png)
