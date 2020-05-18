# 环境搭建

## create-react-app

create-react-app脚手架是基于Webpack + ES6 ，可以快速搭建react开发环境，执行以下命令创建项目：

```bash
$ npm install -g create-react-app
$ create-react-app my-app
$ cd my-app/
$ npm start
```

## 初试文件目录结构

```
my-app
├── README.md 项目介绍
├── node_modules  存放 npm 安装的工具包 或 模块
├── package.json  npm包配置文件，里面定义了项目的npm脚本，依赖包等信息
├── .gitignore  git的选择性上传的配置文件
├── public  静态资源，公用模板和图标等
│   ├── favicon.ico  网站图标
│   ├── index.html  首页的模板文件
│   └── manifest.json  移动端配置文件
└── src  源码目录，存放开放源代码
    ├── App.css
    ├── App.js  方法模块
    ├── App.test.js
    ├── index.css
    ├── index.js  项目的入口文件
    ├── logo.svg
    └── serviceWorker.js
    └── setupTests.js
```

问题：目录规范

参考其他项目整合项目目录结构

```
├── build          ----------------------网页配置
│   ├── favicon.ico  
│   └── manifest.json 
├── config            ------------------webpack配置
├── package-lock.json
├── package.json    --------------------项目package.json
├── README.md      ----------------------README
├── public          --------------------出口
│   ├── favicon.ico
│   ├── index.html   ---------------------入口文件，单页面
│   └── manifest.json   ---------------------缓存
├── scripts        ---------------------运行的脚本
│   ├── build.js
│   ├── start.js
│   └── test.js
└── src           ----------------------源码目录
    ├── api       ----------------------API目录
    │   ├── api.js
    │   └── server.js
    ├── assets   -----------------------资源目录
    │   └── iconfont -------------------iconfont目录
    ├── components   -------------------公共组件
    │   └── ......
    ├── config    ----------------------项目一些配置
    │   ├── envconfig.js  --------------配置信息
    │   └── rem.js  --------------------自适应
    ├── pages       --------------------页面目录
    │   ├── home    --------------------主页页面
    |   ├── login   ---------------------商店页面
    │   └── ... 
    ├── router   -----------------------路由
    │   └── index.js
    ├── store   ------------------------react-redux状态管理目录
    │   ├── store.js
    │   └── user
    ├── style   ------------------------通用样式目录
    │   ├── base.scss
    │   ├── mixin.scss
    │   └── swiper.min.css
    └── utils  ------------------------公用方法
    │   ├── asyncComponent.jsx  -------异步加载组件
    │   └── commons.js  ---------------公用方法
    ├── App.css
    ├── App.js  方法模块
    ├── App.test.js
    ├── index.css
    ├── index.js   ---------------------项目的入口文件
    ├── logo.svg
    ├── serviceWorker.js ---------------热加载
    └── setupTests.js

```
