# Loud_ML
InfluxDB, Chronograf, &amp; Loud ML container configs and setup to make time series predictions with machine learning. 

````bash
docker network create --subnet=172.18.0.0/24 loudml2
````

````bash 
$INFLUXDB="/Users/super/work/learning/loudml/Loud_ML/influxdb"
````

```bash 
$LOUDMLTEL="/Users/super/work/learning/loudml/Loud_ML/LoudML2"
```

```bash 
docker run -p 8086:8086 --net loudml2 --ip 172.18.0.86  --name influxdb2 -v /Users/super/work/learning/loudml/Loud_ML/influxdb:/var/lib/influxdb -v /Users/super/work/learning/loudml/Loud_ML/LoudML2/influxdb.conf:/etc/influxdb/influxdb.conf:ro influxdb -config /etc/influxdb/influxdb.conf
```

```bash
docker run -p 8888:8888 --net loudml2 --ip 172.18.0.77 --name chrono2 -v /Users/super/work/learning/loudml/Loud_ML/LoudML2/chronograf:/var/lib/chronograf chronograf
```

````bash
docker run -ti -p 8077:8077 --net loudml2 --ip 172.18.0.88 --name loudml2 -v /Users/super/work/learning/loudml/Loud_ML/LoudML2:/var/lib/loudml:rw -v /Users/super/work/learning/loudml/Loud_ML/LoudML2/config.yml:/etc/loudml/config.yml:ro -v /Users/super/work/learning/loudml/Loud_ML/LoudML2/model.json:/etc/loudml/model.json:ro loudml/community
````
