# React 第三天

 ## ES6快速入门

   [*Bable*](http://babeljs.io/)  把SE6 语法  转换成阅览器可执行的ES5

   ES6 语法

- `let `块级声明 作用域{}中 相比 var 不会变量提升 （被Bable 编译后还会变成var；

- `const`  常量 只读  对象属性和方法可以改

- 解构赋值 

  - 变量 `let [a,b,c]=[20,10,12];`  如果缺少值得，会根据数组下标；
  - 对象` let {foo,bar}={bar:"bbb",foo:"aaa"} `    根据key来赋值value
    - `let {age,name}=obj`  自动找 obj 中的属性并赋值
    - `let  obj={name,age}`    作用域中有和value名相同的变量  对象的key和value 相同 可以省略 value
  - 字符串 `let[a,b,c,d,e='hello'];`  对应下标分别赋值给各个变量 

- Arrows箭头函数 

  - `()=>{}||x=>x-10`匿名函数没有参数或多个必须写小括号  只有一个参数可以省略小括号
  - `let add=(x,y)=>x+y; console.log(add(1,2));` 单个箭头 默认不用写return；
  - `let add=(x,y)=>{console.log(x);console.log(y);return x+y}` 多条语句需要用大括号 **{}**包裹并且得写**return**；
  - `let a1=(x,y)=>({age:x+y});`  如果返回的值是对象的话，需要用 小括号**（）** 包起来里面写 大括号 **{}**
  - 箭头函数完全修复了`this`的指向，`this`总是指向词法作用域

- 模板字符串 

  - 用反引号包裹  ${itme} 

  - ```
    console.log(`${name1}`);
    ```

    ​

- 函数的方法

  - 默认值绑定

  - ```
    function say (name='zzD',age=22) {
        console.log(name,age);
        // body
    }

    ```

- 数组操作

  - map

    - 会重新的返回一个新的数组

    - ```
      let news =[
        {title:'今天天气真好', author:'zzd'},
        {title:'今天天气真好', author:'zzd'},
        {title:'今天天气真好', author:'zzd'}];

      let newList =news.map(item=>item.title);
      console.log(newList);
      ```

    ​

  - …rest 

    -  … 可以替代 arguments   a只接受第一个字符,多余的赋值给rest

    - ```
      function methodName (a,...rest) {
          console.log(a);
          console.log(rest);
      }
      ```

      ​

  - 展开操作符

    - ```
      let a =[1,2,3];
      let b =[4,5,6];
      let c= [...a,...b];

      ```




- forEach 和 map的区别	
  - `forEach `不会返回新的数组在原先数组中修改
  - `map `会产生新的数组 