# GitLab

## Build a self-hosted GitLab

Get Docker CE

[Instructions for Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

Download docker-compose

[Instructions](https://docs.docker.com/compose/install/)

Create docker-compose.yml and replace {host_ip} to the actual IP address of the server.

```yml
version: "3.6" 
services:
  web:
    image: 'gitlab/gitlab-ce'
    container_name: 'gitlab'
    restart: always
    hostname: {host_ip}
    environment:
      GITLAB_OMNIBUS_CONFIG: |
        external_url 'http://{host_ip}:8081'
    networks:
      - gitlab-network
    ports:
      - '80:80'
      - '443:443'
      - '8081:8081'
      - '22:22'
    volumes:
      - '/srv/gitlab/config:/etc/gitlab'
      - '/srv/gitlab/logs:/var/log/gitlab'
      - '/srv/gitlab/data:/var/opt/gitlab'

networks:
  gitlab-network:
    name: gitlab-network
```

Start GitLab

```
docker-compose up --build --abort-on-container-exit
```

Given username is "root".

## References

1. [How to use Docker to build a Self-Host GitLab and GitLab Runner](https://medium.com/@rukeith/how-to-use-docker-to-build-a-self-host-gitlab-and-gitlab-runner-781981dc4d03)
