## 组件和props

组件一般是指UI级别的组件，而模块是指功能上的模块，在页面多，且有相似的功能的时候，需要用到组件，比如头部和底部。把这些都抽取出来，在一个地方修改，其他都可以发生变化，这样的话可以让开发效率更高，否则在每个页面都需要修改的话，成本就会很高。

### 组件的创建方式

#### <del>React.createClass()</del>

最早期版本，后面废弃了

#### 函数式组件（无状态组件）

该方式没有状态，没有生命周期，直接去加载就可以用

```javascript
function Hello(props) {
    return <div>
        <h1>Hello, {props.name}</h1>
        <p>年龄： {props.age}</p>
        <p>擅长： JavaScript</p>
    </div>;
}
ReactDOM.render(
    <Hello name="Jack" age="20"/>
, document.getElementById('app'));
```

#### React.Component

带状态组件，这种方法中的this指向React.Component的实例，具有生命周期

```javascript
// React.Component(有状态的)
class HelloJack extends React.Component{
    render(){
        return <div>
            <h1>Hello, {this.props.name}</h1>
            <p>年龄： {this.props.age}</p>
            <p>擅长： JavaScript</p>
        </div>;
    }
}
ReactDOM.render(
    <HelloJack name="Jack" age="20"/>
, document.getElementById('app'));
```

上一篇：[02-元素渲染](../02-元素渲染/)
下一篇：[04-react生命周期](../04-react生命周期/)