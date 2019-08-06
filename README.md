# Web-Daily-Question
大前端每日一题，系统构建前端完整的知识体系！
注：每天早上9点左右更新题目及前一天的答案！

今日一题：  
编程题，根据以下要求，写一个数组去重函数（蘑菇街）  
```  
如传入的数组元素为[123, "meili", "123", "mogu", 123]，则输出：[123, "meili", "123", "mogu"]

如传入的数组元素为[123, [1, 2, 3], [1, "2", 3], [1, 2, 3], "meili"]，则输出：[123, [1, 2, 3], [1, "2", 3], "meili"]

如传入的数组元素为[123, {a: 1}, {a: {b: 1}}, {a: "1"}, {a: {b: 1}}, "meili"]，则输出：[123, {a: 1}, {a: {b: 1}}, {a: "1"}, "meili"] 
```

第1题(2019-07-22)
以下代码会输出什么
```
function fn(a) {
	console.log(a);
	var a = 2;
	function a() {}
	console.log(a);
}
fn(1);
```
答案：f a() { }  2  
解析：我们知道预解析阶段，变量声明和函数声明会提前，且变量名和函数名同名时，函数优先级高于变量，会覆盖变量，因此第一个输出的是f a(){ }，继续执行，会执行a=2，再输出的时候就会输出2，不理解的同学百度一下变量提升和函数提升

第2题(2019-07-23)：

a在什么情况下，控制台会输出hello world（答案不唯一）

```
var a = ?;
if(a == 1 && a == 2 && a == 3){
  console.log('Hello world!');
}

```
参考答案：
```
var a = {
        i: 1,
        toString: function () {
            return a.i++;
        }
    }  
```
解析：==比较的时候类型不一样会转换类型，Object类型会调用toString，array调用join，number调用valueOf，因此三种方式都可以实现，上面的答案为重写Object的toString的方式。

第3题(2019-07-24)：  

请使用原型链相关知识实现b继承n=1;c继承n=2;m=3

答案：
```
var obj = function(){}
obj.prototype.n = 1;
var b = new obj();
obj.prototype = {
	n:2,
	m:3
}
var c = new obj();
console.log(b.n,b.m,c.n,c.m)
```

第4题(2019-07-25)  
以下代码输出什么？
```
var a = 1 < 2 < 1 < 1 ? 3 ： 4；
var b = 3 < 2 < 1 < 1 ? 2 : 1;
console.log(a);
console.log(b);
```
答案：3  1  
解析：大于小于运算符优先级高于三目运算符，且从左往右执行
a的执行顺序如下：
第一步：1 < 2 为true
第二步：true < 1，这时true会转为1，false会转为0进行比较，因此这一步结果为false
第三步：fasle < 1，结果为true，因此a的结果是3
b的结果同理于a，不再写详细计算步骤。

第5题(2019-07-26)  
已知以下数组：  
编写一个程序将数组扁平化去并除其中重复部分数据，最终得到一个升序并且不重复的数组 
```
var arr = [ [11, 22, 22], [13, 14, 15, 15], [16, 17, 18, 19, [11, 12, [12, 13, [14] ] ] ], 12];
```
答案：
```  
//flat方法接受一个参数n,可以将深度为n的数组扁平化,然后去重并排序,去重可以用set,排序用sort
// 当然也可以使用递归等其他方法
var newArray = Array.from(new Set(arr.flat(Infinity))).sort((a,b) => a-b);
console.log(newArray);  
```

第6题(2019-07-29)  
```  
//实现一个函数add,满足下列输出结果
add(1); // 1
add(1)(2); // 3
add(1)(2)(3); // 6
add(1)(2,3); // 6
add(1,2)(3); // 6
add(1,2,3); // 6
```
答案：  
```  
function add(){
	var args = [...arguments];
	var fn = function(){
	   args.push(...arguments);
	   return fn;
	}
	fn.tostring = function(){
	    return args.reduce((x,y) => x + y)
	}
	return fn;
}
console.log(add(1,2)); // 3
console.log(add(1)(2)); // 3
console.log(add(1)(2)(3)); // 6
console.log(add(1,2,3)(4)); // 10
```  

第7题(2019-07-30)  
```  
['1', '2', '3'].map(parseInt) what & why ?   

```  
答案：[1, NaN, NaN]  
解析：
首先让我们回顾一下，map函数的第一个参数callback：
var new_array = arr.map(function callback(currentValue[, index[, array]]) { // Return element for new_array }[, thisArg])
这个callback一共可以接收三个参数，其中第一个参数代表当前被处理的元素，而第二个参数代表该元素的索引。

而parseInt则是用来解析字符串的，使字符串成为指定基数的整数。
parseInt(string, radix)
接收两个参数，第一个表示被处理的值（字符串），第二个表示为解析时的基数。

了解这两个函数后，我们可以模拟一下运行情况

parseInt('1', 0) //radix为0时，且string参数不以“0x”和“0”开头时，按照10为基数处理。这个时候返回1
parseInt('2', 1) //基数为1（1进制）表示的数中，最大值小于2，所以无法解析，返回NaN
parseInt('3', 2) //基数为2（2进制）表示的数中，最大值小于3，所以无法解析，返回NaN
map函数返回的是一个数组，所以最后结果为[1, NaN, NaN]

最后附上MDN上对于这两个函数的链接，具体参数大家可以到里面看
https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseInt
https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/map

推荐web程序员必备微信号 
▼

web夜读课
微信号：ydhlwnxs

推荐理由：web开发人员都在关注的公众号，在多学一点知识，就可以少写一行代码！专注于技术资源分享，经验交流，最新技术解读，另有海量免费电子书以及成套学习资源，关注web夜读课，做技术得先驱者。

 ▼长按下方↓↓↓二维码识别关注
 
![web夜读课公众号二维码](https://github.com/qappleh/Web-Daily-Question/blob/master/qrcode_for_gh_64b8beeaaf09_344.jpg)
