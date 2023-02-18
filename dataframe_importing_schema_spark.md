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
from pyspark.sql.types import *
```

```
users_schema = StructType(
    [
        StructField('id', IntegerType()),
        StructField('first_name', StringType()),
        StructField('last_name', StringType()),
        StructField('email', StringType()),
        StructField('is_customer', IntegerType()),
        StructField('amount_paid', FloatType()),
        StructField('customer_from', DateType()),
        StructField('last_updated_ts', TimestampType())
    ]
)
```

```
spark.createDataFrame(users, schema = users_schema)
```