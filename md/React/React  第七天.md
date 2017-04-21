​	React 	第七天



####   React核心 **start,props,lifecycle,Compoment**

**props**

 组件之间数据传递 只能父级往子级传送

使用方法



```
this.props //拿到父级传过来的数据
this.props.xxx //根据对象名来获取数据
```



 设置默认属性

```
App.defaultProps = {
    bg: '#0f0',
    color: 'red',
    pad: 80
}
```

类型检查 **PropTypes**

 需要导入`PropTypes` 没有导入可以写成`React.PropTypes.xxx`

通过指定 `propTypes` 可以校验props属性值的类型，校验可提升开发者体验，用于约定统一的接口规范

```
import React, {Component,PropTypes} from 'react';

App.propTypes={
    bg:PropTypes.string,
    pad:PropTypes.number
    
}
```



用`...`用展开对象来代替普通赋值

```
 <Card  title='第三天的标题' date='2017.3.30' index={3}/>
                {data.map((item) => 
                             < Card {...item}/> 
                )}
```

**Chidren**





**AJAX**

原生请求

```
   		var xml = new XMLHttpRequest();
        //
        xml.onreadystatechange = function () {
            if (xml.readyState == 4 && xml.status == 200) {
                console.log(xml.responseText);
            }
        }

        xml.open("GET", "https://cnodejs.org/api/v1/topics",true);
        //limit=2 限制传回数据
        xml.send();
```

**JSON**

```
var  jsonobj=JSON.stringify(obj);  // 对象转换过成JSON对象
var obj=JSON.parse(jsonStr); // 将JSON对象解析成对象

```







