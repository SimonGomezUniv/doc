# Monitoring your applications


## step 1 : install grafana 

we are going to create a dockercompose file for these monitoring solution

add grafana in your dockercompose file :

```  
grafana:
    image: grafana/grafana
    container_name: grafana
    ports:
      - 3000:3000
    restart: unless-stopped
    networks:
      - monitor-net
```  

check that grafana is working by connecting on localhost:3000, default password should be admin/admin


## step 2 : install prometheus


### add prometheus to your dockercompose

add prometheus in your dockercompose file :

```
  prometheus:
    image: prom/prometheus
    container_name: prometheus
    volumes:
      - ./prometheus/:/etc/prometheus/
    restart: unless-stopped
    command:
      - '--config.file=/etc/prometheus/prometheus.yml'
    expose:
      - 9090
    ports:
      - 9090:9090
    networks:
      - monitor-net
 ```
 
 
### configure prometheus


create a file prometheus.yml in a prometheus directory

```
global:
  scrape_interval: 1m

scrape_configs:
  - job_name: "prometheus"
    scrape_interval: 1m
    static_configs:
    - targets: ["localhost:9090"]

```
 
 - run your dockercompose
 - connect to your grafana
 - add the prometheus instance as a datasource (You should see "Data source is working" in your grafana interface

 
 ## step 3 : add the node exporter to monitor your system
 
 
 add a node exporter instance in your dockercompose file 
 
 ```
   node-exporter:
    image: prom/node-exporter:latest
    container_name: node-exporter
    restart: unless-stopped
    volumes:
      - /proc:/host/proc:ro
      - /sys:/host/sys:ro
      - /:/rootfs:ro
    command:
      - '--path.procfs=/host/proc'
      - '--path.rootfs=/rootfs'
      - '--path.sysfs=/host/sys'
      - '--collector.filesystem.mount-points-exclude=^/(sys|proc|dev|host|etc)($$|/)'
    expose:
      - 9100
    ports:
      - 9100:9100
    networks:
      - monitor-net
   ```
   
   Connect to http://localhost:9100/metrics and have a look to all data gathered
   
   Add the node exporter to your prometheus configuration
   
  ```
     - job_name: "node-exporter"
    static_configs:
    - targets: ["node-exporter:9100"]
  ```
  
  Restart your docker compose
  try graphing the prometheus collect : 
  - new dashboard
  - new panel
  - use your prometheus datasource
  - graphe :  promhttp_metric_handler_requests_total
  
  
 
 
