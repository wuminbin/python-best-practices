# type hints from python 3.5
```python
from typing import *  # most used: List, Tuple, Dict
def process_list(a: List[str]) -> str:
    return ",".join(a)

def process_dict(d: Dict[str, any]) -> str:
    return  ";".join(d.keys())

def process_tuple():
    return 

# It's better to use an abstract collection type such as `Sequence` to annotate parameters
def return_list(s: Sequence[str]) -> List[str]:
    return sorted(s)

def return_dict(d: Mapping[str, any]) -> Dict[str, any]:
    res = {}
    for k, v in d.items():
        res[k] = v
    return res

```