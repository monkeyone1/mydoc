#  React 第8天

**React的生命周期(life-cycle)**

setState 是异步方法

```
//setState 的另一种写法 
handleClick(){
    this.setState((prevProps,prevState) => ({
        num:prevState.num+20
    }))
}
```



实例化 

- getDefaultProps(es6 用app.defaultPros替代)

- getInitialState()

- componentWillMount

  - 在完成首次渲染之前调用，此时仍可以修改组件的state。

- render

  - 必选的方法，创建虚拟DOM，该方法具有特殊的规则：
    - 只能通过`this.props`和`this.state`访问数据
    - `this.props`和`this.state`更新会复发此方法
    - 可以返回`null`、`false`或任何React组件
    - 只能出现一个顶级组件（不能返回数组）
    - 不能改变组件的状态
    - 不能修改DOM的输出

- componentDidMount

  ​

更新

- componentWillReceiveProps  
- shouldComponentUpdate
  - 每次调用setState后都会调用shouldComponentUpdate判断是否需要重新渲染组件。
  - 默认返回`ture`,重新render
  - `false`表示跳过后续的生命周期方法
- componentWillUpdate
- render
- componentDidUpdate ()

销毁

- componentWillUnmount 组件被移除之前被调用，可以用于做一些清理工作

  ​



## React的 form

传统的form

```
form action='url'提交地址	 method='GET/POST'提交方式

```



input的处理

```
<input onChange={//通过onchange事件来获取 value值

                this.handleInput.bind(this,'input')
            } type="text" value={this.state.input}/>
            
            
```

```
handleInput(aaa,e){
        console.log(e.target.value);
        this.setState({
            [aaa]:e.target.value, //key 变量 用[]包括
            
        });
    }
```

