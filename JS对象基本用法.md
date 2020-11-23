# JS 对象基本用法
`JavaScript`语言一共有七种数据类型：
* 数值（number）：整数和小数（比如1和3.14）
* 字符串（string）：文本（比如Hello World）。五个falsy值：undefined、null、0、null、‘’（空字符串）
* 布尔值（boolean）：表示真伪的两个特殊值，即true（真）和false（假）
* undefined：表示“未定义”或不存在，即由于目前没有定义，所以此处暂时没有任何值
* null：表示空值，即此处的值为空
* Symbol，Symbol()函数会返回symbol类型的值，该类型具有静态属性和静态方法
* 对象（object）：各种无序的值组成的集合

### `object`，对象就是一组“键值对”（key-value）的集合，是一种无序的复合数据集合。

  #### 1.声明对象
  ```
  let obj = {'name': 'frank', 'age': 18}
  let obj = new Object({'name': 'frank'})
  ```
  keys键名都是字符串，不管引号有无省略。

  #### 2.删除对象属性
  ```
  delete obj.xxx
  delete obj['xxx']
  ```
  以上两种方法可以删除obj的xxx属性。

  #### 3.查看属性
  查看所有属性可以用以下两种方法：

  `Object.keys(obj)`可以查看自身所有属性

  `console.dir(obj)`可以查看自身+共有属性

  如果只是简单地查看属性可以用：
  ```
  obj['key']
  obj.key
  ```

  #### 4.修改或增加属性
  * 直接赋值
  `let obj = {name: 'frank'}`
  * 批量赋值
  `Object.assign(obj, {age:18, gender:'man'})`

  #### 5.`'name' in obj`和`obj.hasOwnProperty('name')` 的区别
  `'name' in obj` 只能判断obj自身属性+共有属性之中是否存在'name'属性名

  `obj.hasOwnProperty('name')` 则是判断obj自身的属性之中是否有'name'属性名

