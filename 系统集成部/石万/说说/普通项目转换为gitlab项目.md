

## 命令行工具 
`git` [**点击下载**](http://dlsw.baidu.com/sw-search-sp/soft/e7/40642/Git-2.7.2-64-bit_setup.1457942968.exe)      

![](http://img5sw.baidu.com/soft/e7/40642/8b2002ac09be72284411c9ee5162b45e.png?version=3218763599)  

---

## 老油条请看

![](/系统集成部/石万/resource/gitlab/TIM图片20180417153348.png)

---

## 萌新请看
> 我在F:\java_test下新建了test001的springboot的java示例项目，教程以此项目为例子。

1. gitlab创建test001项目      

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180417155426.png)    

    创建成功后点击复制项目地址    

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180417155508.png)

2. 进入命令行    

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180417154346.png)

3. 输入`git init`命令初始化git工程

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180417154824.png)

4. .gitignore文件（非必需，可跳过）
    > 在Git工作区的根目录下创建一个特殊的.gitignore文件，然后把要忽略的文件名填进去，Git就会自动忽略这些文件。       

    可以编辑.gitignore文件屏蔽配置文件jar包等

5. 添加远程仓库

    命令行添加远程仓库地址`remote add origin https://gitlab.hntyhb.com.cn/xxxxxx/xxxxxx.git`

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180417155640.png)

6. 打开github desktop，点击File菜单，点击`Add local repository`,选择项目的目录

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180417155939.png)

7. commit

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180417160149.png)

8. 点击`Publish branch`按钮，上传项目

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180417160236.png)    

    这样我们的工程就转换成了gitlab工程

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180417160410.png)

