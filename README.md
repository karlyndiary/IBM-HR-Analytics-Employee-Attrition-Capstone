# IBM HR Analytics Employee Attrition Capstone

## 1. Summary

IBM is an American MNC operating in around 170 countries with major business vertical as computing, software, and hardware. Attrition is a major risk to service-providing organizations where trained and experienced people are the assets of the company. The organization would like to identify the factors which influence the attrition of employees.

## 2. Prepare
The data used is stored in Kaggle under the IBM Employee Dataset. The dataset contains information about their education, department, and more.

## 3. Process

### 3.1 Installing the necessary packages needed for cleaning and analysis.

```bash
#Installing the packages
import pandas as pd
import numpy as np

#Data Viz
import matplotlib.pyplot as plt
from matplotlib import style
import seaborn as sns
```

### 3.2 Loading the dataset
```bash
attrition_dataset = pd.read_csv('/kaggle/input/employee/train.csv')
```

### 3.3 Exploring the dataframe
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
  ![image](https://www.kaggleusercontent.com/kf/117531757/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..yOcaLCFlPwPPP4qICpoY7A.dJz9_LxO3O8Yyx3dJ3B-T_o9q7Cgqq4C81qwzGxBJ89dceZeQ5A9boWeFS7o_5CeBEPhYlQXMJ4yGJFMNf-fILFyXhF7iZssM6C2uetzw3GL1e5roAelKOg8yel0DlmdRbsT_EX0tjrgJwE3NYV3bPaAXdxgf8gU3__2P7n3yPvTt0Z7tAvF2pUsMMx4b-ipZMFudtVljn65Tps3t4_NV65M1kJn3h12glEBMuSbCvjDTaUNhjn57T4DlL4XKQbGL7YIf1CE89q6IihmPr8UJ5kLOcOvUKmwODb6_3eR6C1gNXErgMnpS7xCpNaUvPryI-3XTUVtqTvXIV6_eiGQEcrxRcgn4AlVUF9wUsMxOEDiW36Eaj_F0ADjfVHTbRYe2aJGjFgVRmR7nUo__CDIDSiAAo8RwJap2JX0rGaDe1d4I4EzPMC-yV-fkxc9RAIXlebMnyMnK62URCFLq2iSFGnlcWWGe8zcMUFzNiBEInXAmq0HovdpG_ZtxltW1loq5WHyzoUNDzJjJq320A5ycuQ83zWaz-m8rD0dq_7CbjLkQMjcdFOxHdFISFFWNBiQHtg2q_JD4vGPv0Tq9NpBEo6XvZ9qajJxZSdxzABfAhGxcUkMFytAkTfiOvc347hjHMre_dhiuVklMLEmnqI3dgUtQZsONB1PE89Xp4Nyxj9020Cdog2_2K5O4Gn-JirHmy_M0A4IbvDlh49EQQsxYA.F6zp1yLe6a3vzmaA2df_0g/__results___files/__results___8_0.png)
 
 **Explore attrition by age**
```
plt.figure(figsize=(5,5))
plt.bar(attrition_dataset.Attrition,attrition_dataset.Age, alpha=.55)
plt.title("Attrition by Age")
plt.ylabel("Age of the Employees")
plt.show()  
```
 ![image](https://www.kaggleusercontent.com/kf/117531757/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..yOcaLCFlPwPPP4qICpoY7A.dJz9_LxO3O8Yyx3dJ3B-T_o9q7Cgqq4C81qwzGxBJ89dceZeQ5A9boWeFS7o_5CeBEPhYlQXMJ4yGJFMNf-fILFyXhF7iZssM6C2uetzw3GL1e5roAelKOg8yel0DlmdRbsT_EX0tjrgJwE3NYV3bPaAXdxgf8gU3__2P7n3yPvTt0Z7tAvF2pUsMMx4b-ipZMFudtVljn65Tps3t4_NV65M1kJn3h12glEBMuSbCvjDTaUNhjn57T4DlL4XKQbGL7YIf1CE89q6IihmPr8UJ5kLOcOvUKmwODb6_3eR6C1gNXErgMnpS7xCpNaUvPryI-3XTUVtqTvXIV6_eiGQEcrxRcgn4AlVUF9wUsMxOEDiW36Eaj_F0ADjfVHTbRYe2aJGjFgVRmR7nUo__CDIDSiAAo8RwJap2JX0rGaDe1d4I4EzPMC-yV-fkxc9RAIXlebMnyMnK62URCFLq2iSFGnlcWWGe8zcMUFzNiBEInXAmq0HovdpG_ZtxltW1loq5WHyzoUNDzJjJq320A5ycuQ83zWaz-m8rD0dq_7CbjLkQMjcdFOxHdFISFFWNBiQHtg2q_JD4vGPv0Tq9NpBEo6XvZ9qajJxZSdxzABfAhGxcUkMFytAkTfiOvc347hjHMre_dhiuVklMLEmnqI3dgUtQZsONB1PE89Xp4Nyxj9020Cdog2_2K5O4Gn-JirHmy_M0A4IbvDlh49EQQsxYA.F6zp1yLe6a3vzmaA2df_0g/__results___files/__results___10_0.png)

**Explore data for left employees**

```
plt.figure(figsize=(8,8))
attrition_dataset.Attrition.value_counts().plot(kind='barh', color='r', alpha = 0.6)
plt.title("Employees Attrition Distribution")
plt.ylabel("Attrition Level")
plt.show()
  ```

  ![image](https://www.kaggleusercontent.com/kf/117531757/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..yOcaLCFlPwPPP4qICpoY7A.dJz9_LxO3O8Yyx3dJ3B-T_o9q7Cgqq4C81qwzGxBJ89dceZeQ5A9boWeFS7o_5CeBEPhYlQXMJ4yGJFMNf-fILFyXhF7iZssM6C2uetzw3GL1e5roAelKOg8yel0DlmdRbsT_EX0tjrgJwE3NYV3bPaAXdxgf8gU3__2P7n3yPvTt0Z7tAvF2pUsMMx4b-ipZMFudtVljn65Tps3t4_NV65M1kJn3h12glEBMuSbCvjDTaUNhjn57T4DlL4XKQbGL7YIf1CE89q6IihmPr8UJ5kLOcOvUKmwODb6_3eR6C1gNXErgMnpS7xCpNaUvPryI-3XTUVtqTvXIV6_eiGQEcrxRcgn4AlVUF9wUsMxOEDiW36Eaj_F0ADjfVHTbRYe2aJGjFgVRmR7nUo__CDIDSiAAo8RwJap2JX0rGaDe1d4I4EzPMC-yV-fkxc9RAIXlebMnyMnK62URCFLq2iSFGnlcWWGe8zcMUFzNiBEInXAmq0HovdpG_ZtxltW1loq5WHyzoUNDzJjJq320A5ycuQ83zWaz-m8rD0dq_7CbjLkQMjcdFOxHdFISFFWNBiQHtg2q_JD4vGPv0Tq9NpBEo6XvZ9qajJxZSdxzABfAhGxcUkMFytAkTfiOvc347hjHMre_dhiuVklMLEmnqI3dgUtQZsONB1PE89Xp4Nyxj9020Cdog2_2K5O4Gn-JirHmy_M0A4IbvDlh49EQQsxYA.F6zp1yLe6a3vzmaA2df_0g/__results___files/__results___12_0.png)

**Distribution of employees by the education field**
```
plt.figure(figsize=(8,8))
attrition_dataset.EducationField.value_counts().plot(kind='barh', color='r', alpha = 0.6)
plt.title("Employees Education Distribution")
plt.ylabel("Education Fields")
plt.show()
```
![image](https://www.kaggleusercontent.com/kf/117531757/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..yOcaLCFlPwPPP4qICpoY7A.dJz9_LxO3O8Yyx3dJ3B-T_o9q7Cgqq4C81qwzGxBJ89dceZeQ5A9boWeFS7o_5CeBEPhYlQXMJ4yGJFMNf-fILFyXhF7iZssM6C2uetzw3GL1e5roAelKOg8yel0DlmdRbsT_EX0tjrgJwE3NYV3bPaAXdxgf8gU3__2P7n3yPvTt0Z7tAvF2pUsMMx4b-ipZMFudtVljn65Tps3t4_NV65M1kJn3h12glEBMuSbCvjDTaUNhjn57T4DlL4XKQbGL7YIf1CE89q6IihmPr8UJ5kLOcOvUKmwODb6_3eR6C1gNXErgMnpS7xCpNaUvPryI-3XTUVtqTvXIV6_eiGQEcrxRcgn4AlVUF9wUsMxOEDiW36Eaj_F0ADjfVHTbRYe2aJGjFgVRmR7nUo__CDIDSiAAo8RwJap2JX0rGaDe1d4I4EzPMC-yV-fkxc9RAIXlebMnyMnK62URCFLq2iSFGnlcWWGe8zcMUFzNiBEInXAmq0HovdpG_ZtxltW1loq5WHyzoUNDzJjJq320A5ycuQ83zWaz-m8rD0dq_7CbjLkQMjcdFOxHdFISFFWNBiQHtg2q_JD4vGPv0Tq9NpBEo6XvZ9qajJxZSdxzABfAhGxcUkMFytAkTfiOvc347hjHMre_dhiuVklMLEmnqI3dgUtQZsONB1PE89Xp4Nyxj9020Cdog2_2K5O4Gn-JirHmy_M0A4IbvDlh49EQQsxYA.F6zp1yLe6a3vzmaA2df_0g/__results___files/__results___14_0.png)

**Distribution of marital status of employees**

```
plt.figure(figsize=(8,8))
attrition_dataset.MaritalStatus.value_counts().plot(kind='barh', color='r', alpha = 0.6)
plt.title("Marital Status")
plt.show()```
```
![image](https://www.kaggleusercontent.com/kf/117531757/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..yOcaLCFlPwPPP4qICpoY7A.dJz9_LxO3O8Yyx3dJ3B-T_o9q7Cgqq4C81qwzGxBJ89dceZeQ5A9boWeFS7o_5CeBEPhYlQXMJ4yGJFMNf-fILFyXhF7iZssM6C2uetzw3GL1e5roAelKOg8yel0DlmdRbsT_EX0tjrgJwE3NYV3bPaAXdxgf8gU3__2P7n3yPvTt0Z7tAvF2pUsMMx4b-ipZMFudtVljn65Tps3t4_NV65M1kJn3h12glEBMuSbCvjDTaUNhjn57T4DlL4XKQbGL7YIf1CE89q6IihmPr8UJ5kLOcOvUKmwODb6_3eR6C1gNXErgMnpS7xCpNaUvPryI-3XTUVtqTvXIV6_eiGQEcrxRcgn4AlVUF9wUsMxOEDiW36Eaj_F0ADjfVHTbRYe2aJGjFgVRmR7nUo__CDIDSiAAo8RwJap2JX0rGaDe1d4I4EzPMC-yV-fkxc9RAIXlebMnyMnK62URCFLq2iSFGnlcWWGe8zcMUFzNiBEInXAmq0HovdpG_ZtxltW1loq5WHyzoUNDzJjJq320A5ycuQ83zWaz-m8rD0dq_7CbjLkQMjcdFOxHdFISFFWNBiQHtg2q_JD4vGPv0Tq9NpBEo6XvZ9qajJxZSdxzABfAhGxcUkMFytAkTfiOvc347hjHMre_dhiuVklMLEmnqI3dgUtQZsONB1PE89Xp4Nyxj9020Cdog2_2K5O4Gn-JirHmy_M0A4IbvDlh49EQQsxYA.F6zp1yLe6a3vzmaA2df_0g/__results___files/__results___16_0.png)
