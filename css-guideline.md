# css书写规范

命名使用小写字母，复合单词用-连接，如xg-name

根据内容或功能来命名，皮肤类的命名可以加入表现，如skin-blue，其他不推荐根据表现来命名

使用.js-来命名js钩子，并且不应该为其写样式

id和class的命名长度应该适中，不要太简略也不要太详细

    #nav /* 推荐 */
    #navigation /* 不推荐 */

避免元素选择器和类选择器以及 id 选择器混用，例如

    /* 不推荐 */
    div#id
    div.class

    /* 推荐 */
    #id
    .class

为了防止冲突，对于应用特定的样式附加应用前缀

    /* 不推荐 */
    .title

    /* 推荐 */
    .section-title

避免css hack，考虑使用特定浏览器前缀表示

    /* 推荐 */
    .ie6 p { margin: 10px; }

    /* 不推荐 */
    p { _margin: 10px; }

尽可能的使用简写属性

* padding
* margin
* font
* background
* border
* border-radius

    /* 不推荐 */
    margin-top: 10px;
    margin-left: 10px;
    margin-right: 10px;
    margin-bottom: 10px;

    /* 推荐 */
    margin: 10px;

对属性值为 0 的情况省略单位

    /* 推荐 */
    margin: 0;

    /* 不推荐 */
    margin: 0px;

省略属性值中的 0 前缀

    /* 推荐 */
    font-size: .8em;

16进制的颜色值表示尽量使用3位表示

    /* 不推荐 */
    color: #eebbcc;

    /* 推荐 */
    color: #ebc;

为选择器分组时，将单独的选择器单独放在一行

    .selector, .selector-secondary {} /* 不推荐 */

    /* 推荐 */
    .selector,
    .selector-secondary {

    }

选择器 与 { 之间以及属性名的冒号之后应当包含空格,

    .selector {
        display: inline;
    }

>、+、~ 选择器的两边各保留一个空格

    #nav > li {}

列表型属性值 书写在单行时，逗号后必须跟一个空格

    font-family: Arial, sans-serif;

每条声明都应该独占一行

声明块的右花括号应当单独成行

单个属性都应该加上分号

    /* 推荐 */
    p {
        margin: 0;
    }

    /* 不推荐 */
    p {
        margin: 0
    }

相关的属性声明应当归为一组，并按照下面的顺序排列：

1. Positioning（定位）
2. Box model（盒模型）
3. Typographic（文本）
4. Visual（视觉）

    declaration-order {
        /* Positioning */
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        z-index: 100;

        /* Box-model */
        display: block;
        float: right;
        width: 100px;
        height: 100px;

        /* Typography */
        font: normal 13px "Helvetica Neue", sans-serif;
        line-height: 1.5;
        color: #333;
        text-align: center;

        /* Visual */
        background-color: #f5f5f5;
        border: 1px solid #e5e5e5;
        border-radius: 3px;

        /* Misc */
        opacity: 1;
    }

不要使用 @import

尽量不使用 !important 声明

禁止使用 expression

选择器的嵌套层级应不大于 3 级

对于无语义的标签，尽量少作为选择器出现

    <div id="demo"><span></span></div>

    /* 不推荐 */
    #demo span {}

    /* 推荐给span一个class或者id再书写样式 */

url() 函数中的路径不加引号

    body {
        background: url(//baidu.com/img/bg.png) no-repeat 0 0;
    }
