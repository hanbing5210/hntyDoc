## axure工具
1. `Axure RP Pro`原型设计软件 v8.0.0.3303免费汉化包版    [点击下载](http://tcy.mqego.com/axureprproch.zip)  

    ![](http://pic.cr173.com/up/2016-11/2016111815033952.png)

2. svn工具 (大家都有我就不写了)

3. `ant ux` 素材包  [点击下载](http://ux.ant.design/download/Ant_UX_Axure.zip)


## axure 创建团队工程（只有所有者需要操作这一步）

1. 点击创建团队工程  

    ![](/系统集成部/石万/resource/axure/TIM截图20180416133152.png)

2. 配置svn仓库  
  
    ![](/系统集成部/石万/resource/axure/TIM截图20180416133725.png)

3. 配置成功
  
    ![](/系统集成部/石万/resource/axure/TIM截图20180416142622.png)



## axure 团队协同（团队成员都需要）  
1. 点击获取团队工程

    ![](/系统集成部/石万/resource/axure/TIM截图20180416141242.png)

2. 配置svn仓库  
  
    ![](/系统集成部/石万/resource/axure/TIM截图20180416155453.png)

3. 签出(获取页面编辑所有权)并第一次修改页面

    ![](/系统集成部/石万/resource/axure/TIM截图20180416155645.png)

    ![](/系统集成部/石万/resource/axure/TIM截图20180416155808.png)

4. 提交变更(svn)

    ![](/系统集成部/石万/resource/axure/TIM截图20180416155942.png)

    ![](/系统集成部/石万/resource/axure/TIM截图20180416160139.png)

5. 签入(释放页面编辑所有权)

    ![](/系统集成部/石万/resource/axure/TIM截图20180416161621.png)    

    这样其他成员就可以编辑这个页面了

6. 每次要修改原型时，先“获取变更”一次，将其他人的改动更新到本地版本，以免有冲突。至于那个“提交变更”，则是相当于先做了一次“签入”，然后再次“签出”（这样可以在提交变更到服务器的同时，继续保持编辑状态）。

    ![](http://www.typemylife.com/wp-content/uploads/2016/12/update-from-all.png)
