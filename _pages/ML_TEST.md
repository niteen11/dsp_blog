---
permalink: /ML_TEST/
title: "ML_TEST"
---

```python
import pandas as pd
import sklearn
from sklearn.linear_model import LinearRegression
```


```python
lineReg = LinearRegression()
```


```python
# fit
# predict
# score - coefficient of determination
from sklearn.datasets import load_boston
```


```python
boston_dataset = load_boston()
df_boston = pd.DataFrame(boston_dataset.data)
df_boston.columns = boston_dataset.feature_names
```


```python
df_boston['Price'] = boston_dataset.target
```


```python
df_boston.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CRIM</th>
      <th>ZN</th>
      <th>INDUS</th>
      <th>CHAS</th>
      <th>NOX</th>
      <th>RM</th>
      <th>AGE</th>
      <th>DIS</th>
      <th>RAD</th>
      <th>TAX</th>
      <th>PTRATIO</th>
      <th>B</th>
      <th>LSTAT</th>
      <th>Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.00632</td>
      <td>18.0</td>
      <td>2.31</td>
      <td>0.0</td>
      <td>0.538</td>
      <td>6.575</td>
      <td>65.2</td>
      <td>4.0900</td>
      <td>1.0</td>
      <td>296.0</td>
      <td>15.3</td>
      <td>396.90</td>
      <td>4.98</td>
      <td>24.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.02731</td>
      <td>0.0</td>
      <td>7.07</td>
      <td>0.0</td>
      <td>0.469</td>
      <td>6.421</td>
      <td>78.9</td>
      <td>4.9671</td>
      <td>2.0</td>
      <td>242.0</td>
      <td>17.8</td>
      <td>396.90</td>
      <td>9.14</td>
      <td>21.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.02729</td>
      <td>0.0</td>
      <td>7.07</td>
      <td>0.0</td>
      <td>0.469</td>
      <td>7.185</td>
      <td>61.1</td>
      <td>4.9671</td>
      <td>2.0</td>
      <td>242.0</td>
      <td>17.8</td>
      <td>392.83</td>
      <td>4.03</td>
      <td>34.7</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.03237</td>
      <td>0.0</td>
      <td>2.18</td>
      <td>0.0</td>
      <td>0.458</td>
      <td>6.998</td>
      <td>45.8</td>
      <td>6.0622</td>
      <td>3.0</td>
      <td>222.0</td>
      <td>18.7</td>
      <td>394.63</td>
      <td>2.94</td>
      <td>33.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.06905</td>
      <td>0.0</td>
      <td>2.18</td>
      <td>0.0</td>
      <td>0.458</td>
      <td>7.147</td>
      <td>54.2</td>
      <td>6.0622</td>
      <td>3.0</td>
      <td>222.0</td>
      <td>18.7</td>
      <td>396.90</td>
      <td>5.33</td>
      <td>36.2</td>
    </tr>
  </tbody>
</table>
</div>




```python
X_multi = df_boston.drop('Price',1)
```


```python
Y_target = df_boston.Price
```


```python
lineReg.fit(X_multi,Y_target)
```




    LinearRegression(copy_X=True, fit_intercept=True, n_jobs=None, normalize=False)




```python
print('the intercept coeff is %.2f ' % lineReg.intercept_)
print('the number of coeff used %d ' %len(lineReg.coef_))
```

    the intercept coeff is 36.46 
    the number of coeff used 13 
    


```python
X_multi_org = boston_dataset.data
```


```python
Y_org = boston_dataset.target
```


```python
lineReg.fit(X_multi_org,Y_org)
```




    LinearRegression(copy_X=True, fit_intercept=True, n_jobs=None, normalize=False)




```python
print('the intercept coeff is %.2f ' % lineReg.intercept_)
print('the number of coeff used %d ' %len(lineReg.coef_))
```

    the intercept coeff is 36.46 
    the number of coeff used 13 
    


```python
print(pd.Series(lineReg.coef_))
```

    0     -0.108011
    1      0.046420
    2      0.020559
    3      2.686734
    4    -17.766611
    5      3.809865
    6      0.000692
    7     -1.475567
    8      0.306049
    9     -0.012335
    10    -0.952747
    11     0.009312
    12    -0.524758
    dtype: float64
    


```python
df_lineReg = pd.DataFrame(df_boston.columns)
```


```python
df_lineReg.columns = ['Features']
```


```python
df_lineReg['coeff estimate'] = pd.Series(lineReg.coef_)
```


```python
df_lineReg
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Features</th>
      <th>coeff estimate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>CRIM</td>
      <td>-0.108011</td>
    </tr>
    <tr>
      <th>1</th>
      <td>ZN</td>
      <td>0.046420</td>
    </tr>
    <tr>
      <th>2</th>
      <td>INDUS</td>
      <td>0.020559</td>
    </tr>
    <tr>
      <th>3</th>
      <td>CHAS</td>
      <td>2.686734</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NOX</td>
      <td>-17.766611</td>
    </tr>
    <tr>
      <th>5</th>
      <td>RM</td>
      <td>3.809865</td>
    </tr>
    <tr>
      <th>6</th>
      <td>AGE</td>
      <td>0.000692</td>
    </tr>
    <tr>
      <th>7</th>
      <td>DIS</td>
      <td>-1.475567</td>
    </tr>
    <tr>
      <th>8</th>
      <td>RAD</td>
      <td>0.306049</td>
    </tr>
    <tr>
      <th>9</th>
      <td>TAX</td>
      <td>-0.012335</td>
    </tr>
    <tr>
      <th>10</th>
      <td>PTRATIO</td>
      <td>-0.952747</td>
    </tr>
    <tr>
      <th>11</th>
      <td>B</td>
      <td>0.009312</td>
    </tr>
    <tr>
      <th>12</th>
      <td>LSTAT</td>
      <td>-0.524758</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Price</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>


