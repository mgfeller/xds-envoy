This repository illustrates the use of dynamic routing configuration (RDS) of the Envoy proxy.

It accompanies a forthcoming blog post.

It is based on the front proxy example code from the [Envoy proxy repository](https://github.com/envoyproxy/envoy), documented in the  
[envoy docs](https://www.envoyproxy.io/docs/envoy/v1.9.0/start/sandboxes/front_proxy.html). 

Version 1.9.0 of Envoy is used here, rather than latest. 

Assuming that Docker as well as Docker Compose are installed, run the example using


```
cd front-proxy
docker-compose up --build -d
curl localhost:8000/service/1
curl localhost:8000/service/2
docker-compose down
```

RDS has a statistics tree rooted at http.<stat_prefix>.rds.<route_config_name>, see
https://www.envoyproxy.io/docs/envoy/v1.9.0/configuration/http_conn_man/rds

The statistics is available at http://localhost:8001/stats, in Prometheus format at http://localhost:8001/stats/prometheus.

Filebeat is installed and configured in the front proxy Docker image to send the logs from Envoy to a logstash instance.