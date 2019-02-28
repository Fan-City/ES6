## ECMAScript 6 简介
### ECMAScript 和 JavaScript 的关系
ECMAScript 和 JavaScript 的关系是，前者是后者的规格，后者是前者的一种实现（另外的 ECMAScript 实现还有 Jscript 和 ActionScript）
> Typescript 实现了ECMAScript6 的特性，并且在此之上有进行扩展，所以有些特性并不是ECMAScript6的规范

### ES6 与 ECMAScript 2015 的关系
ES6 是一个泛指，含义是 5.1 版以后的 JavaScript 的下一代标准，涵盖了 ES2015、ES2016、ES2017 等等标准，这些标准都是在每年的 6 月份正式发布的，作为当年的正式版本。本文中提到 ES6 的地方，一般是指 ES2015 标准，
但有时也是泛指“下一代 JavaScript 语言”。

### 语法提案的批准流程
* Stage 0 - Strawman（展示阶段）
* Stage 1 - Proposal（征求意见阶段）
* Stage 2 - Draft（草案阶段）
* Stage 3 - Candidate（候选人阶段）
* Stage 4 - Finished（定案阶段）  

ECMAScript 当前的所有提案，可以在 TC39 的[官方网站](https://github.com/tc39/ecma262)查看。

### ECMAScript 的历史
ES6 从开始制定到最后发布，整整用了 15 年。  

* 1997 年：ECMAScript 1.0  
* 1998 年 6 月：ECMAScript 2.0  
* 1999 年 12 月：ECMAScript 3.0（3.0 版是一个巨大的成功，在业界得到广泛支持，成为通行标准，奠定了 JavaScript 语言的基本语法，以后的版本完全继承。直到今天，初学者一开始学习 JavaScript，其实就是在学 3.0 版的语法）  
* 2000 年：ECMAScript 4.0 开始酝酿 （这个版本最后没有通过，但是它的大部分内容被 ES6 继承了。因此，ES6 制定的起点其实是 2000 年）  
* 2007 年 10 月：ECMAScript 4.0 版草案发布  
* 2008 年 7 月：中止 ECMAScript 4.0 的开发，将其中涉及现有功能改善的一小部分，发布为 ECMAScript 3.1  
* 2009 年 12 月：ECMAScript 5.0 版正式发布  
* 2011 年 6 月：ECMAscript 5.1 版发布，并且成为 ISO 国际标准（ISO/IEC 16262:2011）  
* 2013 年 3 月：ECMAScript 6 草案冻结，不再添加新功能。新的功能设想将被放到 ECMAScript 7  
* 2013 年 12 月：ECMAScript 6 草案发布。然后是 12 个月的讨论期，听取各方反馈  
* 2015 年 6 月：ECMAScript 6 正式通过，成为国际标准  

### 部署进度
各大浏览器的最新版本，对 ES6 的支持可以查看此 [link](http://kangax.github.io/es5-compat-table/es6/)。
```
# 可以查看 Node 已经实现的 ES6 特性
$ node --v8-options | grep harmony
```
访问[es-checker](http://eschecker.michaelxu.cn/)，可以看到您的浏览器支持 ES6 的程度。

```
# 运行下面的命令，可以查看你正在使用的 Node 环境对 ES6 的支持程度
$ npm install -g es-checker
$ es-checker

=========================================
Passes 24 feature Dectations
Your runtime supports 57% of ECMAScript 6
=========================================
```

# 笔记
# ES6 新增特性
## let
不能重复申明

## const 
不能修改

## 变量解构附值
```
const a = {
    "a1":1,
    "a2":2
}
const { a1,a2 } = a;
```
## 模版字符串
```
let name = '代码君';
let a = `${name}你好吗？`
```
## 模块化
```
api.js
export const getData = {……}
export default { getData }

import getData from 'api.js'
```
## 类和继承
```
class Person {
 constructor(name,age){
     this.name = name;
     this.age = age;
  }
 sayHello(){
     console.log(`hello,my name is ${name},${age} `);
 }

class Student extends Person{
     constructor(name,age,score){
         super(name,age);
        this.score = score;
  }
   sayScore(){
     console.log(`hello,my name is ${name},${age},${score} `);
}
```