## 模块用途
> 各应用模块应引用，为通用模块，无路由无服务

## 文件分布
* ./common 通用组件文件夹
* ./layout-fluid 布局组件
* ./switch-menu 菜单按钮
* *.directive.ts 指令(预留)
* *.pipe.ts 管道(预留)

## ./common
* alert 信息提示组件
* common-line-chart 态势页图表
* holder 列表为空时的默认空图组件
* import  默认导入页
* situation-card  态势页panel
* table 默认table

## layout
> 布局文件
```html
<div id="wrap">
	<ng-content></ng-content>
	<app-switch-menu></app-switch-menu>
</div>
```

## switch-menu
> 菜单按钮，默认各模块页面进行导航的按钮，各业务模块都会引用
```ts
  // 链接列表
  menus: any[] = [{
    url: '/app/home',
    title: "主页"
  }, {
    url: '/app/situation',
    title: "仪器整体态势"
  }, 
  {
    href: 'http://47.92.28.186:8080/hnty/a/monitor/device/view',
    title: "测量过程监控"
  }, 
  {
    url: '/app/history',
    title: "测量历史溯源"
  }, {
    url: '/app/step',
    title: "工步历史"
  }, {
    url: '/app/warning',
    title: "测量通知报警"
  }, {
    url: '/app/report',
    title: "仪器测量报表"
  }, {
    url: '/app/customer',
    title: "销售及服务网点"
  }, {
    url: '/app/state',
    title: "系统运行状态"
  }, {
    url: '/app/device',
    title: "仪器列表"
  }]
```