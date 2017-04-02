# Contains

* Oracle JDK 8.121
* sbt 0.13.13 with dependencies
* Alpine Linux 3.5.2

# Usage 

You can run the default sbt command simply:

```
 docker run \
   thothbot/alpine-sbt sbt sbt-version
```

This image is configured with a workdir ```/app```, so to build your project you have to mount a volume for your sources and another at ```/root/.ivy2``` to hold the ivy cache artifacts :

```
docker run -ti --rm \
   -v "/path/to/your/app:/app:rw" \
   -v "/path/to/your/.ivy2":/root/.ivy2 \
   thothbot/alpine-sbt sbt clean compile
```
