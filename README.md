**DATA CLEANING PROCESS**

NAME : AKSHAYA V A

REGISTER NUMBER : 212224040019

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
df=pd.read_csv("SAMPLEIDS.csv")
df.describe()
```

<img width="1376" height="486" alt="Screenshot 2026-02-18 134253" src="https://github.com/user-attachments/assets/265ac6dc-1345-4ecc-93e8-83ff56090811" />


```
df.info()
```
<img width="1311" height="480" alt="Screenshot 2026-02-18 134303" src="https://github.com/user-attachments/assets/795ae604-5231-45ce-9b51-413685fce717" />


```
df.head()
```
<img width="1326" height="382" alt="Screenshot 2026-02-18 134314" src="https://github.com/user-attachments/assets/0a66ff69-1fc5-4be1-8aae-4ca8e2aa368d" />


```
df.isnull()
```
<img width="928" height="873" alt="Screenshot 2026-02-18 134325" src="https://github.com/user-attachments/assets/5a698a88-ed51-4a59-bee9-be6dea8efb9f" />


```
df.isnull().sum()
```
<img width="959" height="619" alt="Screenshot 2026-02-18 134344" src="https://github.com/user-attachments/assets/bf905d0f-fcf7-4e53-9830-b32c947e6819" />


```
df_clean = df.dropna()
df_clean
```
<img width="1167" height="704" alt="Screenshot 2026-02-18 134352" src="https://github.com/user-attachments/assets/d5aebc50-4d56-43ad-b206-ece40f9aa544" />



```
numeric_df = df_clean.select_dtypes(include=['float64', 'int64'])

Q1 = numeric_df.quantile(0.25, numeric_only=True)
Q3 = numeric_df.quantile(0.75, numeric_only=True)
IQR = Q3 - Q1

data = df_clean[~((numeric_df < (Q1 - 1.5 * IQR)) | (numeric_df > (Q3 + 1.5 * IQR))).any(axis=1)]
data
```
<img width="1202" height="822" alt="Screenshot 2026-02-18 134408" src="https://github.com/user-attachments/assets/9657cd88-6cec-4b00-9cbb-61ccc87847ef" />


```
import pandas as pd
df=pd.read_csv("Data_set (1).csv")
df.describe()
```

<img width="1310" height="494" alt="Screenshot 2026-02-18 135613" src="https://github.com/user-attachments/assets/1645bfd5-47d0-4326-ac25-2070ef00951e" />


```
df.head()
```


<img width="1372" height="537" alt="image" src="https://github.com/user-attachments/assets/1094377f-ec8f-4ca4-b325-4ef82a260785" />


```
df.tail()
```

<img width="1349" height="494" alt="image" src="https://github.com/user-attachments/assets/bce060c4-e9b4-4418-ae54-2be0f6ca9b99" />


```
df.isnull()
```

<img width="795" height="426" alt="image" src="https://github.com/user-attachments/assets/b4dac22b-80e3-4b7d-bf10-5c3e429601d6" />


```
df.isnull().sum()
```

<img width="358" height="512" alt="image" src="https://github.com/user-attachments/assets/bddd977f-327f-4230-93c6-2bfbb038b2ff" />


```
df_clean = df.dropna()
df_clean
```


<img width="1357" height="835" alt="image" src="https://github.com/user-attachments/assets/5c3c8e63-438c-4551-b089-ead7546b24e3" />


```
numeric_df = df_clean.select_dtypes(include=['float64', 'int64'])

Q1 = numeric_df.quantile(0.25, numeric_only=True)
Q3 = numeric_df.quantile(0.75, numeric_only=True)
IQR = Q3 - Q1

data = df_clean[~((numeric_df < (Q1 - 1.5 * IQR)) | (numeric_df > (Q3 + 1.5 * IQR))).any(axis=1)]
data
```

<img width="1299" height="808" alt="image" src="https://github.com/user-attachments/assets/fd0694a7-6310-4378-94bc-4115f7e701af" />


```
import pandas as pd
df=pd.read_csv("heights (1).csv")
df.describe()
```

<img width="627" height="491" alt="image" src="https://github.com/user-attachments/assets/93ab1f4c-3ea0-4d7d-9a23-c19e27191484" />


```
df.head()
```

<img width="933" height="454" alt="image" src="https://github.com/user-attachments/assets/99b09ed4-8649-4e30-9912-5bb165d62cfa" />


```
df.tail()
```


<img width="511" height="340" alt="image" src="https://github.com/user-attachments/assets/7cc3f193-fb23-4605-ac19-d424b8286494" />


```
df.isnull()
```

<img width="560" height="697" alt="image" src="https://github.com/user-attachments/assets/5966b4c9-14fc-40c0-9020-c8ce4f5ae228" />


```
df.isnull().sum()
```


<img width="561" height="267" alt="image" src="https://github.com/user-attachments/assets/a6c7c8d7-636c-4ba3-952b-6603db46d382" />


```
df_clean = df.dropna()
df_clean
```

<img width="672" height="750" alt="image" src="https://github.com/user-attachments/assets/a77098a8-d867-40d4-a756-1ded7c7f5359" />



```
numeric_df = df_clean.select_dtypes(include=['float64', 'int64'])

Q1 = numeric_df.quantile(0.25, numeric_only=True)
Q3 = numeric_df.quantile(0.75, numeric_only=True)
IQR = Q3 - Q1

data = df_clean[~((numeric_df < (Q1 - 1.5 * IQR)) | (numeric_df > (Q3 + 1.5 * IQR))).any(axis=1)]
data
```


<img width="1026" height="747" alt="image" src="https://github.com/user-attachments/assets/369987a9-d753-4936-816b-27249a67777d" />


```
import pandas as pd
df=pd.read_csv("Loan_data.csv")
df.describe()
```

<img width="1147" height="509" alt="image" src="https://github.com/user-attachments/assets/8e5d0dd2-920b-44a8-ba39-f0fb953d7930" />


```
df.info
```


<img width="1147" height="509" alt="image" src="https://github.com/user-attachments/assets/0c1b703b-c4e2-403b-860f-44ed28375c44" />


```
df.head()
```

<img width="1360" height="486" alt="image" src="https://github.com/user-attachments/assets/2023a132-ff27-4c64-b253-431333b2adf5" />


```
df.tail()
```


<img width="1369" height="373" alt="image" src="https://github.com/user-attachments/assets/4b514acd-810c-4e75-a349-12bae196ece1" />


```
df.isnull()
```

<img width="1364" height="655" alt="image" src="https://github.com/user-attachments/assets/008af5bb-e66d-4804-97f5-1fb138ecbe91" />

```
numeric_df = df_clean.select_dtypes(include=['float64', 'int64'])

Q1 = numeric_df.quantile(0.25, numeric_only=True)
Q3 = numeric_df.quantile(0.75, numeric_only=True)
IQR = Q3 - Q1

data = df_clean[~((numeric_df < (Q1 - 1.5 * IQR)) | (numeric_df > (Q3 + 1.5 * IQR))).any(axis=1)]
data
```

<img width="1069" height="777" alt="image" src="https://github.com/user-attachments/assets/3ebcd2a2-37f0-443f-bc9e-fedd4a4d0038" />


```
import pandas as pd
df=pd.read_csv("C:\\Users\\admin\\Downloads\\Data_set.csv")
df.describe()
```

<img width="883" height="536" alt="image" src="https://github.com/user-attachments/assets/7ea353c0-3998-4640-9cd6-471d4563d8ee" />


```
df.head()
```

<img width="974" height="387" alt="image" src="https://github.com/user-attachments/assets/51ed117a-8b01-44d2-a47e-ecdcfb0c176e" />


```
df.info()
```

<img width="857" height="359" alt="image" src="https://github.com/user-attachments/assets/eba92746-b2cc-4673-9ce2-5bd641699345" />



```
df.isnull().sum()
```

<img width="1099" height="502" alt="image" src="https://github.com/user-attachments/assets/c84bf741-f15c-40b9-89ef-8a48e46cca6a" />


```
df_clean = df.dropna()
df_clean
```

<img width="980" height="687" alt="image" src="https://github.com/user-attachments/assets/1d4b6251-b2b2-4d66-a841-376e475a0403" />


```
numeric_df = df_clean.select_dtypes(include=['float64', 'int64'])

Q1 = numeric_df.quantile(0.25, numeric_only=True)
Q3 = numeric_df.quantile(0.75, numeric_only=True)
IQR = Q3 - Q1

data = df_clean[~((numeric_df < (Q1 - 1.5 * IQR)) | (numeric_df > (Q3 + 1.5 * IQR))).any(axis=1)]
data
```

<img width="1062" height="721" alt="image" src="https://github.com/user-attachments/assets/854e7f33-2f5e-4ca3-8ae1-0df996756ea9" />


The program was successfully executed 
