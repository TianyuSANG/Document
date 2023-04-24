## Jenkins

持续集成工具Jenkins

1 持续部署

2 持续集成

3 持续交付

 

持续迭代，降低风险，减少重复过程

任何时间，任何地点生成可部署的软件

增强项目可见性

-----

持续集成工具

Jenkins和Hundson

Jenkins可以整合GitHub或Subversion

Hundson也可以整合GitHub或Subversion

---

![Aaron Swartz](https://github.com/TianyuSANG/Document/raw/main/jpg/Manual%20Jenkins.jpg)

---

![Aaron Swartz](https://github.com/TianyuSANG/Document/raw/main/jpg/Auto%20Jenkins.jpg)

## Kubeadm

Kubernetes一键部署脚本（使用docker运行时）

kubeadm 可以帮助部署一套kubernetes集群。kubeadm设计目的是为新用户开始尝试

kubernetes提供一种简单的方法

 

该工具通过两个指令完成一个kubernetes集群的部署

创建一个Master节点

kubeadm init

将一个Node节点加入到当前集群中

kubeadm join <Master节点的IP和端口>



## rpm和deb

RPM是linux下的一个软件包管理器，通过它可以轻松容易的实现软件的安装

安装软件: rpm -ivh rpm包名

rpm -ivh apache-1.3.6.i386.rmp

升级软件: rmp -Uvh rpm包名

反安装: rpm -e rpm包名

查询软件包的详细信息: rpm -qpi rpm包名

查询某个文件时属于哪个rpm包: rpm -qf rpm包名

查询该软件包会向系统写入什么文件: rpm -qpl rpm包名

---

deb是Unix系统下的安装包，基于tar包，本身会记录文件的权限以及所有者/用户组

Unix对权限，所有者，组的严格要求，而deb格式安装包经常涉及到系统底层的操作，权限等设置很重要

deb包本身 三部分组成：数据包，包含实际安装的程序数据，文件名为data.tar.XXX；安装信息及控制脚本包，抱恨deb安装说明，标识脚本等，文件名为control.tar.gz；最后一个是deb文件的一些二进制数据，包含文件头等信息，一般看不到，需要某些软件打开可以看到。

deb包本身可以有不同压缩方式。tar格式并不是一种压缩格式，而是直接将分散的文件和目录集合在一起，并记录权限等数据信息。deb默认使用的压缩格式为gzip格式，data.tar.gz。常有的压缩格式还有bzip2和lzma，其中lzma压缩率最高，但压缩需要的CPU资源和时间都比较长。

data.tar.gz包含的是实际安装的程序数据，安装过程，该包里数据会被直接解压到根目录(即/)，因此打包之前需要根据文件所在位置设置好相应的文件/目录树。

control.tar.gz包含了一个deb安装的时候需要的控制信息。一般包含5个文件：control，用于记录软件标识，版本号，平台，依赖信息等数据；preinst，在解包data.tar.gz前运行的脚本;postinst，在解包数据后运行的脚本；prerm，卸载时，删除文件前执行的脚本；postrm，在删除文件后运行的脚本；



## Docker

容器虚拟化技术，轻量级虚拟化技术，是以应用程序为中心的虚拟化技术

传统的虚拟化技术，是以操作系统为中心的。



传统虚拟化：

指通过虚拟化技术将一台计算机虚拟为多台逻辑计算机。一台计算机上同时运行多个逻辑计算机，每个逻辑计算机可运行不同的操作系统，并且应用程序可以在相互独立的空间内运行互不影响，从而显著提高计算机的工作效率。

随硬件厂商发展，很多虚拟机里面的指令不需要通过虚拟的硬件层走到真正的硬件层。硬件厂商支持直接在虚拟机里使用指令操作硬件，该技术称为硬件辅助的虚拟化，性能和效率比传统虚拟化更高些。

系统级别的虚拟化特点，不需要模拟硬件层，共享同一个宿主机的内核。

 

帮助命令

docker version

docker info

docker --help

镜像命令

docker images 

-a:列出所有镜像

-q:显示当前镜像的id

--digests:显示镜像摘要信息

--no-trunc:显示完整的镜像信息

docker search tomcat

docker pull tomcat

docker rmi tomcat

容器命令

docker run -it id

docker run -it --name mycentos centos

docker ps

exit

ctrl+P+Q //推出容器，但不关闭

dcoker start 容器id

docker restart 容器id

docker stop 容器id

docker kill 容器id

docker rm 容器id 删除已经停止的容器

docker rm -f 容器id 删除在运行的容器

docker rm -f $(docker ps -a -q)删除多个容器

docker ps -a -q | xargs docker rm

 

docker run -d centos 守护进程方式启动容器

docker logs -f -t --tail 容器id

docker inspect 容器id

docker exec -it 容器id 是在容器中打开新的终端，可以启动新的进程

docker attach 容器id 直接进入容器启动命令的终端，不会启动新的进程