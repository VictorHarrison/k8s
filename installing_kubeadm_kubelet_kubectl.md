
victorharrison1c.mylabserver.com login: cloud_user
Password: 
Last login: Sat Apr 18 19:43:29 UTC 2020 from localhost on pts/0
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-1065-aws x86_64)

cloud_user@victorharrison1c:~$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
[sudo] password for cloud_user: 
OK
cloud_user@victorharrison1c:~$ sudo add-apt-repository \
>    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
>    $(lsb_release -cs) \
>    stable"
Hit:1 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease                                                
Hit:3 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease                                              
Get:4 https://download.docker.com/linux/ubuntu bionic InRelease [64.4 kB]                                                    
Hit:5 http://security.ubuntu.com/ubuntu bionic-security InRelease                                                            
Get:6 https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages [11.0 kB]
Fetched 75.5 kB in 0s (158 kB/s)                         
Reading package lists... Done
cloud_user@victorharrison1c:~$ sudo apt-get update
Hit:1 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease
Hit:4 https://download.docker.com/linux/ubuntu bionic InRelease                                     
Hit:5 http://security.ubuntu.com/ubuntu bionic-security InRelease                                   
Reading package lists... Done                      
cloud_user@victorharrison1c:~$ sudo apt-get install -y docker-ce=18.06.1~ce~3-0~ubuntu
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
Fetched 40.4 MB in 2s (19.6 MB/s)      
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
cloud_user@victorharrison1c:~$ curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
OK
cloud_user@victorharrison1c:~$ cat << EOF | sudo tee /etc/apt/sources.list.d/kubernetes.list
> deb https://apt.kubernetes.io/ kubernetes-xenial main
> EOF
deb https://apt.kubernetes.io/ kubernetes-xenial main
cloud_user@victorharrison1c:~$ 
cloud_user@victorharrison1c:~$ 
cloud_user@victorharrison1c:~$ 
cloud_user@victorharrison1c:~$ sudo apt-get update
Hit:1 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Get:2 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]                                      
Get:3 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]                                    
Hit:4 https://download.docker.com/linux/ubuntu bionic InRelease                                                              
Hit:6 http://security.ubuntu.com/ubuntu bionic-security InRelease                                                            
Get:5 https://packages.cloud.google.com/apt kubernetes-xenial InRelease [8993 B]
Get:7 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 Packages [35.3 kB]
Fetched 208 kB in 1s (283 kB/s)    
Reading package lists... Done
cloud_user@victorharrison1c:~$ sudo apt-get install -y kubelet=1.12.7-00 kubeadm=1.12.7-00 kubectl=1.12.7-00
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  conntrack cri-tools kubernetes-cni socat
The following NEW packages will be installed:
  conntrack cri-tools kubeadm kubectl kubelet kubernetes-cni socat
0 upgraded, 7 newly installed, 0 to remove and 1 not upgraded.
Need to get 58.8 MB of archives.
After this operation, 366 MB of additional disk space will be used.
Get:1 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 conntrack amd64 1:1.4.4+snapshot20161117-6ubuntu2 [30.6 kB]
Get:2 http://us-west-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 socat amd64 1.7.3.2-2ubuntu2 [342 kB]
Get:3 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 cri-tools amd64 1.13.0-00 [8776 kB]
Get:4 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 kubernetes-cni amd64 0.7.5-00 [6473 kB]
Get:5 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 kubelet amd64 1.12.7-00 [24.6 MB]
Get:6 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 kubectl amd64 1.12.7-00 [9586 kB]
Get:7 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 kubeadm amd64 1.12.7-00 [8969 kB]
Fetched 58.8 MB in 3s (18.2 MB/s) 
Selecting previously unselected package conntrack.
(Reading database ... 168797 files and directories currently installed.)
Preparing to unpack .../0-conntrack_1%3a1.4.4+snapshot20161117-6ubuntu2_amd64.deb ...
Unpacking conntrack (1:1.4.4+snapshot20161117-6ubuntu2) ...
Selecting previously unselected package cri-tools.
Preparing to unpack .../1-cri-tools_1.13.0-00_amd64.deb ...
Unpacking cri-tools (1.13.0-00) ...
Selecting previously unselected package kubernetes-cni.
Preparing to unpack .../2-kubernetes-cni_0.7.5-00_amd64.deb ...
Unpacking kubernetes-cni (0.7.5-00) ...
Selecting previously unselected package socat.
Preparing to unpack .../3-socat_1.7.3.2-2ubuntu2_amd64.deb ...
Unpacking socat (1.7.3.2-2ubuntu2) ...
Selecting previously unselected package kubelet.
Preparing to unpack .../4-kubelet_1.12.7-00_amd64.deb ...
Unpacking kubelet (1.12.7-00) ...
Selecting previously unselected package kubectl.
Preparing to unpack .../5-kubectl_1.12.7-00_amd64.deb ...
Unpacking kubectl (1.12.7-00) ...
Selecting previously unselected package kubeadm.
Preparing to unpack .../6-kubeadm_1.12.7-00_amd64.deb ...
Unpacking kubeadm (1.12.7-00) ...
Setting up conntrack (1:1.4.4+snapshot20161117-6ubuntu2) ...
Setting up kubernetes-cni (0.7.5-00) ...
Setting up cri-tools (1.13.0-00) ...
Setting up socat (1.7.3.2-2ubuntu2) ...
Setting up kubelet (1.12.7-00) ...
Created symlink /etc/systemd/system/multi-user.target.wants/kubelet.service → /lib/systemd/system/kubelet.service.
Setting up kubectl (1.12.7-00) ...
Setting up kubeadm (1.12.7-00) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
cloud_user@victorharrison1c:~$ 
cloud_user@victorharrison1c:~$ 
cloud_user@victorharrison1c:~$ sudo apt-mark hold kubelet kubeadm kubectl
kubelet set on hold.
kubeadm set on hold.
kubectl set on hold.
cloud_user@victorharrison1c:~$ kubeadm version
kubeadm version: &version.Info{Major:"1", Minor:"12", GitVersion:"v1.12.7", GitCommit:"6f482974b76db3f1e0f5d24605a9d1d38fad9a2b", GitTreeState:"clean", BuildDate:"2019-03-25T02:49:02Z", GoVersion:"go1.10.8", Compiler:"gc", Platform:"linux/amd64"}
cloud_user@victorharrison1c:~$ 
