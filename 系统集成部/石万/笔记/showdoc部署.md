这货并非鸡肋，如果说swagger是机枪的话，这个就是步枪了。临时项目，小项目，突发说明等等都会用上。

## linux部署，easy我就不说了。。。

## windows server（重点来了->_<-）

### 安装 VC++ 2015 运行库

在安装 PHP 运行环境之前，我们需要先安装 VC++ 2015 运行库。访问以下链接即可下载：

```
https://www.microsoft.com/zh-CN/download/details.aspx?id=48145

```

### VC9(X86)
```
https://www.microsoft.com/zh-CN/download/details.aspx?id=5582
```

### VC12(X86)
```
https://www.microsoft.com/en-us/download/details.aspx?id=5582
```

无论操作系统是 32 位还是 64 位，都请下载 **32 位** 的运行库，即 **vc_redist.x86.exe**。

### 安装 PHP 运行环境（之所以不用官方php配置php.ini来开启，openssl和sqlite而使用集合工具，是因为试过没成功。。。）
>感觉最新版的phpStudy有些问题，这个版本实测`good`    

本文选用 phpStudy 来一键安装开发环境，官网是[www.phpstudy.net](http://www.phpstudy.net/ "null")，当前稳定版（phpStudy 2016）可以通过以下链接下载：

```
http://www.phpstudy.net/phpstudy/phpStudy20161103.zip

```

phpStudy安装略。。。


点击 **切换版本** 按钮，选择 php-7.0.12-nts + IIS。(phpStudy自动帮你处理模块映射，此处应有掌声，不过估计要自己设置默认文档。。。)

![image](/系统集成部/石万/resource/tool/TIM截图20180419204259.png)

![image](/系统集成部/石万/resource/tool/TIM截图20180419204647.png)


### 开启 openssl， 还有sqlite哦

点击右下角的 `其他选项` 菜单，如图展开后将 `php_openssl` 打勾即可。phpStudy 会自动修改配置并重启 Web 服务。

![image](https://share-10039692.file.myqcloud.com/lab/9bd893ae19/image/a9vz7jyr5n/TIM%E6%88%AA%E5%9B%BE20171117103701.png)


## 安装 Composer

Composer 是 PHP 下著名的依赖管理工具。本文使用 Composer 来安装 Laravel 以及后续开发中需要的依赖包。

### 安装 Composer

Composer 的官网是 [https://getcomposer.org](https://getcomposer.org "null") 。Windows 安装包可以通过以下链接下载：

```
https://getcomposer.org/Composer-Setup.exe

```

![image](https://share-10039692.file.myqcloud.com/lab/9bd893ae19/image/b32naz5203/TIM%E6%88%AA%E5%9B%BE20171117094952.png)

这里建议大家直接点击 Next 即可，不要勾选 Developer mode。

![image](https://share-10039692.file.myqcloud.com/lab/9bd893ae19/image/u2651yan3j/0.png)

接下来会发现，Composer 无法自动识别我们的 PHP 环境，这是因为 phpStudy 是绿色版软件，没有将 PHP 的位置添加到环境变量 PATH 中，所以我们来手动指定它。

![image](https://share-10039692.file.myqcloud.com/lab/9bd893ae19/image/if26mazkfq/TIM%E6%88%AA%E5%9B%BE20171117100435.png)

点击 Browse 按钮，参照刚才解压 phpStudy 的目录，选择对应的 php.exe。本实验选择 `C:\phpStudy\php\php-7.0.12-nts\php.exe`。（`此处注意，因为会覆盖php.ini文件，所以我机智的没选phpStudy当前的php版本下的php.exe, 请选择其他版本。反正我是这样做的， 就是不要选php-7.0.12-nts\php.exe！！！`）

![image](https://share-10039692.file.myqcloud.com/lab/9bd893ae19/image/clms9pgnis/TIM%E6%88%AA%E5%9B%BE20171117100346.png)

接下来点击 Next，之后都保持`默认设置`，最后点击 Finish 即可完成安装。

在 PowerShell 或命令提示符中执行以下命令，如果出现版本号，则说明安装成功：

```
composer -v

```

![image](https://share-10039692.file.myqcloud.com/lab/9bd893ae19/image/g6s7g3cceh/TIM%E6%88%AA%E5%9B%BE20171117100952.png)

### 配置 Composer 中国镜像

由于线路原因，Composer 默认的源并不是很稳定，可以将其修改为国内源。

在 PowerShell 或命令提示符中执行以下命令：

```
composer config -g repo.packagist composer https://packagist.phpcomposer.com

```


### 全新安装
先cd进入运行web的目录，如/wwwroot。执行以下命令：
```
composer create-project  showdoc/showdoc
```
当然也可以直接git下zip包(666)。[`github`](https://github.com/star7th/showdoc)

![](/系统集成部/石万/resource/tool/TIM截图20180419205559.png)

### IIS 部署showdoc    

![](/系统集成部/石万/resource/tool/TIM截图20180419205759.png)

### 设置文件夹权限
直接访问会发现提示文件夹没有写入的权限，即使去掉只读也没用。。。关键是还去不掉。。。     

![](/系统集成部/石万/resource/tool/TIM截图20180419210056.png)    

最终在渣度下找到了解决方法     

![](/系统集成部/石万/resource/tool/TIM截图20180419210303.png)

当然这个操作依旧是不可用的。。。。不多变通下就可以了！最终解开了文件夹的读写权限    

![](/系统集成部/石万/resource/tool/TIM截图20180419210441.png)

最后还看看我们的成果^_^

![](/系统集成部/石万/resource/tool/TIM截图20180419210605.png)



