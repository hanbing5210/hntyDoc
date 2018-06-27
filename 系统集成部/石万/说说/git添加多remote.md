# git 添加多remote

> 开发测试两不误，开发主fetch/push，测试副push。(当前仅自己的服务器部署jenkins且主web服务器不可随意发布)这样可以在副上用jenkins ci/cd 自动化测试部署预览

## git添加多远程库

    git remote set-url --add origin https://gitlab.com/shiwan66/appclient.git
    git push origin --all




