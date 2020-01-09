# transform-markdown

# 使用
transform-markdown基于原生js开发，无需任何依赖，在页面中引入：
```html
<script src="transform-markdown.min.js"></script>
```
使用**默认样式**：
```html
<link rel="stylesheet" href="transform-markdown.min.css">
```
要使用代码高亮，可以配合**highlight.js**使用：
```html
<link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.11.0/styles/default.min.css">
<script src="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.11.0/highlight.min.js"></script>
```
highlight.js文档：[https://highlightjs.org/usage/](https://highlightjs.org/usage/)

使用解释器：
```html
<textarea id="mark"></textarea>
<div id="preview"></div>
```

```js
window.onload = function () {
    var markdown = new Reader();
    // 转义markdown
    markdown.renderHtml("```js \n var a=123 \n``` ");
    markdown.showHtml("preview");

    监听键盘事件实现实时解析：
    document.getElementById("mark").addEventListener("keyup", function () {
        const str = document.getElementById('mark').value
        markdown.renderHtml(str);
        markdown.showHtml("preview");
    });
};
```
