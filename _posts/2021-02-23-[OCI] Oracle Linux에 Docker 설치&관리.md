---
category: [ OCI ]
---

<p><strong>1. Yum Repository Update</strong></p>
<div class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>[root@docker-server ~]# mv ./public-yum-ol7.repo ./public-yum-ol7.repo_org1
[root@docker-server ~]# mkdir yum.repos.d
[root@docker-server ~]# cd yum.repos.d
[root@docker-server ~]# wget http://yum.oracle.com/public-yum-ol7.repo
[root@docker-server ~]# cat /etc/yum.repos.d/public-yum-ol7.repo
</code></pre>
</div>
</div>
<p>&nbsp;</p>
<p><strong>2. Docker 설치 </strong></p>
<div class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>[root@docker-server ~]# yum install -y docker-engine
Loaded plugins: langpacks, ulninfo
ol7_MySQL80                                                       | 2.8 kB  00:00:00
ol7_UEKR6                                                         | 2.8 kB  00:00:00
ol7_addons                                                        | 2.8 kB  00:00:00
ol7_ksplice                                                       | 2.8 kB  00:00:00
ol7_latest                                                        | 3.4 kB  00:00:00
ol7_oci_included                                                  | 2.9 kB  00:00:00
ol7_optional_latest                                               | 2.8 kB  00:00:00
ol7_software_collections                                          | 2.8 kB  00:00:00
Resolving Dependencies
--> Running transaction check
---> Package docker-engine.x86_64 0:19.03.11.ol-8.el7 will be installed
--> Processing Dependency: container-selinux >= 2:2.77 for package: docker-engine-19.03.11.ol-8.el7.x86_64
--> Processing Dependency: runc for package: docker-engine-19.03.11.ol-8.el7.x86_64
--> Processing Dependency: docker-cli for package: docker-engine-19.03.11.ol-8.el7.x86_64
--> Processing Dependency: containerd for package: docker-engine-19.03.11.ol-8.el7.x86_64
--> Running transaction check
---> Package container-selinux.noarch 2:2.107-3.el7 will be installed
---> Package containerd.x86_64 0:1.3.9-2.el7 will be installed
---> Package docker-cli.x86_64 0:19.03.11.ol-8.el7 will be installed
---> Package runc.x86_64 0:1.0.0-19.rc5.git4bb1fe4.0.4.el7 will be installed
--> Processing Dependency: criu for package: runc-1.0.0-19.rc5.git4bb1fe4.0.4.el7.x86_64
--> Running transaction check
---> Package criu.x86_64 0:3.12-2.el7 will be installed
--> Processing Dependency: libprotobuf-c.so.1(LIBPROTOBUF_C_1.0.0)(64bit) for package: criu-3.12-2.el7.x86_64
--> Processing Dependency: libprotobuf-c.so.1()(64bit) for package: criu-3.12-2.el7.x86_64
--> Processing Dependency: libnet.so.1()(64bit) for package: criu-3.12-2.el7.x86_64
--> Running transaction check
---> Package libnet.x86_64 0:1.1.6-7.el7 will be installed
---> Package protobuf-c.x86_64 0:1.0.2-3.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

======================================================================================================
 Package                       Arch      Version                           Repository        Size
======================================================================================================
Installing:
 docker-engine                 x86_64    19.03.11.ol-8.el7                 ol7_addons        21 M
Installing for dependencies:
 container-selinux             noarch    2:2.107-3.el7                     ol7_addons        39 k
 containerd                    x86_64    1.3.9-2.el7                       ol7_addons        27 M
 criu                          x86_64    3.12-2.el7                        ol7_latest       452 k
 docker-cli                    x86_64    19.03.11.ol-8.el7                 ol7_addons        34 M
 libnet                        x86_64    1.1.6-7.el7                       ol7_latest        57 k
 protobuf-c                    x86_64    1.0.2-3.el7                       ol7_latest        27 k
 runc                          x86_64    1.0.0-19.rc5.git4bb1fe4.0.4.el7   ol7_addons       1.9 M

Transaction Summary
=======================================================================================================
Install  1 Package (+7 Dependent packages)

Total download size: 85 M
Installed size: 347 M
Downloading packages:
(1/8): container-selinux-2.107-3.el7.noarch.rpm                                     |  39 kB  00:00:00
(2/8): criu-3.12-2.el7.x86_64.rpm                                                   | 452 kB  00:00:01
(3/8): containerd-1.3.9-2.el7.x86_64.rpm                                            |  27 MB  00:00:01
(4/8): docker-cli-19.03.11.ol-8.el7.x86_64.rpm                                      |  34 MB  00:00:01
(5/8): runc-1.0.0-19.rc5.git4bb1fe4.0.4.el7.x86_64.rpm                              | 1.9 MB  00:00:00
(6/8): docker-engine-19.03.11.ol-8.el7.x86_64.rpm                                   |  21 MB  00:00:01
(7/8): protobuf-c-1.0.2-3.el7.x86_64.rpm                                            |  27 kB  00:00:01
(8/8): libnet-1.1.6-7.el7.x86_64.rpm                                                |  57 kB  00:00:02
--------------------------------------------------------------------------------------------------------
Total                                                                       21 MB/s |  85 MB  00:00:03
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : 2:container-selinux-2.107-3.el7.noarch                                         1/8
  Installing : containerd-1.3.9-2.el7.x86_64                                                  2/8
  Installing : libnet-1.1.6-7.el7.x86_64                                                      3/8
  Installing : docker-cli-19.03.11.ol-8.el7.x86_64                                            4/8
  Installing : protobuf-c-1.0.2-3.el7.x86_64                                                  5/8
  Installing : criu-3.12-2.el7.x86_64                                                         6/8
  Installing : runc-1.0.0-19.rc5.git4bb1fe4.0.4.el7.x86_64                                    7/8
  Installing : docker-engine-19.03.11.ol-8.el7.x86_64                                         8/8
xfs_info: cannot open /var/lib: Is a directory
  Verifying  : protobuf-c-1.0.2-3.el7.x86_64                                                  1/8
  Verifying  : criu-3.12-2.el7.x86_64                                                         2/8
  Verifying  : runc-1.0.0-19.rc5.git4bb1fe4.0.4.el7.x86_64                                    3/8
  Verifying  : docker-cli-19.03.11.ol-8.el7.x86_64                                            4/8
  Verifying  : 2:container-selinux-2.107-3.el7.noarch                                         5/8
  Verifying  : docker-engine-19.03.11.ol-8.el7.x86_64                                         6/8
  Verifying  : containerd-1.3.9-2.el7.x86_64                                                  7/8
  Verifying  : libnet-1.1.6-7.el7.x86_64                                                      8/8

Installed:
  docker-engine.x86_64 0:19.03.11.ol-8.el7

Dependency Installed:
  container-selinux.noarch 2:2.107-3.el7
  containerd.x86_64 0:1.3.9-2.el7
  criu.x86_64 0:3.12-2.el7
  docker-cli.x86_64 0:19.03.11.ol-8.el7
  libnet.x86_64 0:1.1.6-7.el7
  protobuf-c.x86_64 0:1.0.2-3.el7
  runc.x86_64 0:1.0.0-19.rc5.git4bb1fe4.0.4.el7

Complete!
</code></pre>
</div>
</div>
<p>&nbsp;</p>
<p><strong><font size="4">3. Docker Service 실행</font></strong></p>
<pre class="highlight"><code>[root@docker-server ~]# systemctl enable docker
Created symlink from /etc/systemd/system/multi-user.target.wants/docker.service to /usr/lib/systemd/system/docker.service.</p>
[root@docker-server ~]# systemctl start docker
</code></pre>
<p>&nbsp;</p>
<p><strong><font size="4">4. Docker Service 확인</font></strong></p>
<pre class="highlight"><code>[root@docker-server ~]# docker -v
Docker version 19.03.11-ol, build f0aae77

[root@docker-server ~]# systemctl status docker
 docker.service - Docker Application Container Engine
   Loaded: loaded (/usr/lib/systemd/system/docker.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2021-02-23 00:32:33 GMT; 2min 22s ago
     Docs: https://docs.docker.com
 Main PID: 32222 (dockerd)
    Tasks: 8
   Memory: 46.5M
   CGroup: /system.slice/docker.service
           └─32222 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

Feb 23 00:32:31 docker-server dockerd[32222]: time="2021-02-23T00:32:31.892546703Z" level=warning msg="Your kernel does not support cgroup blkio weight"
Feb 23 00:32:31 docker-server dockerd[32222]: time="2021-02-23T00:32:31.892579424Z" level=warning msg="Your kernel does not support cgroup blkio weight_device"
Feb 23 00:32:31 docker-server dockerd[32222]: time="2021-02-23T00:32:31.893639687Z" level=info msg="Loading containers: start."
Feb 23 00:32:33 docker-server dockerd[32222]: time="2021-02-23T00:32:33.095688521Z" level=info msg="Default bridge (docker0) is assigned with an IP address 172.17.0.0/16. Daemon option --bip...d IP address"
Feb 23 00:32:33 docker-server dockerd[32222]: time="2021-02-23T00:32:33.593555847Z" level=info msg="Loading containers: done."
Feb 23 00:32:33 docker-server dockerd[32222]: time="2021-02-23T00:32:33.720785853Z" level=warning msg="Not using native diff for overlay2, this may cause degraded performance for building im...iver=overlay2
Feb 23 00:32:33 docker-server dockerd[32222]: time="2021-02-23T00:32:33.720998533Z" level=info msg="Docker daemon" commit=f0aae77 graphdriver(s)=overlay2 version=19.03.11-ol
Feb 23 00:32:33 docker-server dockerd[32222]: time="2021-02-23T00:32:33.722011567Z" level=info msg="Daemon has completed initialization"
Feb 23 00:32:33 docker-server systemd[1]: Started Docker Application Container Engine.
Feb 23 00:32:33 docker-server dockerd[32222]: time="2021-02-23T00:32:33.807070467Z" level=info msg="API listen on /var/run/docker.sock"
Hint: Some lines were ellipsized, use -l to show in full.
</code></pre>
<p>&nbsp;</p>
<strong><font size="4">5. Docker 관리</font></strong>
<div style="white-space:nowrap; overflow:auto;" class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>
<b># 부팅시 자동 Docker Daemon 시작</b>
[root@docker-server ~]# systemctl enable docker.service

<b># Docker Hub 사용을 위한 계정생성</b>
[root@docker-server ~]# sudo docker login
Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.
Username: chulhwani
Password:
WARNING! Your password will be stored unencrypted in /root/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded

<b># Docker Image 검색</b>
[root@docker-server ~]# sudo docker search nginx
INDEX         NAME                              DESCRIPTION                                     STARS   OFFICIAL   AUTOMATED
docker.io     nginx                             Official build of Nginx.                        14466   [OK]      
docker.io     jwilder/nginx-proxy               Automated Nginx reverse proxy for docker con…   1968               [OK]
docker.io     richarvey/nginx-php-fpm           Container running Nginx + PHP-FPM capable of…   807                [OK]
docker.io     jc21/nginx-proxy-manager          Docker container for managing Nginx proxy ho…   150               
docker.io     linuxserver/nginx                 An Nginx container, brought to you by LinuxS…   141               
docker.io     tiangolo/nginx-rtmp               Docker image with Nginx using the nginx-rtmp…   115                [OK]
docker.io     jlesage/nginx-proxy-manager       Docker container for Nginx Proxy Manager        95                 [OK]
docker.io     bitnami/nginx                     Bitnami nginx Docker Image                      94                 [OK]
docker.io     alfg/nginx-rtmp                   NGINX, nginx-rtmp-module and FFmpeg from sou…   89                 [OK]
docker.io     nginxdemos/hello                  NGINX webserver that serves a simple page co…   66                 [OK]
docker.io     nginx/nginx-ingress               NGINX Ingress Controller for Kubernetes         48                
docker.io     privatebin/nginx-fpm-alpine       PrivateBin running on an Nginx, php-fpm & Al…   46                 [OK]
docker.io     nginxinc/nginx-unprivileged       Unprivileged NGINX Dockerfiles                  31                
docker.io     schmunk42/nginx-redirect          A very simple container to redirect HTTP tra…   19                 [OK]
docker.io     staticfloat/nginx-certbot         Opinionated setup for automatic TLS certs lo…   19                 [OK]
docker.io     centos/nginx-112-centos7          Platform for running nginx 1.12 or building …   15                
docker.io     nginx/nginx-prometheus-exporter   NGINX Prometheus Exporter                       15                
docker.io     centos/nginx-18-centos7           Platform for running nginx 1.8 or building n…   13                
docker.io     raulr/nginx-wordpress             Nginx front-end for the official wordpress:f…   13                 [OK]
docker.io     bitwarden/nginx                   The Bitwarden nginx web server acting as a r…   9                 
docker.io     flashspys/nginx-static            Super Lightweight Nginx Image                   9                  [OK]
docker.io     bitnami/nginx-ingress-controller  Bitnami Docker Image for NGINX Ingress Contr…   8                  [OK]
docker.io     mailu/nginx                       Mailu nginx frontend                            8                  [OK]
docker.io     ansibleplaybookbundle/nginx-apb   An APB to deploy NGINX                          2                  [OK]
docker.io     wodby/nginx                       Generic nginx                                   1                  [OK]

<b># Docker Image download</b>
[root@docker-server ~]# docker pull nginx:latest
Trying to pull repository docker.io/library/nginx ...
latest: Pulling from docker.io/library/nginx
45b42c59be33: Pull complete
8acc495f1d91: Pull complete
ec3bd7de90d7: Pull complete
19e2441aeeab: Pull complete
f5a38c5f8d4e: Pull complete
83500d851118: Pull complete
Digest: sha256:f3693fe50d5b1df1ecd315d54813a77afd56b0245a404055a946574deb6b34fc
Status: Downloaded newer image for nginx:latest
nginx:latest

<b># Docker Image 목록 보기</b>
[root@docker-server ~]# docker image list
[root@docker-server ~]# docker image ls
[root@docker-server ~]# docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
nginx               latest              35c43ace9216        5 days ago          133MB
</code>
</pre>
</div>
</div>
<p>&nbsp;</p>
<strong><font size="4">6. Docker Image 생성</font></strong>
<div style="white-space:nowrap; overflow:auto;" class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>
[root@docker-server ~]# mkdir hostname_finder
[root@docker-server ~]# cd hostname_finder

<b># "main.go" Application Code 생성</b>
[root@docker-server hostname_finder]# cat main.go
package main

import (
        "fmt"
        "os"
        "log"
        "net/http"
)
func handler(w http.ResponseWriter, r *http.Request){
        name, err := os.Hostname()
        if err != nil {
                panic(err)
        }

        fmt.Fprintln(w,"hostname:", name)
}
func main() {
  fmt.Fprintln(os.Stdout,"Starting GoApp Server......")
        http.HandleFunc("/",handler)
        log.Fatal(http.ListenAndServe(":8080",nil))
}

<b># Dockerfile 파일 생성</b>
[root@docker-server hostname_finder]# cat Dockerfile
FROM golang:1.11-alpine AS build

WORKDIR /src/
COPY main.go go.* /src/
RUN CGO_ENABLED=0 go build -o /bin/demo

FROM scratch
COPY --from=build /bin/demo /bin/demo
ENTRYPOINT ["/bin/demo"]

<b># Dockerfile 참조해서 "goapp" 이미지 생성</b>
[root@docker-server hostname_finder]# docker build -t goapp .
Sending build context to Docker daemon  3.072kB
Step 1/7 : FROM golang:1.11-alpine AS build
Trying to pull repository docker.io/library/golang ...
1.11-alpine: Pulling from docker.io/library/golang
9d48c3bd43c5: Pull complete
7f94eaf8af20: Pull complete
9fe9984849c1: Pull complete
ec448270508e: Pull complete
65ba82af53f7: Pull complete
Digest: sha256:09e47edb668c2cac8c0bbce113f2f72c97b1555d70546dff569c8b9b27fcebd3
Status: Downloaded newer image for golang:1.11-alpine
 ---> e116d2efa2ab
Step 2/7 : WORKDIR /src/
 ---> Running in e0c50665d6ed
Removing intermediate container e0c50665d6ed
 ---> fe92438beb97
Step 3/7 : COPY main.go go.* /src/
 ---> 29dd9892d3a8
Step 4/7 : RUN CGO_ENABLED=0 go build -o /bin/demo
 ---> Running in d96fc6e909aa
Removing intermediate container d96fc6e909aa
 ---> 382c2e92fdc8
Step 5/7 : FROM scratch
 --->
Step 6/7 : COPY --from=build /bin/demo /bin/demo
 ---> f54098d2d7bd
Step 7/7 : ENTRYPOINT ["/bin/demo"]
 ---> Running in ea48d14822ea
Removing intermediate container ea48d14822ea
 ---> 4934dcbeee46
Successfully built 4934dcbeee46
Successfully tagged goapp:latest

<b># Docker Image 확인</b>
[root@docker-server hostname_finder]# docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
goapp               latest              4934dcbeee46        18 seconds ago      6.51MB
none                none                382c2e92fdc8        19 seconds ago      325MB
nginx               latest              35c43ace9216        5 days ago          133MB
golang              1.11-alpine         e116d2efa2ab        18 months ago       312MB
</code></pre>
</div>
</div>
<p>&nbsp;</p>
<strong><font size="4">7. Docker Container 시작/확인</font></strong>
<div class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>
<b># Docker Container 시작</b>
[root@docker-server hostname_finder]# docker run --name goapp-project -p 8080:8080 -d goapp
729f55251fd6a7b88bdf680fac8486be8206780fab58afd3b8545c6823e2c059

<b># Container Service 확인</b>
[root@docker-server hostname_finder]# curl localhost:8080
hostname: 729f55251fd6

<b># Container List 조회</b>
[root@docker-server hostname_finder]# docker container ls
[root@docker-server hostname_finder]# docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS                    NAMES
729f55251fd6        goapp               "/bin/demo"         21 seconds ago      Up 18 seconds       0.0.0.0:8080->8080/tcp   goapp-project

<b># 전체 Container List 조회</b>
[root@docker-server hostname_finder]# docker ps -a

<b># Docker Process 상세정보 확인</b>
[root@docker-server hostname_finder]# docker inspect goapp-project
[
    {
        "Id": "729f55251fd6a7b88bdf680fac8486be8206780fab58afd3b8545c6823e2c059",
        "Created": "2021-02-23T05:15:47.993914692Z",
        "Path": "/bin/demo",
        "Args": [],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 12361,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2021-02-23T05:15:49.898204306Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:4934dcbeee465b7b37bfcf7e867d603208ef7b31398472350bc6c3d32aefc17c",
        "ResolvConfPath": "/var/lib/docker/containers/729f55251fd6a7b88bdf680fac8486be8206780fab58afd3b8545c6823e2c059/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/729f55251fd6a7b88bdf680fac8486be8206780fab58afd3b8545c6823e2c059/hostname",
        "HostsPath": "/var/lib/docker/containers/729f55251fd6a7b88bdf680fac8486be8206780fab58afd3b8545c6823e2c059/hosts",
        "LogPath": "/var/lib/docker/containers/729f55251fd6a7b88bdf680fac8486be8206780fab58afd3b8545c6823e2c059/729f55251fd6a7b88bdf680fac8486be8206780fab58afd3b8545c6823e2c059-json.log",
        "Name": "/goapp-project",
        "RestartCount": 0,
        "Driver": "overlay2",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "default",
            "PortBindings": {
                "8080/tcp": [
                    {
                        "HostIp": "",
                        "HostPort": "8080"
                    }
                ]
            },
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "CapAdd": null,
            "CapDrop": null,
            "Capabilities": null,
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "ConsoleSize": [
                0,
                0
            ],
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": null,
            "BlkioDeviceWriteBps": null,
            "BlkioDeviceReadIOps": null,
            "BlkioDeviceWriteIOps": null,
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "KernelMemory": 0,
            "KernelMemoryTCP": 0,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": false,
            "PidsLimit": null,
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/17cf8aca3036256838e0838580c3d15111bcef2a2db896c5224e9e726c9f0800-init/diff:/var/lib/docker/overlay2/84516e3c3040b0336b800e673c0314d9753ce2816d40f314971c24c509ef32d1/diff",
                "MergedDir": "/var/lib/docker/overlay2/17cf8aca3036256838e0838580c3d15111bcef2a2db896c5224e9e726c9f0800/merged",
                "UpperDir": "/var/lib/docker/overlay2/17cf8aca3036256838e0838580c3d15111bcef2a2db896c5224e9e726c9f0800/diff",
                "WorkDir": "/var/lib/docker/overlay2/17cf8aca3036256838e0838580c3d15111bcef2a2db896c5224e9e726c9f0800/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "729f55251fd6",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "8080/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
            ],
            "Cmd": null,
            "Image": "goapp",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": [
                "/bin/demo"
            ],
            "OnBuild": null,
            "Labels": {}
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "8d124e6092c2a915586de4af814b868db8040dbefc61c258c9434aad47ae00e6",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {
                "8080/tcp": [
                    {
                        "HostIp": "0.0.0.0",
                        "HostPort": "8080"
                    }
                ]
            },
            "SandboxKey": "/var/run/docker/netns/8d124e6092c2",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "c6813f088b645bb2b01abf6aa9f32b13e3cb1c01b449ecc990ec1627549a58c0",
            "Gateway": "172.17.0.1",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.17.0.2",
            "IPPrefixLen": 16,
            "IPv6Gateway": "",
            "MacAddress": "02:42:ac:11:00:02",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "633aa1977d348150859486313eac2f2d0da48b57afc66a3866ab6b0de390b2c1",
                    "EndpointID": "c6813f088b645bb2b01abf6aa9f32b13e3cb1c01b449ecc990ec1627549a58c0",
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.2",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:ac:11:00:02",
                    "DriverOpts": null
                }
            }
        }
    }
]
</code></pre>
</div>
</div>
<p>&nbsp;</p>
<strong><font size="4">8. Docker Hub에 image upload</font></strong>
<div style="white-space:nowrap; overflow:auto;" class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>
[root@docker-server ~]# docker login --username chulhwani
[root@docker-server ~]# docker push chulhwani/goapp
The push refers to repository [docker.io/chulhwani/goapp]
cc282a374c26: Pushed
latest: digest: sha256:b18b5ff03599893a7361feda054ebe26de61a71f019dc8725bb33d87f2115968 size: 528

<b># Docker Hub의 image로 Container 실행</b>
[root@docker-server ~]# docker run --name goapp-project -p 8080:8080 -d chulhwani/goapp
CONTAINER ID   IMAGE            COMMAND      CREATED        STATUS         PORTS                   NAMES
0938068f8709   chulhwani/goapp  "/bin/demo"  5 seconds ago  Up 4 seconds   0.0.0.0:8080->8080/tcp  goapp-project
</code></pre>
</div>
</div>
<p>&nbsp;</p>
<strong><font size="4">9. Docker Instance 중지 및 삭제</font></strong>
<div style="white-space:nowrap; overflow:auto;" class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>
<b># Docker Instance 중지</b>
[root@docker-server hostname_finder]# docker stop goapp-project
goapp-project

<b># Docker Image 확인</b>
[root@docker-server hostname_finder]# docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
goapp               latest              4934dcbeee46        21 minutes ago      6.51MB
none                none                382c2e92fdc8        21 minutes ago      325MB
nginx               latest              35c43ace9216        5 days ago          133MB
golang              1.11-alpine         e116d2efa2ab        18 months ago       312MB

<b># Docker goapp Image 삭제(에러발생)</b>
[root@docker-server hostname_finder]# docker rmi 4934dcbeee46
Error response from daemon: conflict: unable to delete 4934dcbeee46 (must be forced) - image is being used by stopped container 729f55251fd6

<b># Docker 모든 Image 강제 삭제</b>
[root@docker-server hostname_finder]# docker rmi $(docker images -q) -f
Untagged: goapp:latest
Deleted: sha256:4934dcbeee465b7b37bfcf7e867d603208ef7b31398472350bc6c3d32aefc17c
Deleted: sha256:f54098d2d7bd4e1ad9f3aa0728c27553c031b25c4652ba6e94d08641943979b7
Deleted: sha256:382c2e92fdc880d724c2c8a4125b5dc5737803ebd02571e4912aa6882ec8bf93
Deleted: sha256:4f3baa7ed94a529a7224a24a27c27e4bc60409ca47b8a3108e9794d1f7acf126
Deleted: sha256:29dd9892d3a89651c848fcab420331df520b90743beb4dd2fc5334cbfe811fc4
Deleted: sha256:92927ded1036d1a5b30725a9cc0a5a92c8423da32c2d613e45008e10d61f5139
Deleted: sha256:fe92438beb9760f9473cfdf1a4367486dcb8771b66a213b91392bf5baacce8b3
Deleted: sha256:73d4225c31f262978c0f7607bd29c58faef4777d7ae43d4de3080855b3db3e4d
Untagged: nginx:latest
Untagged: nginx@sha256:f3693fe50d5b1df1ecd315d54813a77afd56b0245a404055a946574deb6b34fc
Deleted: sha256:35c43ace9216212c0f0e546a65eec93fa9fc8e96b25880ee222b7ed2ca1d2151
Deleted: sha256:61f2666cb67e4572a31412367fa44567e6ac238226385762ea65670ed39034a8
Deleted: sha256:622fb7fb6a35078e3a2d446bb0e74c6a0cd500e3a211fd17ecbbcea5377ded38
Deleted: sha256:69a8591f1aaa7d694fa79a187886f6690e6e51e8c2bc91727be01a9e87daacd2
Deleted: sha256:8a451c701633832102e10093db7545eada8e5639a1b35bb14afaf48601948802
Deleted: sha256:2edbde38832e9e0e07d113df74817dc736fd49ea2f9c0d7ce8e40e3446b49b82
Deleted: sha256:9eb82f04c782ef3f5ca25911e60d75e441ce0fe82e49f0dbf02c81a3161d1300
Untagged: golang:1.11-alpine
Untagged: golang@sha256:09e47edb668c2cac8c0bbce113f2f72c97b1555d70546dff569c8b9b27fcebd3
Deleted: sha256:e116d2efa2ab6f7af3e077771fda81477a2bc8d5c5e98d60ad00bccec714f6b9
Deleted: sha256:5fec25f9ac3477c413742ca10f2d6c16399fd78a41e5c8aea0418afd8a17a513
Deleted: sha256:2b0889b33a0db51cf154ab6a296f6dd035c8d3004ad0aed97924ec33885c0a4e
Deleted: sha256:901d0a7238b8bb071fa1529039a816df841a517eea1cb7e14f593a033295f305
Deleted: sha256:ac07a2767514fcd0741ef837900172f6c3a6df7900d1f52f11644389bd98001a
Deleted: sha256:03901b4a2ea88eeaad62dbe59b072b28b6efa00491962b8741081c5df50c65e0

<b># Docker Image 확인</b>
[root@docker-server hostname_finder]# docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE

</code></pre>
</div>
</div>
<p>&nbsp;</p>
<strong><font size="4">참고 URL</font></strong>
<pre class="highlight">
<a href="https://blogs.oracle.com/virtualization/install-docker-on-oracle-linux-7-v2" target="_blank">Install Docker on Oracle Linux 7</a><br>
<a href="https://blogs.oracle.com/blogbypuneeth/a-simple-guide-to-docker-installation-on-oracle-linux-75" target="_blank">A Simple Guide to docker installation on Oracle Linux 7.5</a>
</pre>
