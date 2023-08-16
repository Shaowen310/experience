# Docker installation

## Ubuntu 18.04

### Docker Community Edition

TL;DR See [Script](https://github.com/Shaowen310/scripts/blob/master/ubuntu/bash/install-docker-ce.sh)

1. Remove any older installations of Docker that may be on the system

```text
sudo apt remove docker docker-engine docker.io
```

1. Add Docker’s repository

```text
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

1. Add Docker’s GPG key:

```text
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

1. Add the stable Docker repository

```text
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

1. Install Docker CE

```text
sudo apt update
sudo apt install docker-ce
```

1. Get rid of sudo \(takes effect after user logging out\)

```text
sudo usermod -aG docker $USER
```

1. Check that the installation was successful

```text
docker run hello-world
```

## docker-compose

[https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)

## Docker for Non-root User

[https://www.thegeekdiary.com/run-docker-as-a-non-root-user/](https://www.thegeekdiary.com/run-docker-as-a-non-root-user/)

## References

1. [Offical Document: Get Docker Engine - Community for Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
2. [https://www.thegeekdiary.com/run-docker-as-a-non-root-user/](https://www.thegeekdiary.com/run-docker-as-a-non-root-user/)

