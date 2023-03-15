### DataFrame
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
  
