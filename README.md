# Web-Daily-Question
大前端每日一题，系统构建前端完整的知识体系！
注：每天早上9点左右更新题目及前一天的答案！

2019-07-22
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

2019-07-23：

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
推荐web程序员必备微信号 
▼

web夜读课
微信号：ydhlwnxs

推荐理由：web开发人员都在关注的公众号，在多学一点知识，就可以少写一行代码！专注于技术资源分享，经验交流，最新技术解读，另有海量免费电子书以及成套学习资源，关注web夜读课，做技术得先驱者。

 ▼长按下方↓↓↓二维码识别关注
 
![web夜读课公众号二维码](https://github.com/qappleh/Web-Daily-Question/blob/master/qrcode_for_gh_64b8beeaaf09_344.jpg)
