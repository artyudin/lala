

```python
import pandas as pd
import numpy as np
import datetime
from datetime import date
from pandas.io.data import DataReader
from pandas.io import data, wb
```

    /Users/mclaren/anaconda3/lib/python3.5/site-packages/pandas/io/data.py:33: FutureWarning: 
    The pandas.io.data module is moved to a separate package (pandas-datareader) and will be removed from pandas in a future version.
    After installing the pandas-datareader package (https://github.com/pydata/pandas-datareader), you can change the import ``from pandas.io import data, wb`` to ``from pandas_datareader import data, wb``.
      FutureWarning)
    /Users/mclaren/anaconda3/lib/python3.5/site-packages/pandas/io/wb.py:19: FutureWarning: 
    The pandas.io.wb module is moved to a separate package (pandas-datareader) and will be removed from pandas in a future version.
    After installing the pandas-datareader package (https://github.com/pydata/pandas-datareader), you can change the import ``from pandas.io import data, wb`` to ``from pandas_datareader import data, wb``.
      FutureWarning)



```python
start = date(2015, 1, 1)

end = date.today()

start

```




    datetime.date(2015, 1, 1)




```python
stocks = ['AAPL', 'TSLA', 'IBM']
```


```python
df = DataReader(stocks, 'yahoo', start, end)
df
```




    <class 'pandas.core.panel.Panel'>
    Dimensions: 6 (items) x 518 (major_axis) x 3 (minor_axis)
    Items axis: Open to Adj Close
    Major_axis axis: 2015-01-02 00:00:00 to 2017-01-23 00:00:00
    Minor_axis axis: AAPL to TSLA




```python
close = df['Adj Close']
close.tail(2)
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AAPL</th>
      <th>IBM</th>
      <th>TSLA</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2017-01-20</th>
      <td>120.000000</td>
      <td>170.550003</td>
      <td>244.729996</td>
    </tr>
    <tr>
      <th>2017-01-23</th>
      <td>120.080002</td>
      <td>171.029999</td>
      <td>248.919998</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
