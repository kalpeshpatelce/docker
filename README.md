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
### Connect to Container
```
docker exec -it <containerName> powershell
```
### Get IP Address of Existing Container

## Get-NetAdapter

![image](https://user-images.githubusercontent.com/13175900/167824520-6e73eeda-113c-4669-967f-5201ff4360fe.png)
Get ifindex of Adapter from Above Image

### Get interfaceAlise from below command

Get-NetIPConfigurtion

![image](https://user-images.githubusercontent.com/13175900/167825369-2be133f6-9ab7-4d81-bafa-db1dede677e5.png)

### Powershell Command for seting Static IP Address

```
syntax
To Assign IP Address
New-NetIPAddress -InterfaceIndex 12 -IPAddress xxx.xxx.xxx.xxx -PrefixLength 24 -DefaultGateway xxx.xxx.xxx.xxx

To Set DNS Address
Set-DnsClientServerAddress -InterfaceIndex "IndexNo" -ServerAddresses "xxx.xxx.xxx.xxx , xxx.xxx.xxx.xxx"

To Remove IP Address
Remove-NetIPAddress -IPAddress xxx.xxx.xxx.xxx -DefaultGateway xxx.xxx.xxx.xxx

```





