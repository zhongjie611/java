#vue 开发使用工具安装

## 工具插件总结	

- ### node.js

  #### 	概念

  ##### 		javascript服务器运行环境

  #### 	安装

  ##### 		1.下载

  ##### 		2.安装一直下一步

  ##### 		3.查看版本cmd node -v

- ### nrm 插件

  安装

  1. 运行`npm i nrm -g`全局安装`nrm`包；
  2. 使用`nrm ls`查看当前所有可用的镜像源地址以及当前所使用的镜像源地址；
  3. 使用`nrm use npm`或`nrm use taobao`切换不同的镜像源地址；

- ### cnpm插件 npm国内镜像

  安装

  ​	`npm install -g cnpm --registry=https://registry.npm.taobao.org `

  

- ### webpack打包插件

  安装

  ​	cnpm i webpack -D

  1. 运行`npm init`初始化项目，使用npm管理项目中的依赖包

     默认包名npm init -y 中文不行 手动输入包名

  2. 创建项目基本的目录结构

  3. 使用`cnpm i jquery --save`安装jquery类库

  4. 创建`main.js`并书写各行变色的代码逻辑：

  ```
  	// 导入jquery类库
      import $ from 'jquery'
  
      // 设置偶数行背景色，索引从0开始，0是偶数
      $('#list li:even').css('backgroundColor','lightblue');
      // 设置奇数行背景色
      $('#list li:odd').css('backgroundColor','pink');
  ```

  1. 直接在页面上引用`main.js`会报错，因为浏览器不认识`import`这种高级的JS语法，需要使用webpack进行处理，webpack默认会把这种高级的语法转换为低级的浏览器能识别的语法；

  2. 运行`webpack 入口文件路径 输出文件路径`对`main.js`进行处理：

     `webpack src/js/main.js dist/bundle.js`

- ### jquery 

  安装

  ​	`cnpm i jquery --save`

- ###webpack-dev-server 

  实现代码实时打包编译，当修改代码之后，会自动进行打包构建

  安装

  ​	`cnpm i webpack-dev-server -D `

- ### `html-webpack-plugin`插件配置启动页面

  安装

  ​	`cnpm i html-webpack-plugin --save-dev`

  ​	`cnpm i html-webpack-plugin -D`

- ### 各种样式loader

   ##### 	安装

   ​	

   ​	````cnpm i style-loader css-loader -D````

   ​	`cnpm i less-loader less -D`

   ​	`cnpm i sass-loader node-sass -D`

   ​	````cnpm i style-loader css-loader --save-dev````

   ​	`````cnpm i sass-loader node-sass --save-dev`````

   ​	`cnpm i sass-loader node-sass --save-dev`

- ###url-loader file-loader 图片字体文件加载器

   安装

   ​	`cnpm i url-loader file-loader -D`

- ###如果使用bootstrap安装包

   安装

   ​	cnpm i bootstrap -S

   ​	package.json

   ​	  "dependencies": {

   ​	    "bootstrap": "^3.3.7"

   ​	  }





