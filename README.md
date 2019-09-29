# Web-Daily-Question
大前端每日一题，从基础到进阶，从原理到实战，系统构建前端完整的知识体系！
注：每天早上9点左右更新题目及前一天的答案！

今日一题：  

第50题(2019-09-29)：已知如下对象，请基于es6的proxy方法设计一个属性拦截读取操作的例子，要求实现去访问目标对象example中不存在的属性时，抛出错误：Property "$(property)" does not exist
```  
const man={
    name:'jscoder',
    age:22
}
 //补全代码
const proxy = new Proxy(...)
proxy.name //"jscoder"
proxy.age //22
proxy.location //Property "$(property)" does not exist
```

讨论与参考答案：[第50题](https://github.com/qappleh/Web-Daily-Question/issues/52)
  
更多每日一题及交流与讨论请点击[Issues](https://github.com/qappleh/Web-Daily-Question/issues)

推荐web程序员必备微信号 
▼

web夜读课
微信号：ydhlwnxs

推荐理由：web开发人员都在关注的公众号，在多学一点知识，就可以少写一行代码！专注于技术资源分享，经验交流，最新技术解读，另有海量免费电子书以及成套学习资源，关注web夜读课，做技术得先驱者。

 ▼长按下方↓↓↓二维码识别关注
 
![web夜读课公众号二维码](https://github.com/qappleh/Web-Daily-Question/blob/master/qrcode_for_gh_64b8beeaaf09_344.jpg)
