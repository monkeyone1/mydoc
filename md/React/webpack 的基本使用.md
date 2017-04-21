##  webpack 的基本使用

 webpack  是 JS 应用开发而生的**模块打捆器**

主要 的4个核心概念

- `Entry  `入口文件
- `Output` 出口文件
- `loader / rules`  加载器
- `Plugins` 插件

安装webpack

```json
npm install -g webpack
npm install webpack --save-dev
```

webpack的配置文件   `webpack.config.js`

webpack的 入口文件 出口设置

Entry 文件就是整个项目的入口文件

 Output 用来指明出口文件的名字，习惯上叫做 bundle.js

```json
module.exports={
  entry: './src/index.js',
  output: {
    path: path.resolve(__dirname, "build"),
    publicPath: "/build/",
    filename: 'bundle.js'
  };
```

~~Loader 加载器~~   reles 规则

```json
module: {
    rules: [
      { test: /\.js$/, exclude: /node_modules/, use: "babel-loader" },
      { test: /\.css$/, use: [ "style-loader","css-loader" ] },
      { test: /\.less$/, use: [ "style-loader","css-loader","less-loader" ] },
      { test: /\.(jpe?g|png)$/, use: 'file-loader' },
      { test: /\.(woff|woff2|ttf|svg|eot)(\?v=\d+\.\d+\.\d+)?$/, use: "url-loader" }
    ]
  },
```

图片加载

```json
{
  test: /\.(jpe?g|png)$/,
  loader: 'file-loader'
}
```

图标字体加载

```
{
  test: /\.(woff|woff2|ttf|svg|eot)(\?v=\d+\.\d+\.\d+)?$/,
  loader: "url?limit=10000"
}
```





Plugins 插件

Webpack 还可以通过添加各种 Plugins 来丰富自己的功能。其他开发环境下能做的一些操作，例如文件压缩，使用 html 模板

```json
  plugins: [
    new webpack.optimize.UglifyJsPlugin({
      compress: {
        warnings: false,
        drop_console: false,
      }
    }),
    new webpack.DefinePlugin({
      'process.env.NODE_ENV': '"production"',
    }),
    new webpack.HotModuleReplacementPlugin()
  ]
```



## 使用Babel-loader来解析es6和jsx

安装 balel

 ```json
npm install babel-loader babel-core --save-dev
 ```

新建个 `.balelrc` 

```json
{
  "presets": ["env", "react"],
  "plugins": []
}
```

下载三个预设需要下载安装

```json
npm install --save-dev babel-preset-env babel-preset-react
```



