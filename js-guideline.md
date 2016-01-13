# JS 规范

基本原则

* 避免全局变量泛滥
* 代码可读性强
* 尽量遵循AMD规范
* 注释参考JsDoc注释规范

一、匿名函数

要避免全局变量泛滥， 可以考虑使用匿名函数， 把不需要在外部访问的变量或者函数限制在一个比较小的范围内。

/**推荐**/
<script>
    (function func1(){
        var list = ["a", "b", "c"];

        for(var i = 0; i < list.length; i++){
            //..
        };
    })(); //　自动运行
</script>

/**不推荐**/
<script>
    function func1(){
        var list = ["a", "b", "c"];

        for(var i = 0; i < list.length; i++){
            //..
        };
    }
    func1(); //　自动运行
</script>

匿名函数的格式：
(function(){
    // 代码块
})();
如果要带参数的话：
(function(arg1, arg2, argN){
    //..
})(arg1, arg2, argN);

二、命名空间

还有另外一个方法可以减少全局变量， 那就是命名空间， 在JS中可以用"对象-属性"来模拟命名空间；

/**推荐**/
var person = { 
	name: "credit"
	age: 16,
	eat: function(){}
}

/**不推荐**/
var name = "credit",
	age = 16,
	eat = function(){};

三、变量声明

变量必须在使用前用var进行声明；
变量的声明应该放在代码块或者函数的头部；
可在一行内声明多个变量， 但要考虑美观易读；
多个变量使用一个var，中间用","隔开；

/**推荐**/
var bankType = "中国银行",
	bankId = 622222222222;

/**不推荐**/
var bankType = "中国银行";
var bankId = 622222222222;

四、命名

普通变量名和函数名采用"小驼峰式命名法"， 如：firstName、lastName

五、符号

1.分号
每条语句必须使用分号结尾（特别是需要压缩的js，省略分号常常会导致压缩失败）；
2.大括号
if语句、函数定义、try语句等带大括号的结构， 左大括号应紧跟前面的部分：
/**推荐**/
var Person = function(){
    //..
}

/**不推荐**/
var Person = function()
{
    //..
}
使用复合语句时不要省略大括号{}
/**推荐**/
for(var i = 0; i < ary.length; i++){
    list.push(ary[i]);
}

/**不推荐**/
for(var i = 0; i < ary.length; i++)
    list.push(ary[i]);
以提高代码可读性为前提，允许例外：
if(!data) return;

if(row) list.push(row);

3.空格
数值操作符(如, +/-/*/% 等)、比较符（大于、小于、等于）两边留空格；
逗号、冒号、分号后要留一个空格（如果后面还有内容的话）；
行尾不要有空格;
点号前后不要出现空格；
函数名末尾和左括号之间不要出现空格；

4.引号
表示字符串用单引号或双引号均可， 建议统一使用双引号，
但表示html标签时一律使用单引号， 如：
var html = '<div class="msg" ></div>';