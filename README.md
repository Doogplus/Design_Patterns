# 设计模式

## 什么是设计模式
“每一个模式描述了一个在我们周围不断重复发生的问题，以及该问题的解决方案的核心。这样，你就能一次又一次地使用该方案而不必做重复劳动”。
——Christopher Alexander

## 如何解决复杂性？
+ 分解
  + 人们面对复杂性有一个常见的做法：即分而治之，将大问题分解为多个小问题，将复杂问题分解为多个简单问题。
+ 抽象
  + 更高层次来讲，人们处理复杂性有一个通用的技术，即抽象。由于不能掌握全部的复杂对象，我们选择忽视它的非本质细节，而去处理泛化和理想化了的对象模型。
  
  
## **面向对象设计原则**
1. 依赖倒置原则（DIP）
  + 高层模块(稳定)不应该依赖于低层模块(变化)，二者都应该依赖于抽象(稳定) 。
  + 抽象(稳定)不应该依赖于实现细节(变化) ，实现细节应该依赖于抽象(稳定)。
2. 开放封闭原则（OCP）
  + 对扩展开放，对更改封闭。
  + 类模块应该是可扩展的，但是不可修改。
3. 单一职责原则（SRP）
  + 一个类应该仅有一个引起它变化的原因。
  + 变化的方向隐含着类的责任。
4. Liskov 替换原则（LSP）
  + 子类必须能够替换它们的基类(IS-A)。
  + 继承表达类型抽象。
5. 接口隔离原则（ISP）
  + 不应该强迫客户程序依赖它们不用的方法。
  + 接口应该小而完备。
6. 优先使用对象组合，而不是类继承
  + 类继承通常为“白箱复用”，对象组合通常为“黑箱复用” 。
  + 继承在某种程度上破坏了封装性，子类父类耦合度高。
  + 而对象组合则只要求被组合的对象具有良好定义的接口，耦合度低。
7. 封装变化点
  + 使用封装来创建对象之间的分界层，让设计者可以在分界层的一侧进行修改，而不会对另一侧产生不良的影响，从而实现层次间的松耦合。
8. 针对接口编程，而不是针对实现编程
  + 不将变量类型声明为某个特定的具体类，而是声明为某个接口。
  + 客户程序无需获知对象的具体类型，只需要知道对象所具有的接口。
  + 减少系统中各部分的依赖关系，从而实现“高内聚、松耦合”的类型设计方案。

## 从封装变化角度对模式分类
### 组件协作：
+ [Template Method]()
+ [Observer/Event]()
+ [Strategy]()
### 单一职责：
+ [Decorator]()
+ [Bridge]()
### 对象创建:
+ [Factory Method]()
+ [Abstract Factory]()
+ [Prototype]()
+ [Builder]()
### 对象性能：(解决性能问题)
+ [Singleton]()
+ [Flyweight(享元模式)]()
### 接口隔离:
+ [Facade(门面模式)]()
+ [Proxy]()
+ [Mediator(中介者)]()
+ [Adapter]()

- facade:系统内、系统外
- proxy:无法直接调用，比如分布式
- adapter：老接口和新接口的对接
- Mediator：复杂耦合
### 状态变化：
+ [Memento(备忘录)]()
+ [State]()
### 数据结构：
+ [Composite(组合模式)]()
+ [Iterator]()
+ [Chain of Resposibility(职责链)]()
### 行为变化：
+ [Command]()
+ [Visitor]()
### 领域问题：
+ [Interpreter]()



## 现代较少用的模式
+ Builder
+ Mediator
+ Mementor //序列化替代
+ Iterator //泛型模板多态替代
+ Chain of Resposibility //数据结构
+ Command //有更好的替代
+ Visitor //前提条件太苛刻
+ Interpreter //小问题不需要复杂问题有标准化语义解析器

## 对象模型

继承：
```cpp
class A: B{
    //...
}
```
内存模型：A|B


组合对象
```cpp
class A{
    B b;
    //...
}
```
内存模型：A|B

组合指针
```cpp
class A{
    B* qb;
    //...
}
```
内存模型：A|? -> B

大部分设计模式采用的都是第三种方式解耦

## 什么时候不需要设计模式：

+ 代码可读性很差时
+ 需求理解还很浅时
+ 变化没有显现时
+ 不是系统的关键依赖点
+ 项目没有复用价值时
+ 项目将要发布时

## 经验之谈
+ 不要为了模式而模式
+ 关注抽象类&接口
+ 理清变化点和稳定点
+ 审视依赖关系
+ 要有Framework和Application的区隔思维
+ 良好的设计是演化的结果

#### 其他链接
+ 课程名称：GeekBand 李建忠 C++设计模式课程
+ 本套材料主要来源 [github/liu-jianhao/Cpp-Design-Patterns](https://github.com/liu-jianhao/Cpp-Design-Patterns)
+ 课程总结文章集合 [http://www.iocoder.cn/DesignPattern/good-collection/](http://www.iocoder.cn/DesignPattern/good-collection/)
