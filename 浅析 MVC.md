# 浅析 MVC

### 1. MVC 三个对象分别做什么，给出伪代码示例

   Model（数据模型），负责操作数据

   View（视图），负责所有UI界面

   Controller（控制器），负责其它

   ```js
   const Model={
       data:{
           n
       }        //保存数据
       //管理数据的用法
       create(){}      //增加数据
       remove(){}      //删除数据
       update(){}      //改变数据
       get(){}         //查看数据
   }
   
   
   const View={
       //管理元素，
       el
      //管理HTML
       html：
       init(){
       //需要刷新的元素
        v.el:
       }，
       //页面渲染
       render(){
           
       }
   }
   
   const Controller = {
       // 初始化相关操作
       init() {}
       
       // 用户操作的事件
       events
     
       // 绑定事件，响应用户操作
       bindEvent() {}
   }
   
   ```

   

### 2. EventBus 有哪些 API，是做什么用的，给出伪代码示例

   ·1、什么是EventBus?

   简单的说，就是一个以事件为驱动的消息服务总线

   ·2、Web平台运行期为什么要用EventBus？

   - 便于业务逻辑解耦
   - 提供丰富的扩展点，包括前扩展、后扩展和覆盖
   - 使用事件驱动，让事件触发更加清晰
   - 让代码更加简洁清楚

   ·3、Web平台运行期在那些地方使用了EventBus？

   - 业务逻辑调度中心，包括前端、Web服务端任何地方
   - 通过EventBus集成各种超类、模板、页面
   - 通过EventBus集成各种系统服务与业务组件

   ·4、EventBus 有哪些 API?

   - on : 监听事件
   - trigger(emit) : 触发事件
   - off : 取消监听

   ```js
   //EventBus.js
   class EventBus {
       constructor() {
           this._eventBus = $(window)
       }
       on(eventName, fn) {
           return this._eventBus.on(eventName, fn)
       }
       trigger(eventName, data) {
           return this._trigger.trigger(eventName, data)
       }
       off(eventName, fn) {
           return this._eventBus.off(eventName, fn)
       }
   }
   export default EventBus
   //new.js
   import EventBus from 'EventBus.js'
   const e = new EventBus()
   e.on()
   e.trigger()
   e.off()
   ```

   

### 3. 表驱动编程是做什么的

   所谓表驱动法(Table-Driven Approach),简单讲是指用查表的方法获取值。最常见的就是哈希表。
   我们平时查字典就是典型的表驱动法。在数值不多的时候我们可以用逻辑语句(if 或case)的方法来获取值,但随着数值的增多逻辑语句就会越来越长,此时表驱动法的优势就显现出来了。

   ```js
   const day = new Date().getDay()
   let selectedDay;
   if(day === 0){
       selectedDay = '星期日'
   }else if(day === 1) {
       selectedDay = '星期一'
   }
   ...
   else{
       selectedDay = '星期六'
   }
   
   // 或者 用 switch case
   switch(day) {
       case 0:
           selectedDay = '星期日'
           break;
       case 1:
           selectedDay = '星期一'
           break;
           ...
   }
   ```

   而用表驱动编程则更简单：

   ```js
   const week = ['星期日', '星期一',..., '星期六']
   const day = new Date().getDay()
   const selectedDay = week[day]
   ```

   

### 4. 我是如何理解模块化的

    1、代码模块化之后无论是代码的整体性还是后期进行代码维护都变的清晰简单了起来。
    2、业务模块化之后可以使业务流程更为清晰，便于开展工作，各个业务模块之间负责自己模块的业务，也避免了一些不必要的麻烦，使得工作的效率也会更高。
    3、模块化是一种高效的思想，这在编程过程中提供了一种优化代码以及重构代码的方向。

