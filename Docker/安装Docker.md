# 安装Docker

本安装教程参考Docker官方文档，地址如下：

https://docs.docker.com/engine/install/centos/

根据官方提示，red hat系统参考centos系统安装

## 卸载旧版

首先如果系统中已经存在旧的Docker，则先卸载：

```shell
sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```

## 配置Docker的yum库

首先要安装一个yum工具

```shell
yum install -y yum-utils
```

安装成功后，执行命令，配置Docker的yum源：

```shell
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

## 安装Docker(使用 rpm 存储库安装)

最后，执行命令，安装Docker

```shell
yum install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## 启动和校验

```shell
# 启动Docker
systemctl start docker

# 停止Docker
systemctl stop docker

# 重启
systemctl restart docker

# 设置开机自启
systemctl enable docker

# 执行docker ps命令，如果不报错，说明安装启动成功
docker ps
```

## 配置镜像加速

这里以阿里云镜像加速为例。

### 注册阿里云账号

首先访问阿里云网站:

https://www.aliyun.com/

注册一个账号。

### 开通镜像服务

在首页的产品中，找到阿里云的**容器镜像服务**：

![2d351932-ed2f-4582-b72d-b5dbcad8b40a](https://s2.loli.net/2024/03/13/3UA8iFfNyMbX74T.png)

点击后进入控制台：

![2d351932-ed2f-4582-b72d-b5dbcad8b40a](https://s2.loli.net/2024/03/13/yK8rjq1mIk6Y9wn.png)

首次可能需要选择立刻开通，然后进入控制台。

### 配置镜像加速

找到**镜像工具**下的**镜像加速器**：

![2d351932-ed2f-4582-b72d-b5dbcad8b40a](https://s2.loli.net/2024/03/13/KdCGL8ISq3bvDru.png)

页面向下滚动，即可找到配置的文档说明：

![2d351932-ed2f-4582-b72d-b5dbcad8b40a](https://s2.loli.net/2024/03/13/fYCIHxL521ivoOt.png)

具体命令如下：

```
# 创建目录
mkdir -p /etc/docker

# 复制内容，注意把其中的镜像加速地址改成你自己的
tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://xxxx.mirror.aliyuncs.com"]
}
EOF

# 重新加载配置
systemctl daemon-reload

# 重启Docker
systemctl restart docker
```

## 安装Docker(从包中安装)

先下载安装包，地址如下：

[https://download.docker.com/linux/centos/](https://download.docker.com/linux/centos/?_gl=1*777dxv*_ga*NTcyMTczNDgxLjE3MTAwNTU1NzU.*_ga_XJWPQMJYHQ*MTcxMDA1NTU3NS4xLjEuMTcxMDA1NTY0MS41Ny4wLjA.)

安装docker

```shell
yum install /path/to/package.rpm
```

用一幅图理解docker如下：

![2d351932-ed2f-4582-b72d-b5dbcad8b40a](https://s2.loli.net/2024/03/13/zd1oeg8Fr4NK23R.png)

## 常见错误

### 缺少必要依赖

如果Docker时报错，比如：

![image-20240313215043118](https://s2.loli.net/2024/03/13/njkq4TB8D6laOJd.png)

这是由于缺少必要依赖造成的，去centos官网下载相应安装包，依次安装即可：

http://mirror.centos.org/centos/7/extras/x86_64/Packages/

```bash
rpm -ivh container-selinux-2.107-3.el7.noarch.rpm
rpm -ivh fuse3-libs-3.6.1-4.el7.x86_64.rpm
# libfuse3.so.3()(64bit) is needed by fuse-overlayfs-0.7.2-6.el7_8.x86_64
rpm -ivh fuse-overlayfs-0.7.2-6.el7_8.x86_64.rpm
rpm -ivh slirp4netns-0.4.3-4.el7_8.x86_64.rpm
```

