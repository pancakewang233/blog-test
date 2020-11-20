# CSS 知识总结
CCS也学了一段时间，现在写一下总结。
### 浏览器渲染原理
1. 根据HTML构建HTML树（DOM）
2. 根据CSS构建CSS树（CSSOM）
3. CSSOM 树和 DOM 树合并成渲染树（Render Tree）
4. 根据渲染树来布局（Layout），以计算每个节点的几何信息
5. 将各个节点绘制到屏幕上
![avatar](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/images/render-tree-construction.png)

### CSS 动画的两种做法（transition 和 animation）
1. transition 

CSS 属性是 transition-property，transition-duration，transition-timing-function 和 transition-delay 的一个简写属性。

transition:属性名+时长+过渡方式+延迟

transition:margin-right 4s ease-in-out 1s;


2. animation 

CSS animation 属性是 animation-name，animation-duration, animation-timing-function，animation-delay，
animation-iteration-count，animation-direction，animation-fill-mode 和 animation-play-state 属性的一个简写属性形式。

animation:（选择器）+时长+过渡方式+延迟+次数+方向+填充模式+是否暂停

animation方向有：reverse反向、alternate往返、infinite alternate循环往返

animation: 3s ease-in 1s 2 reverse both paused slidein;

开始写animation会把选择器写成all，用transition的样式，这样是错误的，程序不会运行。
