 # React 第六天



###  state (状态)

- 一切状态


- 状态变化，会触发react组件渲染
- state 管理组件内部数据和状态
- 修改`state` 需要用`setState`这个方法，否则不会触发重新渲染

代码

```
import React, { Component } from 'react';

class App extends Component {
    constructor() {
        super();
        this.state={
            num:100,
            sex: true
            
        };
    }
    click(){
        console.log(this);
        this.setState({
            num:this.state.num+1,
            sex:!this.state.sex
        });    
    }
   render() {
        return (
            <div>
                我当前的数字是{this.state.num} <br/>
                <p>性别:{this.state.sex? '男':'女'}</p>
                <button onClick={this.click.bind(this)}>+1</button>
//通过bind来绑定this指向
            </div>
        );
    }
}

export default App;

```

### 使用ref 来获取真实 DOM 的方式

**1.第一种方式(字符串方式 过时 不推荐使用)**

```
console.log(this.refs.input.value;)
<Test ref='Test'/> //
```

**2.第二种方式(用回调方式 官方推荐)**

```
console.log(this.input1);
<input ref={input=>this.input1=input} />
```











