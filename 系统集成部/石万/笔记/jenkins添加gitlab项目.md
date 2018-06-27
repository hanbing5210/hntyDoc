# jenkins添加gitlab项目

## jenkins 部分

### 连接配置
1. 填写连接名    

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180627102741.png)

2. 填写gitlab访问URL
3.  选择gitlab认证

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180627103044.png)

### 任务配置    
1. Build when a change is pushed to GitLab. GitLab webhook URL: http://118.24.163.102:8080/project/appclient

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180627103237.png)

2. 选择push events 时间触发构建

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180627103409.png)

3. 选择分支过滤（此处可以根据不同的需求来使用过滤功能）    
    > 可以不选，填写则写分支名以逗号分隔 
    > eg: master,

3. 点击高级->Generate 生成Secret token    

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180627103626.png)

### 构建环境
1. 点击增加构建步骤，选择执行shell    

    ![](/系统集成部/石万/resource/gitlab/TIM截图20180627103713.png)    

2. 填写shell
    
    npm install
    npm run ng build --prod --aot

### 构建后操作
> 随意发挥咯，我已用ssh来操纵其他机器，或docker发布操作等等


## gitlab部分

### 选择webhook
1. Settings -> Integrations    
    ![](/系统集成部/石万/resource/gitlab/TIM截图20180627104907.png)

2. 配置webhook    
    ![](/系统集成部/石万/resource/gitlab/TIM截图20180627105349.png)    
    ![](/系统集成部/石万/resource/gitlab/TIM截图20180627105204.png)



