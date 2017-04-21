# React 第 八 天

 **react-router** 

 下载react-router

```	
npm install react-router --save
```

 一个简单的小Demo

```
import React, { Component } from 'react';
import { Router, Route, browserHistory,IndexRoute, Redirect } from 'react-router';


lass Routers extends Component {
  render() {
    return (
      <Router history={browserHistory}>
        <Route path="/" component={Home}>
          <IndexRoute component={App} onLeave={leaveAlert}/>
          <Route path="about" component={About} />
          <Route path="blog/:title" component={Blog} />
          <Route path="work" component={Work} onEnter={checkAdmin}>
            <Route path="detail" component={Detail} />
          </Route>
          {/* <Route path="*" component={NotFound} /> */}
          <Route path="404" component={NotFound} />
          <Redirect from='aboutme' to='about' />
          <Redirect from='*' to='404' />
        </Route>
      </Router>
    );
  }
}

export default Routers;

```

 

这个小Dome 是react-route 最常用的方法

导入的组件

- `Router`  组件本身只是个容器 可以有属相 `history`分别有三个参数:
  - `browserHistory`   这个需要服务器支持 不再通过Hash 完成,浏览器会调用HIstoty API.
  - `hashHistory`   路由将通过url 的hash部分(#),例如`hello.com/#/home`
  - `createMemoryHistory`  用于服务器渲染, 会在内存中创建History 对象,不再和浏览器url互动



- `Route`  组件定义了url组件的对应的关心 ,你可以同时使用多个路由并且可以嵌套

  - `path` :代表用户访问的路径

  - `component` :  用户访问这个路径的时候, 目的地址是个React的组件

  - 路由钩子 每个路由都有 `onEnter`和`onLeave`钩子, 用户进入或离开的时候会触发(可以来做用户权限)

  - 路由变量: `<Route path="blog/:title" component={Blog} />` 其中`:title`就是一个路由变量可通过`this.props.params.title`  来获取参数

    ​

- `IndexRoute` 组件

- `Redirect` 用于路由的跳转，即用户访问一个路由

- `Link`   是react-router 提供的组件 ，可以直接使用软件路由 （可以理解react 中的`a`标签  ）

  - `activeStyle`

  - `activeClassName`

    ​

  ​
