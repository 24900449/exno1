
# Exno:1
## NAME: M.CHARAN LATHIKA
## REG NO : 212224040052

Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

```
import pandas as pd  
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```

<img width="1914" height="1137" alt="image" src="https://github.com/user-attachments/assets/0a82c51c-59b9-41d5-bf5a-abfd7b53e0dd" />

```
df.head()

```
<img width="1919" height="1141" alt="image" src="https://github.com/user-attachments/assets/bbdd18d3-de4f-4686-a0d0-880c57668c71" />

```
df.tail()
```
<img width="1908" height="761" alt="image" src="https://github.com/user-attachments/assets/50c54cfb-83e2-49cc-87d7-b2cf11cc2d00" />

```
df.info()

```
<img width="1904" height="1133" alt="image" src="https://github.com/user-attachments/assets/a9d39420-1ed2-4b08-8cb8-df78cf9518aa" />

```
df.describe()
```
<img width="1917" height="1139" alt="image" src="https://github.com/user-attachments/assets/9b8f211a-0e5c-48f0-a258-208c4a31ef72" />

```
df.isnull().sum()
```
<img width="1918" height="1141" alt="image" src="https://github.com/user-attachments/assets/93aae9eb-6860-4d38-809d-18dd31110975" />

```
df.isnull().any()
```
<img width="1918" height="1144" alt="image" src="https://github.com/user-attachments/assets/3301a572-9154-41aa-91ae-978737d1aea8" />

```
df.dropna()
```
<img width="1906" height="1130" alt="image" src="https://github.com/user-attachments/assets/467b0bcf-5ad5-4de6-b843-360faad347ee" />

```
df.fillna(0)
```

<img width="1915" height="1110" alt="image" src="https://github.com/user-attachments/assets/27ad0b6d-b412-4ee7-9dc7-7353c2664fc3" />

```
df.fillna(method='ffill')
```
<img width="1908" height="1127" alt="image" src="https://github.com/user-attachments/assets/6b24cf0b-f6c9-4a71-a245-713d6507b97f" />

```
df.fillna({'GENDER':'MALE','NAME':'SRI'})

```
<img width="1837" height="1068" alt="image" src="https://github.com/user-attachments/assets/17f4cd96-1526-447a-87af-935b39c95b7e" />

```
ir=pd.read_csv("/content/iris.csv")
ir
```

![1](https://github.com/user-attachments/assets/1d660f6b-560e-4818-92b0-22cd15fda715)

```
ir.describe()

```

![2](https://github.com/user-attachments/assets/d0579466-3ff4-4750-b0e0-99e4b4edc8fe)

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)

```

![3](https://github.com/user-attachments/assets/9ffcebc3-2384-4919-927d-14c2bd5b1793)

```
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
(IQR)=Q3-Q1
print(IQR)

```

![4](https://github.com/user-attachments/assets/3b9a5ce1-1727-4b22-92f3-f341b72ecba3)

```
ran=ir[((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```

![4](https://github.com/user-attachments/assets/baed2042-9696-46bc-93b1-93fc0d47725d)

```
sns.boxplot(x='sepal_width',data=ran)
```

<img width="1600" height="950" alt="image" src="https://github.com/user-attachments/assets/46fb024c-32f6-43a5-bc37-dda8d7e7313e" />

```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir['petal_length']))
z
```

<img width="1600" height="950" alt="image" src="https://github.com/user-attachments/assets/2ce58cf0-65c3-4030-8b96-882f1fb1285b" />

```
ir1=ir[z<3]
ir1
```

<img width="1600" height="950" alt="image" src="https://github.com/user-attachments/assets/501e3c69-fd79-4784-ae05-ace1a85e3467" />

            
# Result

Thus the given data successfully performed data cleaning and saved the cleaned data to a file


          <<include your Result here>>

