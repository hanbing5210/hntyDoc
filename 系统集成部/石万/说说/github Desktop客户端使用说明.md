## github公司出品图形化工具 `GitHub DeskTop` [**点击下载**](https://central.github.com/deployments/desktop/desktop/latest/win32)     
![](https://desktop.github.com/images/desktop-icon.svg) 

`GitHub DeskTop`是github公司推出的一款git技术图形化工具，既然是盈利性质的公司推出的，那么`你懂的~`会让你登陆github账号，还不明白？想想qq浏览器吧，ie有让你等陆吗？  

说了这么多就是为了说明一点，你不登陆一点都不影响你git的使用。。。没有github账号的请点击 `skip`

***

## 概念说明：  

* 仓库：就是我们说的项目，git里将我们的项目称之为仓库
* 工作区：我们的实际代码
* 远程仓库：放在gitlab服务器上的项目
* 本地仓库：放在本地计算机的项目，在项目的 `.git` 文件夹里
* pull (`拉取`)：从远程仓库同步 (`下载`) 代码到本地仓库
* commit (`提交`)：将工作区的代码提交 (`覆盖`) 到本地仓库里去，并记录这次提交的所有修改
* push (`推送`)：将本地仓库同步(`上传`)到远程仓库
* merge：这个是进阶内容，不在入门范围内。

***

## 新建仓库操作

![](/系统集成部/石万/resource/git/TIM截图20180417111736.png)


1. new repository(`新建仓库`)   

    ![](/系统集成部/石万/resource/git/TIM截图20180417114256.png)


2. add local repository(`添加一个本地仓库`)    
有时候我们本地已经有仓库的了，我们想用`GitHub DeskTop`这个工具来管理我们底git工程而不是用`git pull` 这样的命令来管理项目，就可以添加本地仓库，来图形化管理了


3. clone repositoty(`克隆远程仓库`)     
这是我们用得最多的功能了，可以克隆远程仓库到本地。

    ![](/系统集成部/石万/resource/git/TIM截图20180417114925.png)

***

## pull(`拉取`)当前分支最新代码到本地
> 团队协助，会有非常多他人的提交，经常pull再编辑项目会大大减少冲突的可能性。    

`点击`Fetch origin会拉取远程仓库到本地
![](/系统集成部/石万/resource/git/TIM截图20180417115453.png)

***

## commit(`提交`), push(`推送`) 在git入门文档里有说明


