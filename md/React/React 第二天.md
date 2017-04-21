# React 第二天

 node模块分类

- Node.js 核心模块 api

- 通过npm 安装的模块 (安装到项目文件夹下的node modules 下)

- 自己写的 js 文件 (用相对路径)

  - `var num =require('./b.js');`

    ​

    **npm使用**

    - `npm init ` 初始化node 项目 ，生成 package.json ，记录项目的一些描述及依赖
    - `npm install  ` [包名]  --save|| --save-dev||-g
      - `--save`  将包名记录到了 dependencies 字段下，通常我们项目上线之后仍然依赖的
      - `--save-dev` 可以缩写为 -D 将包名记录到了 devDependencies 字段下，通常我们项目开发时候依赖的上线不需要它的代码，比如一些打包工具
      - `-g` 将模块安装到我们的用户主目录下，通长安装的是一些需要它的脚本命令的，可以在任何地方使用它
    - `npm install `   可以安装项目内package.json中记录的依赖
    - WARN 警告 可以忽略
    - Install uninstall[包名][-g] 卸载模块， **注意手动删除 package.json** 的记录
    - .gitignore  过滤不想上传的文件

  - 安装React

    - ```
      npm install -g create-react-app 
      ```

    - ```
      create-react-app my-app
      cd my-app／
      ```

      ​



**package.json**

```
{
  "name": "mytest",      项目名字
  "version": "1.0.0",    版本号
  "description": "",     描述
  "main": "a.js",        入口文件
  "dependencies": {},    依赖 --save （不要多空格）
  "devDependencies": {}, 开发依赖。
  "scripts": {            可以自定义脚本
    "test": "echo \"Error: no test specified\" && exit 1",
    "test1":"node -v"   自定义的脚本
    
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/monkeyone1/TestDemo.git"
  },
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/monkeyone1/TestDemo/issues"
  },
  "homepage": "https://github.com/monkeyone1/TestDemo#readme"
}

```

