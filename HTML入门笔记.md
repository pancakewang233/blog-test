## HTML入门笔记1
<strong>HTML称为超文本标记语言</strong>，于1989年和HTTP,URL一起由CERN的Tim Berners-Lee发明。<br>
HTML 起手应该写<em> Emmet感叹号</em>，在vscode新建HTML文件，然后输入Emmet感叹号，会自动带出以下代码。
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```
#### 常用的表章节的标签有h1~h6、section、article、main、aside 等等。

h1~h6是标题标签，由大到小。<br>
section标签表示一个章节，通常多个一起使用。<br>
article标签表示一段完整文章内容，可以独立使用。<br>
main表示主体内容，一个页面只能有一个main。main是顶层标签，<br>
不能放在header，footer，nav，article等标签中。<br>
aside用来放置与网页或文章主要内容间接相关的部分。

#### 全局属性有class, contenteditable, hidden, id, style, tabindex等。

#### 常用的内容标签有a、strong、em、code、pre等。

a标签是超链接，可以在对应的文字图片上插入超链接。例如：
`<a href="www.qq.com">点击QQ</a>`<br>
em,strong都表示强调的意思，em是语气上的强调，strong是内容本质上的强调。<br>
code标签可以用来包含需要展示的代码，保持等宽。<br>
pre表示保留原来格式。

