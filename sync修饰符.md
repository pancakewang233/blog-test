# sync修饰符
.sync 修饰符，只是作为一个编译时的语法糖存在，会被扩展为一个自动更新父组件属性的 v-on 监听器。当一个子组件改变了一个prop的值，这个变化也会同步到父组件中所绑定。

```html
<text-document
  v-bind:title="doc.title"
  v-on:update:title="doc.title = $event"
></text-document>
```

等价于：

```html
<text-document v-bind:title.sync="doc.title"></text-document>
```

