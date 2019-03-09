## RDS Statistics

RDS has a statistics tree rooted at http.<stat_prefix>.rds.<route_config_name>..

https://www.envoyproxy.io/docs/envoy/latest/configuration/http_conn_man/rds

http://localhost:8001/stats

Example output: 

~~~~
http.ingress_http.rds.local_route.config_reload: 1
http.ingress_http.rds.local_route.update_attempt: 2
http.ingress_http.rds.local_route.update_empty: 0
http.ingress_http.rds.local_route.update_failure: 1
http.ingress_http.rds.local_route.update_rejected: 0
http.ingress_http.rds.local_route.update_success: 1
http.ingress_http.rds.local_route.version: 7148434200721666028
~~~~

Or, in Prometheus format: http://localhost:8001/stats/prometheus