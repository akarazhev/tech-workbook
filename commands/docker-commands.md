# Docker Commands

## docker build

Once your code is ready and the Dockerfile is written, all you have to do is create your image to contain your application.
The ’-t’ option allows you to define the name of your image:

```bash
docker build -t <image-name> . 
```

## docker run

Once the image is created, your code is ready to be launched:

```bash
docker run <image-name>
```

## docker image

List your images:

```bash
docker image ls
```

Delete a specific image:
```bash
docker image rm <image-name>
```

Delete all existing images:

```bash
docker image rm $(docker images -a -q)
```

## docker ps

List all existing containers (running and not running):

```bash
docker ps -a
```

## docker stop

Stop a specific container:

```bash
docker stop <container-name>
```

Stop all running containers:

```bash
docker stop $(docker ps -a -q)
```

## docker rm

Delete a specific container (only if stopped):

```bash
docker rm <container-name>
```

Delete all containers (only if stopped):

```bash
docker rm $(docker ps -a -q)
```

## docker logs

Display logs of a container:

```bash
docker logs <container-name>
```