# 虚拟 DOM 和 DOM diff

#### 虚拟 DOM 是什么

* 虚拟DOM是一个能代表 DOM 树的Javascript对象，通常含有标签名、标签上的属性、事件监听和子元素们，以及其他属性。在优化几千个节点的时候速度跟原生dom一样快。

#### 虚拟 DOM 优点

1. 减少 DOM 操作

* 虚拟 DOM 可以将多次操作合并为一次操作，比如你添加 1000 个节点，却是一个接一个操作的（减少频率）

* 虚拟 DOM 借助 DOM diff 可以把多余的操作省掉，比如你添加 1000 个节点，其实只有 10 个是新增的（减少范围）

2. 跨平台

* 虚拟 DOM 不仅可以变成 DOM，还可以变成小程序、iOS 应用、安卓应用，因为虚拟 DOM 本质上只是一个 JS 对象



创建虚拟 DOM

```jsx
//React JSX
<div className="red" onClick="{()=> {}}">
    <span>span1</span>
    <span>span2</span>
</div>
```

```html
//vue template，通过vue-loader转为 h 模式
<div class="red" @click="fn">
  <span>span1</span>
  <span>span2</span>
</div>
```

#### 虚拟DOM的缺点

需要额外的创建函数和打包工具，如 createElement 或 h，但可以通过 JSX 来简化成 XML 写法。



#### 什么是 DOM diff

通过JS的计算，返回一个函数，我们称之为 patch。解析patch对象，完成页面的重新渲染。

patches = patch(oldVNode, newVNode)

patches 就是要运行的 DOM 操作，可能长这样：

```js
[

 {type: 'INSERT', vNode: ... },

 {type: 'TEXT', vNode: ... },

 {type: 'PROPS', propsPatch: [...]}

]
```

#### DOM diff的优点

DOM diff 会将新旧两棵树、组件或者标签逐层对比，也就是Tree diff/Component diff/Element diff，找出哪些节点需要更新。解决了每次更新内容需要全部重新渲染的问题，只是找出其中有变化的部分进行局部更新。

#### DOM diff的问题

在使用index下标来作为key时，因为下标index会变化，同级节点对比存在 bug。只能通过设置唯一 key的策略，对 DOM diff 进行算法优化。


