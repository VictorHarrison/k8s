
victorharrison3c.mylabserver.com login: cloud_user
Password: 
Last login: Sat Apr 18 19:46:00 UTC 2020 from localhost on pts/0
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-1065-aws x86_64)

cloud_user@victorharrison3c:~$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
[sudo] password for cloud_user: 
OK
cloud_user@victorharrison3c:~$ sudo add-apt-repository \
>    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
>    $(lsb_release -cs) \
>    stable"
Hit:1 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease                                    
Hit:3 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease                                  
Get:4 https://download.docker.com/linux/ubuntu bionic InRelease [64.4 kB]                                                    
Get:5 https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages [11.0 kB]                                        
Hit:6 http://security.ubuntu.com/ubuntu bionic-security InRelease
Fetched 75.5 kB in 1s (139 kB/s)
Reading package lists... Done
cloud_user@victorharrison3c:~$ sudo apt-get update
Hit:1 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease
Hit:4 https://download.docker.com/linux/ubuntu bionic InRelease                     
Hit:5 http://security.ubuntu.com/ubuntu bionic-security InRelease                   
Reading package lists... Done                      
cloud_user@victorharrison3c:~$ sudo apt-get install -y docker-ce=18.06.1~ce~3-0~ubuntu
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  aufs-tools cgroupfs-mount pigz
The following NEW packages will be installed:
  aufs-tools cgroupfs-mount docker-ce pigz
0 upgraded, 4 newly installed, 0 to remove and 0 not upgraded.
Need to get 40.4 MB of archives.
After this operation, 198 MB of additional disk space will be used.
Get:1 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 pigz amd64 2.4-1 [57.4 kB]
Get:2 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 aufs-tools amd64 1:4.9+20170918-1ubuntu1 [104 kB]
Get:3 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 cgroupfs-mount all 1.4 [6320 B]     
Get:4 https://download.docker.com/linux/ubuntu bionic/stable amd64 docker-ce amd64 18.06.1~ce~3-0~ubuntu [40.2 MB]
Fetched 40.4 MB in 3s (16.0 MB/s)                                            
Selecting previously unselected package pigz.
(Reading database ... 168504 files and directories currently installed.)
Preparing to unpack .../archives/pigz_2.4-1_amd64.deb ...
Unpacking pigz (2.4-1) ...
Selecting previously unselected package aufs-tools.
Preparing to unpack .../aufs-tools_1%3a4.9+20170918-1ubuntu1_amd64.deb ...
Unpacking aufs-tools (1:4.9+20170918-1ubuntu1) ...
Selecting previously unselected package cgroupfs-mount.
Preparing to unpack .../cgroupfs-mount_1.4_all.deb ...
Unpacking cgroupfs-mount (1.4) ...
Selecting previously unselected package docker-ce.
Preparing to unpack .../docker-ce_18.06.1~ce~3-0~ubuntu_amd64.deb ...
Unpacking docker-ce (18.06.1~ce~3-0~ubuntu) ...
Setting up aufs-tools (1:4.9+20170918-1ubuntu1) ...
Setting up docker-ce (18.06.1~ce~3-0~ubuntu) ...
Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /lib/systemd/system/docker.service.
Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.
Setting up cgroupfs-mount (1.4) ...
Setting up pigz (2.4-1) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Processing triggers for systemd (237-3ubuntu10.39) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for ureadahead (0.100.0-21) ...
cloud_user@victorharrison3c:~$ 
cloud_user@victorharrison3c:~$ 
cloud_user@victorharrison3c:~$ 
cloud_user@victorharrison3c:~$ 
cloud_user@victorharrison3c:~$ sudo apt-mark hold docker-ce
docker-ce set on hold.
cloud_user@victorharrison3c:~$ sudo docker version
Client:
 Version:           18.06.1-ce
 API version:       1.38
 Go version:        go1.10.3
 Git commit:        e68fc7a
 Built:             Tue Aug 21 17:24:51 2018
 OS/Arch:           linux/amd64
 Experimental:      false

Server:
 Engine:
  Version:          18.06.1-ce
  API version:      1.38 (minimum version 1.12)
  Go version:       go1.10.3
  Git commit:       e68fc7a
  Built:            Tue Aug 21 17:23:15 2018
  OS/Arch:          linux/amd64
  Experimental:     false
cloud_user@victorharrison3c:~$
