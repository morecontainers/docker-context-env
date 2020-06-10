# Docker Context Env

Example usage:

```
⬢[om@toolbox ~]$ docker context ls
NAME                DESCRIPTION                               DOCKER ENDPOINT                          KUBERNETES ENDPOINT   ORCHESTRATOR
default *           Current DOCKER_HOST based configuration   unix:///var/run/docker.sock                                    swarm
local                                                         tcp://localhost:2376                                           swarm
⬢[om@toolbox ~]$ docker-context-env local
export DOCKER_HOST=tcp://localhost:2376
export DOCKER_TLS_VERIFY=1
export DOCKER_CERT_PATH=/var/home/om/.docker/contexts/tls/25bf8e1a2393f1108d37029b3df5593236c755742ec93465bbafa9b290bddcf6/docker
⬢[om@toolbox ~]$ eval $(docker-context-env local)
⬢[om@toolbox ~]$ echo $DOCKER_HOST
tcp://localhost:2376
⬢[om@toolbox ~]$ docker version
Client: Docker Engine - Community
 Version:           19.03.11
 API version:       1.40
 Go version:        go1.13.10
 Git commit:        42e35e61f3
 Built:             Mon Jun  1 09:09:53 2020
 OS/Arch:           linux/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          19.03.8
  API version:      1.40 (minimum version 1.12)
  Go version:       go1.12.17
  Git commit:       afacb8b7f0
  Built:            Wed Mar 11 01:30:32 2020
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          v1.2.13
  GitCommit:        7ad184331fa3e55e52b890ea95e65ba581ae3429
 runc:
  Version:          1.0.0-rc10
  GitCommit:        dc9208a3303feef5b3839f4323d9beb36df0a9dd
 docker-init:
  Version:          0.18.0
  GitCommit:        fec3683
⬢[om@toolbox ~]$ 
```
