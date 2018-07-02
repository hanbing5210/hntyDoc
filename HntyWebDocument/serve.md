## index页面
> nginx代理静态web服务, 因为有惰性加载，所以会有许多chunk.js  

```shell
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2018/6/29     17:18                assets
-a----        2018/6/29     17:18        1499339 0.14cc0fca671bbbc27c87.chunk.js
-a----        2018/6/29     17:18          97992 1.2fde057dc7d43c4e8d92.chunk.js
-a----        2018/6/29     17:18          72128 1.ffaae6281cd7adfd3768.jpg
-a----        2018/6/29     17:18           9540 10.8944944b6df1c530f529.chunk.js
-a----        2018/6/29     17:18         100822 11.22f51197d85cab6b607f.chunk.js
-a----        2018/6/29     17:18          23776 12.cdcc52cd357bf2eb6858.chunk.js
-a----        2018/6/29     17:18          19084 2.993ba0fb967faf889722.chunk.js
-a----        2018/6/29     17:18           9350 3.bbe50a2898ea2c308c53.chunk.js
-a----        2018/6/29     17:18          27325 3rdpartylicenses.txt
-a----        2018/6/29     17:18          34928 4.9b9debba5f71cf152213.chunk.js
-a----        2018/6/29     17:18          38675 5.8b7dee70776d4f8704ea.chunk.js
-a----        2018/6/29     17:18          17461 6.d409100e02d118b64c75.chunk.js
-a----        2018/6/29     17:18          13968 7.242ad34c22e3f30e0b13.chunk.js
-a----        2018/6/29     17:18          28020 8.28bdaa901907bec8d1e7.chunk.js
-a----        2018/6/29     17:18          77743 9.8d464f9690646de4c97e.chunk.js
-a----        2018/6/29     17:18           2666 data-table.b0aebd744ce7adb780a9.svg
-a----        2018/6/29     17:18           2524 data-table.bce071e976865da51100.eot
-a----        2018/6/29     17:18           5430 favicon.ico
-a----        2018/6/29     17:18            680 index.html
-a----        2018/6/29     17:18           1699 inline.8a7c802296154802ef75.bundle.js
-a----        2018/6/29     17:18         344125 main.682f97503dd074e004ba.bundle.js
-a----        2018/6/29     17:18          94782 polyfills.eb7a6d4164cc6467ba4c.bundle.js
-a----        2018/6/29     17:18         891654 scripts.4a2bc3bee901531305dd.bundle.js
-a----        2018/6/29     17:18         202251 styles.74552295181645b48af7.bundle.css
```

## 开发命令
> ng serve

## 编译命令
> ng build --prod --aot  
> AOT静态编译，大大缩小js编译出的文件大小   

## 如遇node编译超过内存，请使用如下命令
> node --max_old_space_size=8192 "node_modules\@angular\cli\bin\ng" build --prod --aot 

## 编译输出文件夹
> AppClients/dist    

* inline.bundle.js
* polyfills.bundle.js
* scripts.bundle.js
* vendor.bundle.js
* main.bundle.js
* ...


