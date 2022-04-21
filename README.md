# A simple key-value database in python.

# Usage:
```python
import pykvdb
import os

# set db file path, default is './pykvdb'
dbpath = os.path.join(os.path.split(os.path.realpath(__file__))[0], 'pykvdb')
# set db file maxsize, default is 10M
dbsize = 10 * 1024 * 1024

with pykvdb.KVDB(path=kvpath, size=dbsize) as kv:
    kv.set('a', 'test')

# get value
with KVDB(path=kvpath, size=dbsize) as kv:
    print(kv.get('a'))

# scan all key-value
with KVDB(path=kvpath, size=dbsize) as kv:
    cur = kv.cursor()
    for k, v in cur:
        print(k.decode(), v.decode())
```