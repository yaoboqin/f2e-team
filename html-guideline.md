# HTML 规范

基本原则

* 符合web标准
* 语义化
* 结构化
* 结构表现行为分离
* 兼容性优良
* 页面性能

页面文档类型统一使用HTML5 DOCTYPE

如

    <!doctype html>

编码声明方法遵循HTML5的规范.推荐使用 utf-8 编码

    <meta charset="utf-8">

非特殊情况下样式文件必须外链至head之间

非特殊情况下JavaScript文件必须外链至页面底部

引入样式文件或JavaScript文件时, 须略去默认类型声明, 写法如下:

    <link rel="stylesheet" href="">
    <style></style>
    <script src=""></script>

将表现，行为和结构分离：不要在 html 和模板中加入除了结构以外的东西

    <h1 style="font-size: 1em;">HTML sucks</h1> <!-- 不推荐 -->

使用符合语义的标签书写 HTML 文档, 选择恰当的元素表达所需的含义

如

    <div>title</div> <!-- 不推荐 -->
    <h2>title</h2> <!-- 推荐 -->

元素的标签和属性名必须小写, 属性值必须加双引号

如

    <A HREF='/'>Home</A> <!-- 不推荐 -->
    <a href="/">Home</a> <!-- 推荐 -->

标签要正确闭合，HTML5中，br img input meta等自闭和标签可以不用加上最后的/了

嵌套元素应当缩进一次

重要图片必须加上alt属性

给重要的元素和截断的元素加上title

能以背景形式呈现的图片, 尽量写入css样式中

推荐使用 fieldset legend 组织表单

必须为含有描述性表单元素(input, textarea)添加label

链接如果没有特殊要求，使用相对链接

    /path/a.htm <!-- 推荐 -->
    http://a.com/path/a.htm <!-- 不推荐 -->

书写链接地址时, 必须避免重定向，即须在URL地址后面加上/，例如：

    href="http://a.com/" <!-- 推荐 -->
    href="http://a.com" <!-- 不推荐 -->

去除不必要的空格，

特殊符号必须编码，如 < 必须写成&amp;lt;

class & id 参见 css书写规范

使用自定义属性与JavaScript进行数据交互，自定义属性格式为 data-xx

建议对超过10行的html模块进行注释

一般情况下内联元素中不可嵌套块级元素

尽可能减少标签的嵌套与数量

如果链接和当前页面一致则忽略链接的协议部分，例如

    <script src="//www.taobao.com/fp.js"></script>