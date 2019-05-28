
# get char count
```python
# simple way
d = {}  # better than `d = dict()`
for c in 'abc':
    if c in d:
        d[c] += 1
    else:
        d[c] = 1

# better: using `get` method
d = {}
for c in 'abc':
    d[c] = d.get(c, 0) + 1

# best: using collections.Counter
from collections import Counter
ct = Counter('abc')
```

# get vaule chains of kvs by key
```python
data = [("p", 1), ("p", 2), ("p", 3),
        ("h", 1), ("h", 2), ("h", 3)]
# result = {'p': [1, 2, 3], 'h': [1, 2, 3]}
# simple way
result = {}  # better than `result = dict()`
for key, value in data:
    if key in result:
        result[key].append(value)
    else:
        result[key] = [value]
        
# using `get` method, not recommend here
result = {}
for key, value in data:
    result[key] = result.get(key, []) + [value]

# much better
result = {}
data = [("p", 1), ("p", 2), ("p", 3),
        ("h", 1), ("h", 2), ("h", 3)]
for key, value in data:
    result.setdefault(key, []).append(value)

# best for using dict
from collections import defaultdict
result = defaultdict(list)
data = [("p", 1), ("p", 2), ("p", 3),
        ("h", 1), ("h", 2), ("h", 3)]

for key, value in data:
    result[key].append(value)

# another best way: using itertools
import itertools
from operator import itemgetter
data = [("p", 1), ("p", 2), ("p", 3),
        ("h", 1), ("h", 2), ("h", 3)]
result = {}
gp = itertools.groupby(sorted(data), key=itemgetter(0))
for k, g in gp:
    result[k] = [x[1] for x in g]
```