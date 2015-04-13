# Hello Metrics Lightning Talk

### Awe inspiring (?) live demo

```
  # Setup InfluxDB
  # git clone https://github.com/tutumcloud/tutum-docker-influxdb
  docker run -d -p 8083:8083 -p 8086:8086 -e PRE_CREATE_DB="nubuntu" --expose 8090 --expose 8099 tutum/influxdb

  # Setup Graphana reading from InfluxDB
  $local_ip_i_have_entered_manually=<something you have to do manually sorry>
  docker run -d -p 8082:80 \
     -e INFLUXDB_HOST=$local_ip_i_have_entered_manually \
     -e INFLUXDB_PORT=8086 \
     -e INFLUXDB_NAME=nubuntu \
     -e INFLUXDB_USER=root \
     -e INFLUXDB_PASS=root \
     -e INFLUXDB_IS_GRAFANADB=true \
     tutum/grafana

  # Quick dirty ruby app to publish some stats
  git clone https://github.com/krutisfood/quick-dirty-stats.git
  cd quick-dirty-stats
  bundle install
  ./machine_stats.sh

  # Open Graphana and create a graph against the machine series in database nubuntu
  http://localhost:8082

```

To access local InfluxDB open
```
  http://localhost:8082
```

To access local Graphana
```
  http://localhost:8082
```


### Links and thanks go to
* Repos used

  https://github.com/tutumcloud/tutum-docker-influxdb

  https://github.com/tutumcloud/tutum-docker-grafana 

  https://github.com/krutisfood/quick-dirty-stats.git

  https://github.com/krutisfood/hello-metrics.git


## License

NOTE: Refer to invidual repositories for respective licensing details.

Unless otherwise stated code here-in is MIT licensed

Copyright (C) 2015 Kurt Gardiner
