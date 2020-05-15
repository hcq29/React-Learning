# 第四章节 React生命周期

在了解代码的执行过程和顺序，就需要生命周期，会暴露出不同的构造函数，在构造函数里面就可以做很多操作，分四个阶段：

- 组件初始化阶段
  - 负责属性和状态的初始化
- 组件加载阶段
  - 加载组件，可获取属性值等等
- 数据更新阶段
  - 组件加载完后，涉及到组件上的属性发生变化的时候，我们需要更新
- 组件销毁阶段

![img](images/5287253-ccb7dedc0f94f981.webp)



```javascript
class Hello extends React.Component{
    constructor(props){
        console.log('初始化阶段')
        // 初始化props
        super(props)
        // 初始化状态
        this.state = {
            name: 'Jack',
            age: 30
        }
    }
    // 必须使用箭头函数，让this指向react实例，因为button指定事件的话，默认this指向button
    updateUser = ()=>{
        this.setState({
            name: 'Tom',
            age: 22
        })
    }
    componentWillMount(){
        console.log('组件加载前')
    }
    componentDidMount(){
        console.log('组件加载后')
    }
    shouldComponentUpdate(){
        console.log('数据是否需要更新')
        return true;
    }
    componentWillUpdate(){
        console.log('数据将要更新')
    }
    componentDidUpdate(){
        console.log('数据已经更新')
    }
    render(){
        console.log('组件加载或者数据更新')
        return <div>
            <h1>Hello, {this.state.name}</h1>
            <p>年龄： {this.state.age}</p>
            <p>擅长： JavaScript</p>
            <button onClick={this.updateUser}>更新数据</button>
        </div>;
    }
}
ReactDOM.render(
    <Hello/>
, document.getElementById('app'));

```

![image-20200513221159499](images/image-20200513221159499.png)

- 组件加载前可以请求数据提前存储
- 初始化阶段可以初始化默认值

> 上一篇：[03-组件和Props](../03-组件和Props/)
> 下一篇：[05-事件处理](../05-事件处理/)
