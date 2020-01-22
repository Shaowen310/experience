# Connecting to a Remote Docker Daemon

## Exposing TCP port 2375

This method is not secure, so don't use it in public network.

### 1. Install Docker

See [docker installation](https://github.com/Shaowen310/engineering/blob/master/docker/docker-installation.md).

### 2. Configure the Docker daemon in the VM to allow remote connections

#### Docker for Ubuntu

```
# These commands get run inside of your VM.

# Create the directory to store the configuration file.
sudo mkdir -p /etc/systemd/system/docker.service.d

# Create a new file to store the daemon options.
sudo nano /etc/systemd/system/docker.service.d/options.conf

# Now make it look like this and save the file when you're done:
[Service]
ExecStart=
ExecStart=/usr/bin/dockerd -H unix:// -H tcp://0.0.0.0:2375

# Reload the systemd daemon.
sudo systemctl daemon-reload

# Restart Docker.
sudo systemctl restart docker
```

#### Docker for Windows

![https://medium.com/@sebagomez/installing-the-docker-client-on-ubuntus-windows-subsystem-for-linux-612b392a44c4](https://miro.medium.com/max/832/1*6XwT-oT7cbw63UFHLjQPzA.png)

Picture from https://medium.com/@sebagomez/installing-the-docker-client-on-ubuntus-windows-subsystem-for-linux-612b392a44c4

### 3. Add DOCKER_HOST environment variable to `.profile`

```
export DOCKER_HOST=localhost:2375
```

## References

1. [Connecting to a Remote Docker Daemon](https://nickjanetakis.com/blog/docker-tip-73-connecting-to-a-remote-docker-daemon)
2. [Installing the Docker client on Windows Subsystem for Linux (Ubuntu)](https://medium.com/@sebagomez/installing-the-docker-client-on-ubuntus-windows-subsystem-for-linux-612b392a44c4)
