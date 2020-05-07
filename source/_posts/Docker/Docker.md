---
uuid: 20ffa65c-7042-26b2-b86b-12843d6bbd66
title: Docker
date: 2020-01-10 08:31:17
tags:
  - Linux
categories:
  - Linux
  - docker
toc:
  enable: true # or false
  number: true # or false. Since v1.5.6
---

- Docker 是一个开源的应用容器引擎。Docker可以让开发者打包他们的应用以及依赖包到一个轻量级、可移植的容器中，然后发布到任何流行的 Linux 机器上，也可以实现虚拟化
- 容器技术：在计算机的世界中，容器拥有一段漫长且传奇的历史。容器与管理程序虚拟化（hypervisor virtualization，HV）有所不同，管理程序虚拟化通过中间层将一台或者多台独立的机器虚拟运行与物理硬件之上，而容器则是直接运行在操作系统内核之上的用户空间。因此，容器虚拟化也被称为"操作系统级虚拟化"，容器技术可以让多个独立的用户空间运行在同一台宿主级上
- docker-ee
  - 收费的
- docker-ce
  - 免费的


----

# **Docker特点**

1. 上手快：用户只需要几分钟，就可以把自己的程序“Docker 化”。Docker 依赖于“写时复制” (copy-on-write)模型，使修改应用程序也非常迅速，可以说达到“随心所致，代码即改” 的境界；随后，就可以创建容器来运行应用程序了。大多数 Docker 容器只需要不到 1 秒中即可 启动。由于去除了管理程序的开销，Docker 容器拥有很高的性能，同时同一台宿主机中也 可以运行更多的容器，使用户尽可能的充分利用系统资源

2. 职责的逻辑分类：使用 Docker，开发人员只需要关心容器中运行的应用程序，而运维人员只需要关心如 何管理容器。Docker 设计的目的就是要加强开发人员写代码的开发环境与应用程序要部署 的生产环境一致性。从而降低那种“开发时一切正常，肯定是运维的问题(测试环境都是正 常的，上线后出了问题就归结为肯定是运维的问题)”

3. 快速高效的开发生命周期：Docker 的目标之一就是缩短代码从开发、测试到部署、上线运行的周期，让你的应用 程序具备可移植性，易于构建，并易于协作。(通俗一点说，Docker 就像一个盒子，里面 可以装很多物件，如果需要这些物件的可以直接将该大盒子拿走，而不需要从该盒子中一件 件的取。)

4. 鼓励使用面向服务的架构：Docker 还鼓励面向服务的体系结构和微服务架构。Docker 推荐单个容器只运行一个应 用程序或进程，这样就形成了一个分布式的应用程序模型，在这种模型下，应用程序或者服 务都可以表示为一系列内部互联的容器，从而使分布式部署应用程序，扩展或调试应用程序 都变得非常简单，同时也提高了程序的内省性。(当然，可以在一个容器中运行多个应用程 序)


----


# **Docker客户端和服务器**

* Docker 是一个客户端-服务器(C/S)架构程序。Docker 客户端只需要向 Docker 服务器 或者守护进程发出请求，服务器或者守护进程将完成所有工作并返回结果。Docker 提供了 一个命令行工具 Docker 以及一整套 RESTful API。你可以在同一台宿主机上运行 Docker 守护 进程和客户端，也可以从本地的 Docker 客户端连接到运行在另一台宿主机上的远程 Docker 守护进程

----



# **Docker镜像**

* 镜像是构建 Docker 的基石。用户基于镜像来运行自己的容器，镜像也是 Docker 生命周 期中的“构建”部分。镜像是基于联合文件系统的一种层式结构，由一系列指令一步一步构 建出来。例如:
  * 添加一个文件;
  * 执行一个命令;
  * 打开一个窗口。
* 也可以将镜像当作容器的“源代码”。镜像体积很小，非常“便携”，易于分享、存储和更新


----


# **Registry镜像注册**

* Docker 用 Registry 来保存用户构建的镜像。
* Registry 分为公共和私有两种。Docker 公司 运营公共的 Registry 叫做 Docker Hub
* 用户可以在 Docker Hub 注册账号，分享并保存自己的 镜像(说明:在 Docker Hub 下载镜像巨慢，可以自己构建私有的 Registry）


----


# **Docker容器**

* Docker 可以帮助你构建和部署容器，你只需要把自己的应用程序或者服务打包放进容 器即可
* 容器是基于镜像启动起来的，容器中可以运行一个或多个进程
* 我们可以认为，镜像是Docker生命周期中的构建或者打包阶段，而容器则是启动或者执行阶段。容器基于 镜像启动，一旦容器启动完成后，我们就可以登录到容器中安装自己需要的软件或者服务
* 安装好的一个虚拟机


----


# **Docker镜像**

* Docker 把应用程序及其依赖，打包在 image 文件里面
* 只有通过这个文件，才能生成 Docker 容器。image 文件可以看作是容器的模板。Docker 根据 image 文件生成容器的实例。同一个 image 文件，可以生成多个同时运行的容器实例
* image 是二进制文件。实际开发中，一个 image 文件往往通过继承另一个 image 文件，加上一些个性化设置而生成。举例来说，你可以在自己操作系统所使用的image 基础上，往里面加入 Apache 服务器，形成你的image
* 就是一个操作系统文件


----


# **Docker容器操作**

1. **创建容器**
```linux
sudo docker run [option] 镜像名
-i 表示以“交互模式”运行容器
-t 表示容器启动后会进入其命令行。加入这两个参数后，容器创建就能登录进去。即 分配一个伪终端。
–name 为创建的容器命名
-v 表示目录映射关系(前者是宿主机目录，后者是映射到宿主机上的目录，即 宿主机目录:容器中目录)，可以使 用多个-v 做多个目录或文件映射。注意:最好做目录映射，在宿主机上做修改，然后 共享到容器上。
-d 在run后面加上-d参数,则会创建一个守护式容器在后台运行(这样创建容器后不 会自动登录容器，如果只加-i -t 两个参数，创建后就会自动进去容器)。
-p 表示端口映射，前者是宿主机端口，后者是容器内的映射端口。可以使用多个-p 做多个端口映射
-e 为容器设置环境变量
–network=host 表示将主机的网络环境映射到容器中，容器的网络与主机相同
```

2. **停止或启动容器**

* `docker container stop 容器名或ID`


----


# **centos部署docker**

1. 安装docker
```shell
yum -y install yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
# 添加docker-repo源
yum install docker-ce
# 尝试安装docker-ce
yum erase docker-common-2:1.13.1-96.gitb2f74b2.el7.centos.x86_64
# 删除已安装的docker
```

2. 开启docker服务
  * `systemctl start docker`


3. 查看docker镜像
  * REPOSITORY：镜像所在的仓库名称
  * TAG：镜像标签
  * IMAGEID：镜像ID
  * CREATED：镜像的创建日期(不是获取该镜像的日期)
  * SIZE：镜像大小
```shell
# 查看命令
docker image ls
docker  rm 
```

4. 拉取镜像及删除镜像
  * `sudo docker image pull delron/fastdfs`
> 上面的代码中，docker image pull是抓取 image 文件的命令。delron/fastdfs是 image 文件的名字

5. 开启fastdfs的tracker服务
  * `docker run -dti --network=host --name tracker -v /var/fdfs/tracker:/var/fdfs delron/fastdfs tracker`

6. 开启fastdfs的storage服务
  * `docker run -dti --network=host --name storage -e TRACKER_SERVER=47.96.179.72:22122 -v /var/fdfs/storage:/var/fdfs delron/fastdfs storage`

7. 关闭docker容器
  * `docker stop container_id `

8. 查看当前运行的容器
  * `docker container ls`

9. 查看docker进程
  * `docker ps -a`

10. 重启
  * `docker  container stop storage    # 关闭容器`
  * `docker  container rm  storage    # 结束进程`
  * `docker run -dti --network=host --name storage -e TRACKER_SERVER=47.96.179.72:22122 -v /var/fdfs/storage:/var/fdfs delron/fastdfs storage    # 从新启动`

11. 结束任务
  * `docker rm 12312e(进程号)`


----


# **ATOM连接docker**

1. 打开 ATOM 点击FILE==>settings

2. 点击 install
<img src="cli_install.jpg" title="进入settings" width="300px">

3. 输入 Remote-FTP
<img src="input_Remote-FTP.jpg" title="输入 Remote-FTP" width="300px">

4. 安装插件
<img src="install_Remote-FTP.jpg" title="安装 Remote-FTP" width="300px">

5. 第五步建立在安装成功的基础上，可以在自己本地建一个文件夹，我的叫fastDFS，打开就可以
<img src="open_folder.jpg" title="fastDFS文件夹" width="300px">

6. 在创建的文件夹下执行以下操作 ，创建ssh连接的文件
<img src="create_link.jpg" title="创建连接文件" 
width="300px">

7. 配置完之后，保存并退出，一定要保存
<img src="deploy_FTP.jpg" title="配置连接文件" 
width="300px">

8. 按图点击
<img src="cli_toggle.jpg" title="点击toggle"
width="300px">

9. 按图点击
<img src="cli_remote.jpg" title="点击remote"
width="300px">

10. 输入ssh连接的密码
<img src="input_Remote-FTP.jpg" title="输入ssh连接密码"
width="300px">

11. 成功
<img src="win.jpg" title="连接成功"
width="300px">


