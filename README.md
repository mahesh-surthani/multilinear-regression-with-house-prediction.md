# multilinear-regression-with-house-prediction.md
house prediction price with rooms and Furnitures using multi linear regressions



import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn import linear_model

df=pd.read_csv(r"C:\Users\Administrator\Downloads\sample file.csv")
df
df.bedrooms.median()
3.0
import math 
df1 = math.floor(df.bedrooms.median())
df1
3
df.bedrooms=df.bedrooms.fillna(df1)
df.bedrooms
0    3.0
1    4.0
2    3.0
3    3.0
Name: bedrooms, dtype: float64
df.bedrooms
0     3.0
1     4.0
2     3.0
3     5.0
4     3.0
     ... 
94    3.0
95    3.0
96    3.0
97    3.0
98    3.0
Name: bedrooms, Length: 99, dtype: float64
df
<style scoped> .dataframe tbody tr th:only-of-type { vertical-align: middle; }
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
</style>
area	bedrooms	age	price
0	2600	3.0	20	55000
1	3000	4.0	15	64000
2	3200	3.0	18	72000
3	3600	3.0	30	85000
df.head(5)
<style scoped> .dataframe tbody tr th:only-of-type { vertical-align: middle; }
.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
</style>
area	bedrooms	age	price
0	2600	3.0	20	55000
1	3000	4.0	15	64000
2	3200	3.0	18	72000
3	3600	3.0	30	85000
reg = linear_model.LinearRegression()
reg.fit(df[["area","bedrooms","age"]],df.price)
LinearRegression()
reg.coef_
array([   28.75, -1875.  ,   125.  ])
reg.intercept_
-16624.999999999956
reg.predict([[3000,4,15]])
C:\Users\Administrator\anaconda3\lib\site-packages\sklearn\base.py:450: UserWarning: X does not have valid feature names, but LinearRegression was fitted with feature names
  warnings.warn(





array([64000.])
#mutilinear
#y=m1*x1+m2*x2+m3*x3+c
#m is coefficient
#c is intercept
28.75*3600+-1875*3+125*30+-16624.999999999956
85000.00000000004
# finally we pridict the house price , 85000.00000000004
