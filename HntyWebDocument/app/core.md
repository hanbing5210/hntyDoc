## 文件分布
* auth-guard.service
* auth.service
* core.module

### auth-guard.service
> 路由守护文件，在各个router文件里使用。对需要登陆操作的路由进行守护
```js
  // 核心代码
  canActivate(route: ActivatedRouteSnapshot, state: RouterStateSnapshot): boolean {
    let url: string = state.url;

    return this.checkLogin(url);
  }

  // 校验是否登陆，未登录跳转登陆页面
  checkLogin(url: string): boolean {
    if (this.authService.isLoggedIn) { return true; }
    let isLoggedIn = sessionStorage.getItem("isLoggedIn");
    if(isLoggedIn == "true") return true;

    // Store the attempted URL for redirecting
    this.authService.redirectUrl = url;

    // Navigate to the login page with extras
    this.router.navigate(['/login']);
    return false;
  }
```

### auth.service
> 用户登陆，登出。及权限管理   
```typescript
  // 用户登陆
  login(): boolean {
    return this.isLoggedIn;
  }

  // 用户登出
  logout(): void {
    this.isLoggedIn = false;
  }

  // 错误处理
  handleError(err: HttpErrorResponse) {
    localStorage.setItem("errorMsg", JSON.stringify((<any>err)._body))
    switch(err.status) {
      case 500:
        this.router.navigate(['/app/error/500'])
        break;
      case 404:
          this.router.navigate(['/app/error/404'])
          break;
      default : 
        break;
    }
  }
```

### core.module
> 配置authHttp，配合localStorage进行jwt验证（**预留 JWT 接口未启用**）
```typescript
export function authHttpServiceFactory(http: Http, options: RequestOptions) {
    return new AuthHttp(new AuthConfig({
        tokenName: 'token',
        tokenGetter: (() => localStorage.getItem('token')),
        globalHeaders: [{'Content-Type':'application/json'}],
        headerName: 'Authorization',
        headerPrefix: 'Bearer',
        noJwtError: true,
        noTokenScheme: true
    }), http, options);
}
```