# LokiGuide
What? Why? Where to? How to of LOKI Log aggregation tool

**How to run LOKI?**\
`docker rm <containerid>`
`docker run --name loki -d -v $(pwd):/mnt/config -p 3100:3100 grafana/loki:2.7.4 -config.file=/mnt/config/loki-config.yaml`

`docker rm <containerid>`
`docker run --name promtail -d -v $(pwd):/mnt/config -v /var/log:/var/log --link loki grafana/promtail:2.7.4 -config.file=/mnt/config/promtail-config.yaml`


# Questions
what is LOKI?\
Why LOKI?\
