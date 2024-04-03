# failed to initialize NVML: Unknown Error In Docker Container
![image](https://github.com/kalpeshpatelce/docker/assets/13175900/7327a562-5929-498e-a31b-e9b984cccb08)
## When I do nvidia-smi in docker machine. I see this msg
"Failed to initialize NVML: Unknown Error"
## Stop the Docker Service
```
sudo systemctl stop docker.servie
```
## open the /etc/docker/daemon.json 
```
sudo nano /etc/docker/daemon.json 
```
## Then, within the file, add this parameter setting.
```
"exec-opts": ["native.cgroupdriver=cgroupfs"]  
```
## Reload Daemon
```
sudo systemctl daemon-reload
```
## Restart Docker Service
```
sudo systemctl start docker.servie
```
