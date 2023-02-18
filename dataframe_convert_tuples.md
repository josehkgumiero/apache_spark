```
_list = [(1, 'Scott'), (2, 'Donald'), (3, 'Mickey'), (4, 'Elvis)]
```

```
spark.createDataFrame(_list, 'user_id int' 'user_name string')
```

```
from pyspark.sql import Row
```

```
user_row = [Row(user) for user in _list]
```

```
spark.createDataFrame(user_row, 'user_id int', 'user_name string')
```
