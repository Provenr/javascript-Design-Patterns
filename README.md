<h1 align="center" style="margin: 30px 0 35px;">JavaScript设计模式与开发实践</h1>
<p align="center">
 <a href="https://travis-ci.org/github/Provenr/javascript-Design-Patterns"><img src="https://travis-ci.org/Provenr/javascript-Design-Patterns.svg?branch=master" /></a>
</p>

[在线地址]()

前端在软件开发过程中开始扮演越来越重要的角色，需要处理的业务越来越复杂，前端跟后端的差距也越来越小。

设计模式是对软件中普遍存在的各种问题所提出的解决方案，设计模式作为通用设计思想，可以极大的提高软件的扩展性、复用性和可维护性，那么设计模式将如何帮助前端工程师开发出更加优秀的软件产品呢？

《设计模式》一书共归纳了 <i class="focus">23</i> 种设计模式，这些设计模式被分为三大类: 创建型模式、结构型模式、行为型模式

本文为《JavaScripti 计模式与开发实践》一书的学习与思考。

## 基础知识

- [javascript 面向对象](/基础知识/面向对象.html)
- [this、bind、call、apply](/基础知识/this、bind、call、apply.html)
- [闭包和高阶函数](/基础知识/闭包和高阶函数.html)

## 设计模式

**创建型模式：** 封装创建对象的变化

- [工厂模式 Factory Pattern](/设计模式/工厂模式.html) 封装 new 构造函数
- [单例模式 Singleton Pattern](/设计模式/单例模式.html) 对象池

**结构型模式：** 封装对象之间的组合关系

- [外观模式 Facade Pattern](/设计模式/外观模式.html) utils；统一兼容接口
- [代理模式 Proxy Pattern](/设计模式/代理模式.html) 代理拦截；缓存机制提升性能
- [Mixin 模式 Mixin Pattern](/设计模式/Mixin模式.html) 多继承 mixin
- [装饰器模式 Decorator Pattern](/设计模式/装饰器模式.html) 对现有类进行一次包装，增加功能。 等同于 ES7 的 装饰器
- [适配器模式 Adapter Pattern](/设计模式/适配器模式.html) 接口等适配，达到统一目的
- [享元模式 Flyweight Pattern](/设计模式/享元模式.html) 对象池缓存共享
- [组合模式 Composite Pattern](/设计模式/组合模式.html) 树形结构，统一接口

**行为型模式：** 封装的对象的行为变化

- [策略模式 Strategy Pattern](/设计模式/策略模式.html) 同一类功能，定义不同逻辑算法，用户随意选择
- [命令模式 Command Pattern](/设计模式/命令模式.html) 封装一系列动作，例子很优秀呦
- [状态模式 State Pattern](/设计模式/状态模式.html) 多状态对象间相互固定切换
- [职责链模式 Chain Of Responsibility Pattern](/设计模式/职责链模式.html) 解耦紧密的 if-else 判断逻辑，可 AOP 实现
- [观察者模式 Observer Pattern](/设计模式/观察者模式.html) 发布订阅(发布者发送)
- [中介者模式 Mediator Pattern](/设计模式/中介者模式.html) 发布订阅(订阅者互发)
- [迭代器模式 Iterator Pattern](/设计模式/迭代器模式.html) ES6 Iterator | Generator
- [模板方法模式 Template Pattern](/设计模式/模板方法模式.html) 继承共用父类模板

## 设计原则和编程技巧

- [单一职责原则 Single Responsibility Principle](/设计原则和编程技巧/单一职责原则.html)
- [最少知识原则 Least Knowledge Principle](/设计原则和编程技巧/最少知识原则.html)
- [开放-封闭原则 Open-Closed Principle](/设计原则和编程技巧/开放-封闭原则.html)
- [依赖倒置原则 Dependence Inversion Principle](/设计原则和编程技巧/依赖倒置原则.html)
- [代码重构](/设计原则和编程技巧/代码重构.html)

## 补充文档

【1】[JavaScript Design Patterns](https://medium.com/better-programming/javascript-design-patterns-25f0faaaa15)

【2】[JavaScripti 计模式与开发实践](https://www.kancloud.cn/wengwang/read_1/436074)
