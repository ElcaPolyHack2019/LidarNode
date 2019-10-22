This project was created from the [Duckietown basic template](https://github.com/duckietown/template-basic)

# Instructions

## Build
Local:
```
docker build -t elcalan/lidarnode:latest-amd64 --build-arg ARCH=amd64 .
```

On Duckiebot:
```
docker -H DUCKIEBOT.local build -t elcalan/lidarnode:latest-arm32v7 --build-arg ARCH=arm32v7 .
```

## Run
Local:
```
docker run -it --rm --net host -v /dev/ydlidar:/dev/ydlidar --privileged --env ROS_MASTER_URI=http://DUCKIEBOT_IP:11311 --name lidarnode elcalan/lidarnode:latest-amd64
```

On Duckiebot:
```
docker -H DUCKIEBOT.local run -it -v /dev/ydlidar:/dev/ydlidar --privileged --rm --net=host elcalan/lidarnode:latest-arm32v7
```

## Push (to DockerHub)
```
docker push elcalan/lidarnode:latest-amd64
docker -H DUCKIEBOT.local push elcalan/lidarnode:latest-arm32v7
```
