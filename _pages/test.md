---
permalink: /TEST/
title: "TEST"
toc: true
toc_sticky: true
---

## Data Acquisition

```python
import os
```


```python
from platform import python_version
print(python_version())
```

    3.6.9
    
## Setting up libraries

```python
import numpy as np
```


```python
ar1 = np.arange(12)
```

## Data Wrangling

```python
ar1
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11])




```python
ar1.reshape(4,3)
```




    array([[ 0,  1,  2],
           [ 3,  4,  5],
           [ 6,  7,  8],
           [ 9, 10, 11]])




```python
x= [4,7,3,8,9,10,1,5,2]
#y = sorted(x)
#print(y)
```


```python
x.sort()
```


```python
x
```




    [1, 2, 3, 4, 5, 7, 8, 9, 10]




```python

```
