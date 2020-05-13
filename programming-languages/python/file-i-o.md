# Python File I/O

## String I/O

```python
with open("example.json") as json_file:
    json_str = json_file.read()
```

### Open

### File pointer

## Data I/O

### JSON

#### json library

[Doc](https://docs.python.org/3/library/json.html)

```python
import json
data_obj = json.loads('["foo", {"bar":["baz", null, 1.0, 2]}]')
json_str = json.dumps(data_obj)
json.dump(data_obj, io)
```

#### pandas library

For table-structured data

`pandas.read_json`

[Doc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_json.html)

`pandas.DataFrame.to_json`

[Doc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_json.html)

