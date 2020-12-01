# jQuery基础介绍
毫无疑问，jQuery现在是前端应用最广泛的JavaScript库，尽管vue/react出现之后有所衰落，但是依旧不能否定jQuery对前端的重要作用。对前端人员来说，学习jQuery是必要的，因为这是基础的通用技能。

#### 1. jQuery 如何获取元素
使用jQuery的第一步，往往就是将一个选择表达式，放进构造函数jQuery()（简写为$），然后得到被选中的元素。
```
$(document) //选择整个文档对象
$('#test') //选择ID为test的网页元素
$('div.red') // 选择class为red的div元素
```
#### 2. jQuery 的链式操作是怎样的
选中网页元素以后，可以对它进行一系列操作，并且所有操作可以连接在一起，以链条的形式写出来
```
$('div').find('h3').addClass('red').addClass('blue');
```
#### 3. jQuery 如何创建元素
常见的就是直接把这个节点的结构给通过HTML标记字符串描述出来，通过$()函数处理，$("html结构")
```
$("<div></div>")
$("<div id='test' class='aaron'>我是文本节点</div>")
```

#### 4. jQuery 如何移动元素
jQuery提供两组方法，来操作元素在网页中的位置移动。一组方法是直接移动该元素，另一组方法是移动其他元素，使得目标元素达到我们想要的位置。
假定我们选中了一个div元素，需要把它移动到p元素后面。

第一种方法是使用.insertAfter()，把div元素移动p元素后面：
```$('div').insertAfter($('p'));```

第二种方法是使用.after()，把p元素加到div元素前面：
```$('p').after($('div'));```

#### 5. jQuery 如何修改元素的属性
除了元素的位置移动之外，jQuery还提供其他几种修改元素属性方法。
```
$('#p').attr('class','red') //如果存在就是修改，如果不存在就是添加
$('#p').removeAttr('name') //删除某个属性
$('#p').addClass('blue') //添加class名称
```
PS：以上内容部分参考阮一峰[jQuery设计思想](http://www.ruanyifeng.com/blog/2011/07/jquery_fundamentals.html)
