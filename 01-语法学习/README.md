# 第一章节 React简介与语法学习

## React介绍

**React** 是一个用于构建用户界面的 JavaScript 库。

是Facebook在2013年5月推出的面向视图层的前端开发框架，可以解决大型应用的开发，也可以帮助程序员很好的管理DOM。

### 知识点

- 编写HelloWorld
- JSX语法
- 元素渲染
- 组件和props（单页面运用，组件间传递数据）
- React生命周期
- 事件处理（绑定事件）
- 条件渲染
- 列表渲染

## 为什么要学习React？

- 高效、灵活、组件化、Virtual DOM（与真实DOM相比）...

- 企业大多技术栈是React，现在会Vue还不够。
- react使用的是MVC框架，单项响应的数据流。

## 回顾Vue

- vue是MVVM框架（model view viewModel）
- 处理
  - model： data（defineProperty GETTER/SETTER）、computed、vuex...
    - **数据层，在new Vue的时候会指定一个data响应式状态，还会指定computed计算属性，还有可能拿Vuex存储一些公共状态，数据的改变会影响视图，因为在data中我们用defineProperty 做了一个GETTER/SETTER**
  - view： template、el、render...
    - **视图层主要是指定模板或者是el跟render**
  - viewModel： **vue用来监听数据和视图的改变，从而实现双向数据绑定**

## MVC

MVC是一种代码的组织形式，

M是model，指的是数据层，V是View，指的是视图层，C是Controller，指的是控制层，

数据层中主要负责的是数据的管理，视图层是负责用户界面的呈现，C是负责View视图层中的一些业务逻辑，例如说监听鼠标事件和键盘事件，执行到如果让数据变化的话，控制层会更新model层，然后数据渲染视图。

react相当于MVC中的V，因为它把所有要操作的数据跟操作都写在JSX语法模板中。它做的事包括，监听数据的更新，当数据更新后，帮助我们去渲染视图（DOM DIFF 、虚拟DOM变为真实DOM）

相比Vue来说

- 试图更新并没有改变数据（MVC是单向的）
- 如果需要数据的更新，则需要自己在Controller中单独处理

![MVC](images/image-20200511123927282.png)



## JSX语法

将HTML代码插入JavaScript中

```xml
<div id="root"></div>
<script type="text/babel">
  ReactDOM.render(
    <h1>Hello, world!</h1>,
    document.getElementById('root')
  );
</script>
```

```javascript
const name = 'Jack';
const element = <h1 tabIndex="0" className="red">Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

> **![img](images/0229A6BD.png)警告：**
>
> 因为 JSX 语法上更接近 JavaScript 而不是 HTML，所以 React DOM 使用 `camelCase`（小驼峰命名）来定义属性的名称，而不使用 HTML 属性名称的命名约定。
>
> 例如，JSX 里的 `class` 变成了 `className`，而 `tabindex` 则变为 `tabIndex`。

**优点**：

- 执行速度更快
- 定义虚拟DOM，更简单快捷编写模板

## 基础知识

### 编写Hello World

#### cdn

- https://unpkg.com/react@16/umd/react.development.js
- https://unpkg.com/react-dom@16/umd/react-dom.development.js
- https://unpkg.com/babel-standalone@6/babel.min.js

#### 基本语法

- ReactDOM.render()（渲染标签）
- React.createElement()（创建元素，添加属性）
- React.Component（创建组件，继承组件）

#### demo

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>cdn-react-start</title>
    <script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
</head>
<body>
    <div id="app"></div>
    <script>
        const hello = React.createElement('h1', {}, 'Hello World!')
        ReactDOM.render(hello, document.getElementById('app'));
    </script>
</body>
</html>
```

![image-20200513172234080](images/image-20200513172234080.png)

另外可以使用yarn的方式下载对应的包

```html
yarn add react react-dom --save

// 修改为引入
<script src="node_modules/react/umd/react.development.js"></script>
<script src="node_modules/react-dom/umd/react-dom.development.js"></script>
```

<img src="images/image-20200513172338331.png" alt="image-20200513172338331" style="zoom: 67%;" /><img src="images/image-20200513172422108.png" alt="image-20200513172422108" style="zoom:50%;" />

#### babel

引入babel文件，将**ES5转化成ES6语法**，简化语法

```xml
<script src="https://unpkg.com/babel-standalone@6/babel.js"></script>
<body>
    <div id="app"></div>
    <script type="text/babel">
        ReactDOM.render(
            <h1>hello World!</h1>
        , document.getElementById('app'));
    </script>
</body>
```

> 下一篇：[02-元素渲染](../02-元素渲染/)