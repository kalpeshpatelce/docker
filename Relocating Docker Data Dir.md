# Relocating the Docker root directory

To relocate the Docker root directory, complete the following steps as root or a user with “sudo all” authority:

## 1. Stop the Docker services:
```
sudo systemctl stop docker
sudo systemctl stop docker.socket
sudo systemctl stop containerd
```
## 2. Create the necessary directory structure into which to move Docker root by running the following command. This directory structure must reside on a file system with at least 50 GB free disk space. Significantly more disk space might be required depending on your daily ingestion volumes and data retention policy.
```
sudo mkdir -p /data/docker
```
## 3. Move Docker root to the new directory structure:
```
sudo mv /var/lib/docker /new_dir_structure
```
## 4. Edit the file /etc/docker/daemon.json. If the file does not exist, create the file by running the following command
```
sudo vim /etc/docker/daemon.json
```
## 5. Add the following information to this file:
```
{
  "data-root": "/data/docker"
}
```
## 6. After the /etc/docker/daemon.json file is saved and closed, restart the Docker services
```
sudo systemctl start docker.service
```
## 7. Verify the new Docker root location:
```
docker info -f '{{ .DockerRootDir}}'
```
