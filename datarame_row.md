```
_list = [(21, 'ruan'), (23, 'ronaldo'), (41, 'roberto'), (32, 'deyverson') ]
type(_list)
df = spark.createDataFrame(_list, 'age int', 'name string')
```

```
df.show()
```

```
df.collect()
type(df.collect()
```

```
from pyspark.sql import Row
```

```
help(Row)
```

```
r = Row('alice', 11)
print(r)
```

```
row2 = Row(name='Alice', age=11)
print(row2)
print(row2.name)
print(row2['name'])
```
