## app模块为根模块
* 模块类型为NgModule  
* 在Angular中Component只能注册一次，公用组件在Shared模块内注册  
* 注册服务，可以多次注入服务。在providers中

### Code
```js
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { CoreModule } from './core/core.module'
import { AppRouterModule } from './app-router.module'

import { AppComponent } from './app.component';


@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    CoreModule.forRoot(),
    AppRouterModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

### bootstrap所有app-root根入口
```js
bootstrap: [AppComponent]
```

### 引入新模块
```js
import { TestModule } from './test/test.module'
...
imports: [
    ...
    TestModule,
    ...
]
...
export class AppModule { }
```

### Route路由
```js
//appModule
import { AppRouterModule } from './app-router.module'
//appRouter
RouterModule.forRoot(routes) //只有appModule的路由才能用forRoot, 其他模块的路由只能用forChild
```

### app-Router 惰性加载各模块
> 极大的减小了包的大小，惰性加载提高载入速度，大型工程必选。原理：只有在载入模块时才加载对应的chunk.js
```js
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from "@angular/router";

const routes: Routes = [
  {path: '', redirectTo: 'login', pathMatch: 'full'},
  {path: 'login', loadChildren: 'app/login/login.module#LoginModule'},
  {path: 'test', loadChildren: 'app/test/test.module#TestModule'},
  {
    path: 'app', 
    children: [
      {path: 'home', loadChildren: 'app/home/home.module#HomeModule'},
      {path: 'situation', loadChildren: 'app/situation/situation.module#SituationModule'},
      {path: 'history', loadChildren: 'app/history/history.module#HistoryModule'},
      {path: 'warning', loadChildren: 'app/warning/warning.module#WarningModule'},
      {path: 'customer', loadChildren: 'app/customer-serve/customer-serve.module#CustomerServeModule'},
      {path: 'report', loadChildren: 'app/report/report.module#ReportModule'},
      {path: 'state', loadChildren: 'app/sys-state/sys-state.module#SysStateModule'},
      {path: 'error', loadChildren: 'app/error/error.module#ErrorModule'},
      {path: 'device', loadChildren: 'app/device/device.module#DeviceModule'},
      {path: 'step', loadChildren: 'app/step/step.module#StepModule'},
    ]
  }
];

@NgModule({
  imports: [
    RouterModule.forRoot(routes)
  ],
  exports: [RouterModule]
})
export class AppRouterModule { }
```

### 命令
> 新建模块
```js
ng g m xxx
```

> 新建模块路由
```js
ng g m --flat xxx/xxx-router
```

> 新建组件
```js
ng g c xxx
```

