# HTML常用标签
HTML常用的标签有超链接a、图片img、表格table标签等。

### a超链接标签
* 跳转外部页面
* 跳转内部锚点
* 跳转到邮箱电话

常用属性有href和target等
href的取值可以有：
1. 网址
//google.com
2. 路径
/a/b/c
3. 伪协议
javascript:伪代码
4. 邮箱手机号
5. id
href=#XXX

target的取值可以是：
1. 内置名字（新链接打开方式）
    * _blank
    * _top
    * _self
    * _parent
2. 程序员命名
    * window的name
    * iframe的name

### table表格标签

相关的标签有：
* table
* thead
* tbody
* tfoot
* tr
* th
* td

### img图片标签
发出get请求，展示一张照片

属性有：
* alt图片展示失败时表示
* height图片高度
* width图片宽度
* src图片地址

写网页经常需要控制图片不超过展示页面
```
img {
        max-width: 100%;
    }
```

### 前端工作需要有一定的耐心和信心！
