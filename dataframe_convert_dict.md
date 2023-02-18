```
_list = [
    {"user_id": 1, "user_name": 'Scott'},
    {"user_id": 2, "user_name": 'Donald'},
    {"user_id": 3, "user_name": 'Mickey'},
    {"user_id": 4, "user_name": 'Elvis}
    ]
```

```
spark.createDataFrame(_list, 'user_id int' 'user_name string')
```

```
from pyspark.sql import Row
```

```
user_row = [Row(**user) for user in _list]
```

```
spark.createDataFrame(user_row, 'user_id int', 'user_name string')
```
