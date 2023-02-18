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
        "phone_numbers":{"mobile": "+1 714 512 9752", "home": "+1 714 512 6601"},
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
        "phone_numbers": None,
        "is_customer": True,
        "amount_paid": 900.00,
        "cusomer_from": datetime.date(2021, 2, 14),
        "last_updated_ts": datetime.datetime(2021, 2, 18, 3, 33, 0)
    }
]
```

```
from pyspark.sql import Row
```

```
df = spark.createDataFrame(Row(**user for user in users))
```

```
df.show()
```

```
df.printSchema()
```

```
df.select('id','phone_numbers').show(truncate=False)
```

```
df.columns
```

```
df.dtypes
```

```
from pyspark.sql.functions import col
```

```
df.select('id', col('phone_numbers')['mobile']).show()
```

```
df.select('id', \
    col('phone_numbers')['mobile']).alias('mobile'), \
    col('phone_numbers')['home']).alias('home'). \
    show()
```

```
from pyspark.sql.functions import explode
```

```
df. \
    select(
        'id',
        explode('phone_numbers')
    ).show()
```

```
from pyspark.sql.functions import explode_outer
```

```
df. \
    select(
        'id',
        explode_outer('phone_numbers')
    ).show()
```

```
df. \
    select('*', explode('phone_numbers')). \
    withColumnsRenamed('key', 'phone_type'). \
    withColumnsRenamed('value', 'phone_number'). \
    drop('phone_number'). \
    show()
```