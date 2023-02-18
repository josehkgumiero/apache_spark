```
help(spark.createDataFrame)
```

```
_list = []
spark.createDataFrame(_list)
```

```
_list = []
spark.createDataFrame(_list, 'int')
```

```
from pyspark.sql.types import IntegerType
```

```
spark.createDataFrame(_list, IntegerType())
```

```
_list = []
spark.createDataFrame(_list, 'str')
```

```
from pyspark.sql.types import StringType
```

```
spark.createDataFrame(_list, StringType())
```

```
_list = [(21, 'ruan'), (23, 'ronaldo'), (41, 'roberto'), (32, 'deyverson') ]
type(_list)
spark.createDataFrame(_list, 'age int', 'name string')
```