# 第五章节 事件处理

将事件的this指向当前组件实例的三种方法：

## 方法一：箭头函数

在组件中定义事件，需要使用箭头函数，这样才能够让this指向React实例，不然像下面这样的话，打印的是undefined，使用箭头函数的话，this指向的就是Hello这个组件。

```javascript
class Hello extends React.Component{
    // 错误写法，this为undefined
    // updateUser(){
    //     console.log(this) // =>undefined
    // }
    click = ()=>{
        console.log(this) //  =>Hello{...}
    }
    render(){
        return <div>
            <h1>Hello world</h1>
            <button onClick={this.click}>点击</button>
        </div>;
    }
}
ReactDOM.render(
    <Hello/>
, document.getElementById('app'));
```

## 方法二：bind方法

在constructor内部绑定指针

```javascript
constructor(props){
    // 初始化props
    super(props)
    // 初始化状态
    this.state = {
        name: 'Jack',
        age: 30
    }
    this.click = this.click.bind(this) // 改变this的指向，但不调用函数方法，使用bind
}
click(){
    console.log(this) // =>Hello{...}
}
```

## 方法三：定义时指定作用域

```javascript
class Hello extends React.Component{
    click(){
        console.log(this)
    }
    render(){
        return <div>
            <h1>Hello world</h1>
            <button onClick={()=>this.click()}>点击</button>
        </div>;
    }
}
ReactDOM.render(
    <Hello/>
, document.getElementById('app'));
```

## 方法四：定义时改变作用域

```javascript
<button onClick={this.click.bind(this)}>点击</button>
```
> 上一篇：[04-react生命周期](../04-react生命周期/)
> 下一篇：[06-条件处理](../06-条件处理/)