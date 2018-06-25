Jenkins 环境搭建
============

java 8 环境准备
----------

### install java 8 on ubuntu

    sudo add-apt-repository ppa:webupd8team/java
    sudo apt-get update
    sudo apt-get install oracle-java8-installer

## 设置环境变量

    cat >> /etc/environment <<EOL
    JAVA_HOME=/usr/lib/jvm/java-8-oracle
    JRE_HOME=/usr/lib/jvm/java-8-oracle/jre
    EOL

jenkins 安装
----------

### jenkins 安装

    wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
    sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
    sudo apt-get update
    sudo apt-get install jenkins

> 8080端口被占用启动不了可以按如下资料解决：If your /etc/init.d/jenkins file fails to start Jenkins, edit the /etc/default/jenkins to replace the line ----HTTP_PORT=8080---- with ----HTTP_PORT=8081---- Here, "8081" was chosen but you can put another port available.

### jenkins 命令

启动jenkins：
    
> sudo /etc/init.d/jenkins start

关闭jenkins：

> sudo /etc/init.d/jenkins stop