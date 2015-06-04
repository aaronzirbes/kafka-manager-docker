Kafka Manager Docker Container
==============================

A docker image for [Kafka Manager](https://github.com/yahoo/kafka-manager)

Base Docker Image
-----------------

* [dockerfile/java:oracle-java8](https://registry.hub.docker.com/u/dockerfile/java)

Environment Variables
---------------------

* `ZK_HOSTS` default: *zookeeper.service.consul:2181*
* `KM_BINTRAY_REPO` default: *aaronzirbes/maven*
* `KM_VERSION` default: *1.2.4*

Running
-------

    docker run -it --rm  -p 9000:9000 -e ZK_HOSTS="zookeeper.example.com:2181" -e APPLICATION_SECRET=S3cret aaronzirbes/kafka-manager

The config dir is located at `/usr/local/kafka-manager-1.2.4/conf`, so you can override locally via:

    docker run [...] -v /your/local/confdir:/usr/local/kafka-manager-1.2.4/conf [...]

Only 1.2.4 is available until [this](https://github.com/yahoo/kafka-manager/issues/79) is resolved, as 
I'm pulling from my [own Bintray repo](https://bintray.com/aaronzirbes/maven/kafka-manager/view).
