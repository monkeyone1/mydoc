 # React 第5天

**Component 组件**

```
import React, { Component } from 'react'; //导入React
import ReactDOM from 'react-dom'; 导入ReactDOM 

import Collapse from './Collapse'
ReactDOM.render(   //只能用一个节点 
    <Collapse />,
    document.getElementById('root')
)


```



**React 的css 样式**

1.用过 导入css文件

```
import './main.css';
```

2.行内样式

```
    <h1 style={{float:'left'}}>title</h1> //用双大括号包裹
    
   用变量
    let style={
            root:{
                borderBottom:'1px solid #ccc',
                padding:'20px 0'
            },
            btn:{
                float:'right'
            }  
        }
     <div style={style.btn}>
     
```

导入图片

```
import React, { Component } from 'react';

import  Header from './component/Header';
import  bg from './images/01.png';

class App extends Component {
  
    render() {
        return (
            <div className='container' >
                <Header style={{background:`url(${bg})`}}  />
            {/**
             *  <img src={bg} alt="pic"/>
             */}
            </div>
            
        );
    }
}
export default App;
```

