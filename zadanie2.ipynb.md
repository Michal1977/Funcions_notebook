```python

```


```python
prices = [
	(1, 2.12),
	(2, 2.56),
	(3, 3.10),
	(4, 3.16),
	(5, 3.58),
	(6, 5.12),
	(7, 5.16),
	(8, 5.20),
	(9, 4.12),
	(10, 4.10),
	(11, 3.65),
	(12, 4.25),
]

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

df = pd.DataFrame(prices, columns=["month", "pln_price"])
df = df.set_index("month")

matrix1 = np.array(prices)
pln_prices = matrix1[:, 1]
for price in prices:
    usd = list(map(lambda price:price/4, pln_prices))
    
df['usd_price'] = usd

print(df)

df['usd_price'].plot(kind='line',color='red', title="Price of goods (USD)")
```

           pln_price  usd_price
    month                      
    1           2.12     0.5300
    2           2.56     0.6400
    3           3.10     0.7750
    4           3.16     0.7900
    5           3.58     0.8950
    6           5.12     1.2800
    7           5.16     1.2900
    8           5.20     1.3000
    9           4.12     1.0300
    10          4.10     1.0250
    11          3.65     0.9125
    12          4.25     1.0625
    




    <AxesSubplot:title={'center':'Price of goods (USD)'}, xlabel='month'>




    
![png](output_1_2.png)
    



```python

```
