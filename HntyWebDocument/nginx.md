# Nginx    
> web前端使用nginx做web服务器，并使用反向代理来解决跨域问题

### 配置文件地址

    /etc/nginx/sites-enabled/default

### 核心代码    
```nginx
# 反向代理地址
upstream wsbackend {
    server 47.92.28.186:8080;
}

# server配置
server {
    listen 8080 default_server;
    listen [::]:8080 default_server;

    # web路径
    root /home/swsw;
    index index.html index.htm index.nginx-debian.html;
    server_name prod.hntyhb.com.cn;

    # 处理403
    location / {
        try_files $uri $uri/ /index.html;
    }

    # api代理
    location /hnty/real {
        proxy_pass http://wsbackend/hnty/real;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }
    # websocket 代理
    location /a/ {
        proxy_pass http://47.92.28.186:8080/hnty/a/;proxy_redirect default;
    }
}

```