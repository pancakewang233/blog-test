# JS 函数的执行时机
setTimeout()方法设置一个定时器，该定时器在定时器到期后执行一个函数或指定的一段代码。
```
let i = 0
for(i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```
setTimeout会在其他程序执行完之后，再立刻接着执行consol.log(i)。
for循环执行完0-5之后，有了6个setTimeout的打印命令。
再加1得到6，i = 6不满足for循环，退出循环，循环结束。
此时setTimeout运行，进行6个setTimeout命令，并且获取了for循环之后的i = 6。
所以最后是打印出6个6。

想让程序打印出0、1、2、3、4、5，我们可以用for循环结合let。
```
for(let i = 0; i < 5; i++) {
  setTimeout(function () {
    console.log(i);
  }, 0)
}
```
或者
```
for(let i = 0; i < 6; i++){
  fn(i);
}
function fn(i){
  setTimeout(function(){
    console.log(i);
  }, 0)
}
```
