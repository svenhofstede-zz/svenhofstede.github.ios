---
title: Pandas Cheatsheet
published: true
tags:
- Python
---

This, over time, will contain various code snippets that I come across and find useful. For now it's pretty limited :)

## Dataframes

Count the number of empty values in all columns of a given Dataframe.

```python
def missing_values_table(df): 
        mis_val = df.isnull().sum()
        mis_val_percent = 100 * df.isnull().sum()/len(df)
        mis_val_table = pd.concat([mis_val, mis_val_percent], axis=1)
        mis_val_table_ren_columns = mis_val_table.rename(
        columns = {0 : 'Missing Values', 1 : '% of Total Values'})
        return mis_val_table_ren_columns 
```