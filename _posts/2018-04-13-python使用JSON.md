---
title: Python使用JSON
date: 2018-04-13 15:42:20
categories:
- Skills
---

&emsp;&emsp;在Python中，JSON模块提供了一种很简单的方式来编码和解码JSON数据。该库解析JSON后将其转为Python字典或者列表，也可以将Python字典或列表转换为JSON字符串。其中两个主要的函数是json.dumps()和json.loads()。

### 数据转换成JSON格式
```python
import json
data = {
    'name' : 'ACME',
    'shares' : 100,
    'price' : 542.23
}
json_str = json.dumps(data)
```

### 解析JSON格式数据
```python
##json_string = '{"first_name": "Guido", "last_name":"Rossum"}'
import json
parsed_json = json.loads(json_string)
print(parsed_json['first_name'])##像使用dict一样读取数据，输出"Guido"
```

### 结合文件的JSON操作
```python
# Writing JSON data
with open('data.json', 'w') as f:
    json.dump(data, f)
```

```python
# Reading data back
with open('data.json', 'r') as f:
    data = json.load(f)
```
