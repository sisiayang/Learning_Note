## DataFrame
### 遍歷 Dataframe
* 按照row遍歷整個dataframe  
  可以進一步指定欄位(feature_name)
  ```python
  for idx, row in df.iterrows():
      print(idx)
      print(row[feature_name])
  ```
  
* 按照col遍歷整個dataframe  
  可以進一步指定row_index
  ```python
  for idx, col in df.iteritems():
      print(idx)  # output column name
      print(col[row_index])
  ```
  
---
### 判斷nan值
* 無法利用 == 判斷式直接判斷
  ```python
  # not working
  if(df.iloc[idx][feature] == np.nan){
      ...
  }
  ```
  原因是因為，np.nan實際上並不是空值，而是numpy.float64，基於numpy的pandas也相同  
  因此需要利用numpy或是pandas給定的function去做判斷  
  ```python
  # Work
  np.isna(df.iloc[idx][feature])

  pd.isna(df.iloc[idx][feature])

  pd.isnull(df.iloc[idx][feature])
  ```
