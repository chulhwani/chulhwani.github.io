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
<p>Created symlink from /etc/systemd/system/multi-user.target.wants/docker.service to /usr/lib/systemd/system/docker.service.</p>
[root@docker-server ~]# systemctl start docker
</code></pre>
<p>&nbsp;</p>
<p><strong><font size="4">4. Docker Service 확인</font></strong></p>
<pre class="highlight"><code>[root@docker-server ~]# docker -v
<p>Docker version 19.03.11-ol, build f0aae77<p>
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
<code>
</pre>
<p>&nbsp;</p>
<p><strong><font size="4">5. Docker 관리</font></strong></p>
<pre class="highlight"><code>[root@docker-server ~]# systemctl enable docker.service  # 부팅시에 자동 Docker Daemon 시작
<p>&nbsp;</p>
[root@docker-server ~]# sudo docker login   #도커 hub 사용을 위한 계정생성
Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.
Username: chulhwani
Password:
WARNING! Your password will be stored unencrypted in /root/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
</code>
</pre>
