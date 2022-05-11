# Create Bridge network in Docker for Windows Container
### Stop Docker Service
```
Stop-Service Docker
```
### Open C:\ProgramData\Docker\config\daemon.json
```
  {
   “bridge” : “none”
  }
```
### Start Docker Service
```
Start-service Docker
```
### Create Transparent Network
```
docker network create -d transparent external
```
### list docker network
```
docker network ls
```
### Attach network to specific Docker Container
```
docker network connect external <containerName>
```
