# Pandas

## I/O

```python
pd.read_csv()
pd.read_json()
```

### dtype

| Pandas dtype | Python type | NumPy type | Description |
| :--- | :--- | :--- | :--- |
| object | str | str\_, string\_, unicode\_ |  |
| int64 | int | int\_, int8, int16, int32, int64, uint8, uint16,uint32,uint64 |  |
| float64 | float | float\_, float16, float32, float64 |  |
| bool | bool | bool\_ |  |
| datetime64 | -- | datetime64\[ns\] |  |
| timedelta\[ns\] | -- | -- | Difference between two datetimes |
| category | -- | -- | Finite list of text values |

## SQL

### select

`loc` selects rows by indexes, columns by labels

`iloc` selects rows by indexes, columns by positions

```python
df.loc[0:3, ['name', 'gender']]
df.loc[0:3, 'name':'age']
df.iloc[0:3, [0, 3]]
df.iloc[0:3, 0:3]
```

`at` selects one element using row index and column label

`iat` selects one element using row index and column position

```python
df.at[3, 'name']
df.iat[3, 0]
```

`ix` supports both labels and positions

```python
df.ix[0:3, [0, 3]]
df.ix[0:3, ['name', 'gender']]
```

Select rows or columns only

```python
# rows by indexes
df[0:3]
# columns by labels
df[['name','gender']]
```

Select notnull

```python
df.nonzero()
```

Boolean index to position index

```python
boolean_index.to_numpy().nonzero()
```

### where

Use the pattern `df[df[column] boolean expr]`

```python
df[df['gender'] == 'Male']
df[df['total_bill'] > 20]

# and
df[(df['gender'] == 'Male') & (df['total_bill'] > 20)]
# or
df[(df['gender'] == 'Male') | (df['total_bill'] > 20)]
# not
df[-(df['gender'] == 'Male')]
# in
df[df['total_bill'].isin([21.01, 23.68, 24.59])]
# string function
df = df[(-df['app'].isin(sys_app)) & (-df.app.str.contains('^\d+$'))]
```

Use `query`

```python
df.query('col_name == @var_name')
```

Note that `query` is more efficient because it does not need to generate boolean index array.

### distinct

`df.drop_duplicates()`

### count \(length\)

`df.shape[0]` or `len(df)`

### group by

`df.groupby('key').size()` or `df['key'].count_values()`

Multiple aggregation functions

```python
df.groupby().agg({'gender': pd.Series.nunique, 'tip': np.max, 'total_bill': np.sum})
```

### order

```python
df.sort_values(['total_bill', 'tip'], ascending=[False, True])
```

### drop

Drop columns

```python
df.drop(['role'], axis=1)
df.drop(df.columns[[0]], axis=1)
```

## References

1. [【Python 实战】Pandas：让你像写 SQL 一样做数据分析（一）](https://www.cnblogs.com/en-heng/p/5630849.html)

