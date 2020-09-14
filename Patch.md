### 

/usr/local/lib/pypy3.6/dist-packages/pymysql/converters.py:43

```python

def escape_sequence(val, charset, mapping=None):
    n = []
    for item in val:
        quoted = escape_item(item, charset, mapping)
        n.append(quoted)
    return "(" + ",".join(n) + ")"

To:

def escape_sequence(val, charset, mapping=None):
    n = []
    for item in val:
        quoted = escape_item(item, charset, mapping)
        n.append(str(quoted))
    return "(" + ",".join(n) + ")"
```
