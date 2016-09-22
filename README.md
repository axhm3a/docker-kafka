Kafka in Docker
===

This repository provides everything you need to run Kafka in Docker.

For convenience also contains a packaged proxy that can be used to get data from
a legacy Kafka 7 cluster into a dockerized Kafka 8.

Why?
---
The main hurdle of running Kafka in Docker is that it depends on Zookeeper.
Compared to other Kafka docker images, this one runs both Zookeeper and Kafka
in the same container. This means:

* No dependency on an external Zookeeper host, or linking to another container
* Zookeeper and Kafka are configured to work together out of the box

Run
---

```bash
docker run --net=host --env ADVERTISED_HOST=TYPE_YOUR_IP_HERE --env ADVERTISED_PORT=9092 --env KAFKA_ADVERTISED_HOST_NAME=localhost axhm3a/kafka
```

In the box
---
* **axhm3a/kafka**

  The docker image with both Kafka and Zookeeper. Built from the `kafka`
  directory.

Public Builds
---

https://hub.docker.com/r/axhm3a/kafka/

Build from Source
---

    docker build -t axhm3a/kafka kafka/

Todo
---

* Not particularily optimzed for startup time.
* Better docs

