# Web-Daily-Question
大前端每日一题，从基础到进阶，从原理到实战，系统构建前端完整的知识体系！
注：每天早上9点左右更新题目及前一天的答案！

今日一题：  

第49题(2019-09-27)：【编程题】已知数据结构users，请实现语法支持user.unique能够按照name字段去重，并输出结构为：["a","b"]
```  
var users=[{
   id:1,name:"a"
},{
   id:2,name:"a"
},{
   id:3,name:"b"
},{
   id:4,name:"v"
}]
Array.prototype.unique = function () {
    var res;
    this.map(item => {
        this[item.id - 1] = item.name
    })
    // ES6里新添加了两个很好用的东西，set和Array.from
    // set是一种新的数据结构，它可以接收一个数组或者是类数组对象，自动去重其中的重复项目。
    res=new Set(this);
    console.log("new Set对象",res)
    // 但是这里大家可以看到，set返回的是一个对象，但是我们想要的是数组啊。
    // 这回，就该轮到Array.from出场了，它的作用，就是可以把类数组对象、可迭代对象转化为数组。
    res=Array.from(new Set(this));
    return  res//es6 数组去重
}
console.log(users.unique());  
```

讨论与参考答案：[第49题](https://github.com/qappleh/Web-Daily-Question/issues/51)
  
更多每日一题及交流与讨论请点击[Issues](https://github.com/qappleh/Web-Daily-Question/issues)

推荐web程序员必备微信号 
▼

web夜读课
微信号：ydhlwnxs

推荐理由：web开发人员都在关注的公众号，在多学一点知识，就可以少写一行代码！专注于技术资源分享，经验交流，最新技术解读，另有海量免费电子书以及成套学习资源，关注web夜读课，做技术得先驱者。

 ▼长按下方↓↓↓二维码识别关注
 
![web夜读课公众号二维码](https://github.com/qappleh/Web-Daily-Question/blob/master/qrcode_for_gh_64b8beeaaf09_344.jpg)
