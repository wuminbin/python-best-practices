# get top n lines of a large file
```python
import itertools
nrows = 1000
with open('fn') as fr:
    for line in itertools.islice(fr, nrows):
        pass
```

```python
# remember to sort before using itertools.groupby!
import itertools
l = [(1, 'a'), (1, 'g'), (5, 'b'), (2, 'd'), (5, 'k')]
for k, g in itertools.groupby(sorted(l), key=lambda x: x[0]):
    print(k, list(g))

# flatten list
list(itertools.chain.from_iterable([[1, 3], [5], ['a', 'c'], 'bdg']))
```