# React 第四天

## es6 Class 

- ES6的`class`可以看作只是一个语法糖

- `constructor`方法，这就是构造方法，而`this`关键字则代表实例对象.类里面定义属性要写到`constructor`方法中,这个方法是类默认带的

- 默认就是严格模式

- ​

- 代码

  ```
  class Peole {
    constructor(name ,age,height) {
      this.name=name;
      this.age=age;
    }
    say(){
      console.log(this.name,this.age,this.height);
    }
  }
  ```

- super

  - 可以当作函数使用，也可以当作对象使用
  - `super()`作为函数调用时，代表父类的构造函数
  - 更改`this` 指向

- 继承 `extends`



**两种导入js模块的方式**

1. **nodejs的方式导入js**

   - ```
     index.js
      const test = require('./test');
      console.log(test);
      
      test.js
       let str ='hello 这是个测试';
      // module.exports = str; 
      // module.exports.str=str; 以对象形传递
      
     ```

2. 原生js 方式导入js

   - 命名导出

     ````
     // import { str,sun } from './test.js';
     // console.log(str);
     // sun()

     test.js
      let str ='hello 这是个测试';
      function sun() {
          console.log('666');
      }
      export {str,sun};
     ````

   - 默认导出

     ```
     index.js
     import xxx from './test.js';
     console.log(xxx)；
     test.js
     let str ='hello 这是个测试';
     export default str;
     ```



##  React 基础

   **JSX语法特点 **

- jsx可以嵌入变量和表达式,注意在jsx变量中需要{}来包裹
- 每个标签必须关闭
- 每个react节点必须包裹在一个闭合标签内
- render 中  注释必须用{}包裹起来` {/* 我是注释 */}`
- `class` 要写成` className` `  for `要改写成`HTMlfor`

 **React 组件创建的方法**

组件名 必须大写 否者会当做 原生的html来渲染

1. ``` 
   //第一种(过时)
   // var  Dom =React.createClass({
   // 
   //   render:function() {
   //     return(<div>aaaaaa</div> )
   //   }
   // })
   ```

2. ```
   // 第二种（常用）function
   // function Dom () {
   //   return(
   //     <div>hello </div>
   //   )
   // }
   ```
   ​

3. ```

   import React, { Component } from 'react';
   class Header extends Component {
     render() {
       let color ='green';
       let style1={color:{backgroud:'#ff0'},height:{height:'200px'},text:{textDecoration:'underline'}}
       let style={color:color,height:'53px'}
       return (
         <div className='Header' >
           <h1 style={style}>Header</h1>
           <h1 style={Object.assign({},style1.color,style1.height,style1.text)} >hello</h1>
         </div>
       );
     }
   }

   export default Header;
   ```



   ```

   ```

