# LokiGuide
What? Why? Where to? How to of LOKI Log aggregation tool

**Installation**
```
wget https://raw.githubusercontent.com/grafana/loki/v2.7.4/cmd/loki/loki-local-config.yaml -O loki-config.yaml
docker run --name loki -d -v $(pwd):/mnt/config -p 3100:3100 grafana/loki:2.7.4 -config.file=/mnt/config/loki-config.yaml
wget https://raw.githubusercontent.com/grafana/loki/v2.7.4/clients/cmd/promtail/promtail-docker-config.yaml -O promtail-config.yaml
docker run --name promtail -d -v $(pwd):/mnt/config -v /var/log:/var/log --link loki grafana/promtail:2.7.4 -config.file=/mnt/config/promtail-config.yaml
```

**How to run LOKI?**
```
docker rm <containerid>
docker run --name loki -d -v $(pwd):/mnt/config -p 3100:3100 grafana/loki:2.7.4 -config.file=/mnt/config/loki-config.yaml

docker rm <containerid>
docker run --name promtail -d -v $(pwd):/mnt/config -v /var/log:/var/log --link loki grafana/promtail:2.7.4 -config.file=/mnt/config/promtail-config.yaml
```

**Stop all running docker containers**
```
sudo docker rm -f $(docker ps -a -q)
```

# Questions
what is LOKI?\
Why LOKI?
