Jenkins 环境搭建(文章来自[腾讯云](https://cloud.tencent.com/developer/labs/lab/10221))
============

安装 Jenkins
----------

> 任务时间：10min ~ 15min

### Jenkins 简介

**[Jenkins](https://jenkins.io/ "null")** 是一个开源软件项目，是基于Java开发的一种持续集成工具，用于监控持续重复的工作，旨在提供一个开放易用的软件平台，使软件的持续集成变成可能。

### Java 安装

首先我们需要准备 Java 环境，使用下面命令来安装 Java：

    yum -y install java-1.8.0-openjdk-devel
    

### Jenkins 安装

为了使用 Jenkins 仓库，我们要执行以下命令：

    sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
    sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
    

如果您以前从 Jenkins 导入过 key，那么 `rpm --import` 将失败，因为您已经有一个 key。请忽略，继续下面步骤。

#### 安装

接着我们可以使用 `yum` 安装 Jenkins：

    yum -y install jenkins
    

启动 Jenkins
----------

> 任务时间：5min ~ 10min

### 启动

启动 Jenkins 并设置为开机启动：

    systemctl start jenkins.service
    chkconfig jenkins on
    

### 测试访问

Jenkins 默认运行在 8080端口。

稍等片刻，打开 [http://<您的 CVM IP 地址>:8080](http://<您的 CVM IP 地址>:8080 "null") 测试访问。

进入 Jenkins
----------

> 任务时间：5min ~ 10min

### 管理员密码

登入 Jenkins 需要输入管理员密码，按照提示，我们使用以下命令查看初始密码：

    cat /var/lib/jenkins/secrets/initialAdminPassword
    

复制密码，填入，进入 Jenkins。

### 定制 Jenkins

我们选择默认的 `install suggested plugins` 来安装插件。

### 创建用户

请填入相应信息创建用户，然后即可登入 Jenkins 的世界。

### 实验完成

恭喜，您已完成 **搭建 Jenkins 环境搭建** 实验。

有关 **Jenkins** 的使用实践，请继续关注后续实验。