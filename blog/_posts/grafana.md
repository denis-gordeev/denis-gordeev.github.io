I have not found a good introduction on writing data into Grafana and InfluxDB with http, so I write my own.

First you need to create the database.

```
        r = requests.post(
            "http://10.8.0.1:8086/query",
            params={"q": "CREATE DATABASE {}".format(db_name)},
```

Then you need to write the data

```

        r = requests.post(
            "http://10.8.0.1:8086/api/v2/write?bucket={}".format(db_name),
            data="latency,service={} value={}".format(service, latency),
        )
```

