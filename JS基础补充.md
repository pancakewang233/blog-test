# JS基础补充
#### 1. new 操作符
new X()作用：
1. 自动创建空对象
2. 自动为空对象关联原型，原型地址指定为X.prototype
3. 自动将空对象作为this关键词运行构造函数
4. 自动return this
    
```
let squareList = [];
  let widthList = [5, 6, 5, 6, 5, 6, 5, 6, 5, 6, 5, 6];
  function Square(width) {
    this.width = width;
  }
  Square.prototype.getArea = function () {
    return this.width * this.width;
  };
  Square.prototype.getLength = function () {
    return this.width * 4;
  };
  for (let i = 0; i < 12; i++) {
    squareList[i] = new Square(widthList[i]);
    console.log(squareList[i].constructor);
  }
```

#### 2. prototype
* 每个函数都有prototype，用来存放共有属性

* 所有函数一出生就有一个 prototype 属性
 
* 所有 prototype 一出生就有一个 constructor 属性

* 所有 constructor 属性一出生就保存了对应的函数的地址
 
* 如果一个函数不是构造函数，它依然拥有 prototype 属性，只不过这个属性暂时没什么用
 
* 如果一个对象不是函数，那么这个对象一般来说没有 prototype 属性，但这个对象一般一定会有 __proto__ 属性

##### 代码规范：

所有构造函数首字母大写，被构造出的对象首字母小写

new 后面的函数使用名词形式，其他函数一般使用动词开头

##### 原型公式：
对象.__proto__===其构造函数.prototype

* 「x 的原型」等价于「x.__proto__ 所指的对象」
* 一个对象的原型的地址存在这个对象的 __proto__ 属性里，比如 x 的原型地址就存在 x.__proto__ 里
* 一个对象的原型指的是这个对象与其他同类对象的公有属性的集合，比如 obj1 和 ob2 同时拥有 
toString / valueOf，那么 toString / valueOf 等属性组成的对象，就是 obj1 和 obj2 的原型，
这个原型的地址一般储存在构造函数的 prototype 里
* x.__proto__和 Object.prototype 存储着同一个对象的地址，这个对象就是 x 的原型
* 「根对象 Object.prototype」的原型为 null，即没有原型，其他对象都有原型

### 3. 对象分类
类型是指JS数据分类，有七种(number,string,symbol,bool,null,undefined,object)

类是针对对象object的分类，有无数种（对象 Object、数组 Array、函数 Function 等）

#### 3.1 数组对象
定义一个数组
* let arr = [1,2,3]
* let arr = new Array(1,2,3) //元素为1,2,3
* let arr = new Array(3) //长度为3
数组对象本身是字符串

#### 3.2 函数对象
定义一个函数
* function fn(x,y){return x+y}
* let fn2 = function fn(x,y){return x+y}
* let fn = (x,y) => x+y
* let fn = new Function('x','y','x+y')

### 4. 其他

window 是Window构造的
window.Object 是一个函数对象，这个「函数对象」的构造函数是Function， __proto__是Function.prototype
window.Function 是一个函数对象，这个「函数对象」的构造函数是Function， __proto__是Function.prototype
所有「函数对象」的「构造函数」都是 Function

