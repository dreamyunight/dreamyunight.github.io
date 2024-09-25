[Trilium-SyntaxHighlightWidget](https://github.com/antoniotejada/Trilium-SyntaxHighlightWidget)

**trilium不支持代码块高亮，大佬提供了相关实现方法，不过我一开始并没有理解如何使用，研究之后我成功完成并决定写一个文档，因为全网基本找不到相关教程。**

很简单，首先，使用[SyntaxHighlightWidget.js](https://github.com/antoniotejada/Trilium-SyntaxHighlightWidget/blob/main/SyntaxHighlightWidget.js)的内容和标签 #widget 创建 JS Frontend 类型的代码注释：

![SyntaxHightWidget](https://github.com/dreamyunight/dreamyunight.github.io/blob/main/static/trilium%E4%BB%A3%E7%A0%81%E9%AB%98%E4%BA%AE/SyntaxHightWidget.png?raw=true)

![js](https://github.com/dreamyunight/dreamyunight.github.io/blob/main/static/trilium%E4%BB%A3%E7%A0%81%E9%AB%98%E4%BA%AE/js.png?raw=true)

![widget](https://github.com/dreamyunight/dreamyunight.github.io/blob/main/static/trilium%E4%BB%A3%E7%A0%81%E9%AB%98%E4%BA%AE/widget.png?raw=true)

然后，将[highlight.min.js](https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.5.1/highlight.min.js)文件附加到该注释：

```text-x-sh
wget https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.5.1/highlight.min.js
```

可以获取到这个文件，然后：

![importfile](https://github.com/dreamyunight/dreamyunight.github.io/blob/main/static/trilium%E4%BB%A3%E7%A0%81%E9%AB%98%E4%BA%AE/importfile.png?raw=true)

在此处使用import files将[highlight.min.js](https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.5.1/highlight.min.js)文件导入，注意：

![choose](https://github.com/dreamyunight/dreamyunight.github.io/blob/main/static/trilium%E4%BB%A3%E7%A0%81%E9%AB%98%E4%BA%AE/choosesetting.png?raw=true)

导入时，记得将选项中的Safe import勾选项去掉。

完成后Ctrl+R刷新一下就可以正常使用了。  


因为原版的配色更适合浅色主题，你也可以选择修改配色方案，只需要替换主脚本文件顶部 `CONST` 中 `<style>` 标记之间的样式表，我目前使用的是这个配色方案：

```text-css
pre code.hljs {
    display: block;
    overflow-x: auto;
    padding: 1em
}

code.hljs {
    padding: 3px 5px
}

.hljs {
    background: #fff;
    color: #000
}

.hljs-comment,
.hljs-quote,
.hljs-variable {
    color: green
}

.hljs-built_in,
.hljs-keyword,
.hljs-name,
.hljs-selector-tag,
.hljs-tag {
    color: rgb(111, 130, 255)
}

.hljs-addition,
.hljs-attribute,
.hljs-literal,
.hljs-section,
.hljs-string,
.hljs-template-tag,
.hljs-template-variable,
.hljs-title,
.hljs-type {
    color: #a24ba2
}

.hljs-deletion,
.hljs-meta,
.hljs-selector-attr,
.hljs-selector-pseudo {
    color: #5399ae
}

.hljs-doctag {
    color: rgb(220, 232, 140))
}

.hljs-attr {
    color: red
}

.hljs-bullet,
.hljs-link,
.hljs-symbol {
    color: #00b0e8
}

.hljs-emphasis {
    font-style: italic
}

.hljs-strong {
    font-weight: 700
}
```