# Docker installation

## Ubuntu 18.04

### Docker Community Edition

[Script](https://github.com/Shaowen310/scripts/blob/master/ubuntu/bash/install-docker-ce.sh)

1. Remove any older installations of Docker that may be on the system

```
sudo apt remove docker docker-engine docker.io
```

2. Add Docker’s repository

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

3. Add Docker’s GPG key:

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

4. Add the stable Docker repository

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

5. Install Docker CE

```
sudo apt update
sudo apt install docker-ce
```

6. Get rid of sudo (takes effect after user logging out)

```
sudo usermod -aG docker $USER
```

7. Check that the installation was successful

```
docker run hello-world
```

## References

1. [Offical Document: Get Docker Engine - Community for Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
