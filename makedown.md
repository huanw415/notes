## Makedown 是一种轻量级的标记语言, 它的目标就是实现: 易读易写, 成为一种适合于网络书写的语言.
## Markdown 的语法全由一些符号所组成, 并受到一些 text-to-HTML 格式的影响，包括 Setext、atx、Textile、reStructuredText、Grutatext 和 EtText，而最大灵感来源其实是纯文本电子邮件的格式。

## Makedown 是兼容HTML的, 它没有想要超过HTML, 它只涵盖了HTML的一小部分. 所以不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。不需要额外标注这是 HTML 或是 Markdown, 只要直接加标签就可以了.

1. 请注意，在 HTML 区块标签(<div>、<table>、<pre>、<p> 等标签)间的 Markdown 格式语法将不会被处理。比如，你在 HTML 区块内使用 Markdown 样式的*强调*会没有效果。
2. 和处在 HTML 区块标签间不同，Markdown 语法在 HTML 区段标签(如 <span>、<cite>、<del> )间是有效的。

## 特殊字符自动转换

1. 在 HTML 文件中，有两个字符需要特殊处理： < 和 & 。 < 符号用于起始标签，& 符号则用于标记 HTML 实体，如果你只是想要显示这些字符的原型，你必须要使用实体的形式，像是 &lt; 和 &amp;。
   例如:如果你要打「AT&T」 ，你必须要写成「AT&amp;T」。
   而网址中的 & 字符也要转换。比如你要链接到：
   http://images.google.com/images?num=30&q=larry+bird
   你必须要把网址转换写为：
   http://images.google.com/images?num=30&amp;q=larry+bird

2. Markdown 让你可以自然地书写字符，需要转换的由它来处理好了。如果你使用的 & 字符是 HTML 字符实体的一部分，它会保留原状，否则它会被转换成 &amp;。
例如: 书写AT&T, Markdown 就会将它自动转为：AT&amp;T

## 常用语法:
### 区块元素  
#### 标题
##### 支持两种格式: Setext 和 Atx. 对于Setext, 在文本下一行划入不限数量个====和-----分别来生成最高级标题(h1)和第二级标题(h2). 而对于Atx, 则使用1~6个#在文本之前来生成1~6级标题(h1~h6).  
##### 这是标题h1  
##### ================  
##### 这是标题h2  
##### ------------------
##### ### 这是标题h3  
##### ###### 这是标题h6
