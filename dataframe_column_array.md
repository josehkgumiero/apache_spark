```
import datetime
```

```
users = [
    {
        "id": 1,
        "first_name": "Corrie",
        "last_name": "Van Den Oord",
        "email": "cvandenoord@etsy.com",
        "is_customer": True,
        "amount_paid": 1000.55,
        "cusomer_from": datetime.date(2021, 1, 15),
        "last_updated_ts": datetime.datetime(2021, 2, 10, 1, 15, 0)
    },
    {
        "id": 2,
        "first_name": "Nikolaus",
        "last_name": "Brewitt",
        "email": "nbrewitt@etsy.com",
        "is_customer": True,
        "amount_paid": 900.00,
        "cusomer_from": datetime.date(2021, 2, 14),
        "last_updated_ts": datetime.datetime(2021, 2, 18, 3, 33, 0)
    }
]
```

```
import pandas as pd
```

```
pd.DataFrame(users)
```

```
df = spark.createDataFrame(pd.DataFrame(users))
```

```
df.show()
```

```
df.printSchema()
```

```
df.select('id','email').show(truncate=False)
```

```
df.columns
```

```
df.dtypes
```

```
from pyspark.sql.functions import explode
```

```
df. \
    withColumn('email', explode('email')). \
    drop('email'). \
    show()
```

```
from pyspark.sql.functions import col
```

```
df. \
    select('id', col('email')[0].alias('address1'), col('email')[1].alias('address2')). \
    show()
```

```
df. \
    withColumn('email', explode_outer('email')). \
    drop('email'). \
    show()
```