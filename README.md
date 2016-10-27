# vue-learning
基于面向组件的vue学习笔记

崭露头角的 JavaScript 框架 Vue.js 2.0 版本已经发布~\(≧▽≦)/~啦啦啦   [vue.js 2.0](https://vuejs.org/guide/)

教程和官方文档请移步：

[vue.js官方文档](https://vuejs.org/)

[vue.js 1.0中文](https://vuejs.org.cn/)

[vue.js 2.0中文](https://vuefe.cn/)

[vue.js github](https://github.com/vuejs)

### 什么是vue
Vue 是一个前端框架，Vue.js是Javascript MVVM库，它是以数据驱动和组件化的思想构建的。

其特点是：

1.数据绑定

比如你改变一个输入框 Input 标签的值，会自动同步更新到页面上其他绑定该输入框的组件的值

2.组件化

页面上小到一个按钮都可以是一个单独的文件.vue，这些小组件直接可以像积木一样通过互相引用而组装起来

### 环境配置
初始化工程，需要 node 环境使用 npm 安装相应的依赖包。

先创建一个测试目录，在里面依次输入以下命令
```
//初始化package.json
npm init

//安装vue的依赖
npm install vue --save
npm install vue-router --save

//安装webpack的开发依赖
npm install webpack --save-dev

//安装babel的ES6 Loader 的开发依赖
npm install babel --save-dev
npm install babel-core --save-dev
npm install babel-loader --save-dev
npm install babel-preset-es2015 --save-dev

//安装html loacer 的开发依赖
npm install html-loader --save-dev
```

### webpack配置
```
//webpack配置
var webpack = require('webpack');

module.exports = {
	//输入，入口
	entry: {
		bundle: [./src/app.js]
	},
	//输出
	output: {
		path: __dirname,      // 输出文件的保存路径
		publicPath: "/",
		filename: "build/[name].js"  // 输出文件的名称
	},
	module: {
		loaders: [
			{
				test: /(\.js)$/, 
				loaders: ["babel"], 
				exclude: /node_modules/,
			    query: {
			    	presets: ["es2015"]
			    }
		    }
		]
	},
	//模块解析配置项
	resolve: {

	},
	plugins: [
	    /*
	    new webpack.optimize.UglifyJsPlugin({
            compress: {
                warnings: false
            }
        })
	    */
	]
}
```

### 第一个组件
#### components/index.js
```
module.exports = {
  template: require('../templates/index.html'),

  ready: function () {
  }
};
```

#### templates/index.html
```
<h1>Index</h1>
<hr/>
<p>Hello Vue!</p>
```

执行 webpack 构建命令

