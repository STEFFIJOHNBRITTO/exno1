# Exno:1
Data Cleaning Process

# NAME : STEFFI J
# REG NO : 212224220107
# DATE : 30-08-2025

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
df=pd.read_csv("SAMPLEIDS (1).csv")
df
```
# OUTPUT

<img width="1027" height="858" alt="image" src="https://github.com/user-attachments/assets/2c4bb8af-9e20-40db-a880-f969f152817a" />

```
df.head()
```

# OUTPUT 

<img width="1242" height="325" alt="image" src="https://github.com/user-attachments/assets/55a32d52-b06a-4291-a38e-703067ea67af" />

```
df.tail()
```

# OUTPUT

<img width="1233" height="322" alt="image" src="https://github.com/user-attachments/assets/70a0a660-6db0-4937-8863-54d79ba2532c" />

```
df.head(3)
```

# OUTPUT

<img width="1135" height="247" alt="image" src="https://github.com/user-attachments/assets/55a3aeb8-3bcb-4ac9-9592-613c3f2182ea" />

```
df.tail(2)
```

# OUTPUT

<img width="1176" height="217" alt="image" src="https://github.com/user-attachments/assets/e27399ee-8d12-4009-8c5f-8b1f49cc65a5" />

```
df.isnull()
```

# OUTPUT

<img width="838" height="862" alt="image" src="https://github.com/user-attachments/assets/6631e559-5a59-493a-ab22-7892967d105e" />

```
df.notnull()
```

# OUTPUT

<img width="835" height="873" alt="image" src="https://github.com/user-attachments/assets/ff74df7e-4017-440c-a563-0761146a7f13" />

```
df.isnull().sum()
```

# OUTPUT

<img width="393" height="633" alt="image" src="https://github.com/user-attachments/assets/7416fac1-04b7-41c2-aa90-f8b57a4027ed" />

```
df.isnull().any()
```

# OUTPUT

<img width="362" height="642" alt="image" src="https://github.com/user-attachments/assets/88b1de8b-5299-46c4-beb7-9b4eb9f39f39" />

```
df.dropna(axis=0)
```

# OUTPUT

<img width="1078" height="642" alt="image" src="https://github.com/user-attachments/assets/96dc41d8-c8d0-408c-a16c-c2ef90b9981a" />

```
df.dropna(axis=1)
```

# OUTPUT

<img width="397" height="855" alt="image" src="https://github.com/user-attachments/assets/7c302224-a3c4-401b-bfc5-7aa46f02adeb" />

```
df.fillna(0)
```

# OUTPUT

<img width="1035" height="871" alt="image" src="https://github.com/user-attachments/assets/61392e78-494f-48ee-9c45-ccd712ece0ff" />

```
df.fillna(method="ffill")
```

# OUTPUT

<img width="1033" height="863" alt="image" src="https://github.com/user-attachments/assets/fb8e42df-13fd-49de-8f8c-f20ea6d3bf81" />

```
df.fillna(method="bfill")
```

# OUTPUT

<img width="1061" height="852" alt="image" src="https://github.com/user-attachments/assets/00d576a8-8cfd-4906-b701-50ca3133c42a" />

```
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'PONAMALEE','M1':98,'M2':87,'M3':76,'M3':92,'TOTAL':305,'AVG':89.999999})
```

# OUTPUT

<img width="1012" height="860" alt="image" src="https://github.com/user-attachments/assets/501f7191-edfe-4bd5-a9d3-ef94e7283dc2" />

```
import pandas as pd
ir=pd.read_csv("iris (1).csv")
ir
```

# OUTPUT

<img width="725" height="617" alt="image" src="https://github.com/user-attachments/assets/ad30a36f-2285-4df2-9486-abe6a6b83cb5" />

```
ir.describe()
```

# OUTPUT

<img width="651" height="433" alt="image" src="https://github.com/user-attachments/assets/a4d0a15f-70ce-4c2f-91d1-2412dbaf0a9e" />

```
import seaborn as sns
```
```
sns.boxplot(x='sepal_width',data=ir)
```

# OUTPUT

<img width="842" height="716" alt="image" src="https://github.com/user-attachments/assets/ea498ef8-6ee4-456b-b4ba-d6226e8157e0" />

```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```

# OUTPUT

<img width="435" height="177" alt="image" src="https://github.com/user-attachments/assets/4152726c-69c2-43fc-a795-1ca68e37776a" />

```
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```

# OUTPUT

<img width="882" height="342" alt="image" src="https://github.com/user-attachments/assets/035fb1bd-b189-44b0-959b-1d0d092fb694" />

```
rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```
# OUTPUT

<img width="883" height="657" alt="image" src="https://github.com/user-attachments/assets/7f8f8b58-5633-4a49-84bc-de67b5244694" />

```
rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
```

# OUTPUT

<img width="797" height="658" alt="image" src="https://github.com/user-attachments/assets/e57b8f54-0803-45d0-ba53-c6deec35155f" />

```
sns.boxplot(x='sepal_width',data=rid)
```

# OUTPUT

<img width="917" height="652" alt="image" src="https://github.com/user-attachments/assets/7b79f84e-3017-4907-ad06-61f231049fe8" />

```
import numpy as np
import scipy.stats as stats
```
```
z=np.abs(stats.zscore(ir.sepal_width))
z
```

# OUTPUT

<img width="880" height="845" alt="image" src="https://github.com/user-attachments/assets/8cdf4d5f-ee0e-406a-a29c-2b0120cbe4d0" />


# Result
          
Thus, we have read the given data and performed data cleaning and saved the cleaned data to a file successfully.
