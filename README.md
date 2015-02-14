# Container Exporter
[Prometheus](https://github.com/prometheus/prometheus) exporter exposing container metrics.

The container-exporter requests a list of containers running on the host by talking to a 
container manager. Right now, Docker as container manager is supported.
It then gathers various container metrics by using [libcontainer](https://github.com/docker/libcontainer)
and exposes them for prometheus consumption.

## Run it as container

    docker run -p 9104:9104 -v /sys/fs/cgroup:/cgroup \
               -v /var/run/docker.sock:/var/run/docker.sock prom/container-exporter
