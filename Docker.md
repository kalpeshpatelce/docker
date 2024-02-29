# How To Create Docker image from existing Running Container and push to Docker Hub

## List the existing Running Containers

```
docker ps
```
![image](https://github.com/kalpeshpatelce/docker/assets/13175900/6f856a28-df8f-404c-ad21-96db4a1a774f)

## we make Image from container is 56c7991cda4f show in figure
```
docker commit 56c7991cda4f kalpeshpatelce/ankit_gpu:1.1
```
![image](https://github.com/kalpeshpatelce/docker/assets/13175900/8c743616-dde1-4808-9b4d-4d1d909854d0)

## List Images the commit image
```
docker images
```
![image](https://github.com/kalpeshpatelce/docker/assets/13175900/c83d646f-0b8e-4e48-a2f7-51e0532607b0)

## To Upload Image to Docker hub Please Login
```
docker login
```
![image](https://github.com/kalpeshpatelce/docker/assets/13175900/a4a8c966-2486-4f80-8c3e-ab6b32071646)

## Run Push Command
```
 docker push kalpeshpatelce/ankit_gpu:1.1
```
![image](https://github.com/kalpeshpatelce/docker/assets/13175900/ee43e327-9518-4dea-9532-e0da0d7fe341)

## Uploaded Image on DockerHub
![image](https://github.com/kalpeshpatelce/docker/assets/13175900/bb7fdd19-b4f7-4127-b34c-4cf338ad4292)


