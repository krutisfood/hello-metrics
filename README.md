# Hello Metrics Lightning Talk

### incomplete Commands to get running

```
  # git clone https://github.com/tutumcloud/tutum-docker-influxdb
  docker run -d -p 8083:8083 -p 8086:8086 -e PRE_CREATE_DB="db1" --expose 8090 --expose 8099 tutum/influxdb
  # Note the ip address *should* be determined based on this line but may not be...
  docker run -d -p 8082:80 \
     -e INFLUXDB_HOST=$(ifconfig eth0 2>/dev/null|awk '/inet addr:/ {print $2}'|sed 's/addr://') \
     -e INFLUXDB_PORT=8086 \
     -e INFLUXDB_NAME=krut \
     -e INFLUXDB_USER=root \
     -e INFLUXDB_PASS=root \
     -e INFLUXDB_IS_GRAFANADB=true \
     tutum/grafana

```
Now open http://localhost:8082

### Links
* Repos used
  https://github.com/tutumcloud/tutum-docker-influxdb
  https://github.com/tutumcloud/tutum-docker-grafana 
  https://github.com/novaquark/sysinfo_influxdb.git (develop branch for latest version)

## License

NOTE: Refer to invidual repositories for respective licensing details.

Unless otherwise stated code here-in is MIT licensed

Copyright (C) 2015 Kurt Gardiner
