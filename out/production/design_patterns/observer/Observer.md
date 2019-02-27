# Observer

## 动机（Motivation）
+ 在软件构建过程中，我们需要为某些对象建立一种“通知依赖关系” ——一个对象（目标对象）的状态发生改变，所有的依赖对
象（观察者对象）都将得到通知。如果这样的依赖关系过于紧密，将使软件不能很好地抵御变化。
+ 使用面向对象技术，可以将这种依赖关系弱化，并形成一种稳定的依赖关系。从而实现软件体系结构的松耦合。

## 模式定义
定义对象间的一种一对多（变化）的依赖关系，以便当一个对象(Subject)的状态发生改变时，所有依赖于它的对象都得到通知并自动更新。
——《 设计模式》 GoF


## 要点总结
+ 使用面向对象的抽象，Observer模式使得我们可以独立地改变目标与观察者，从而使二者之间的依赖关系达致松耦合。
+ 目标发送通知时，无需指定观察者，通知（可以携带通知信息作为参数）会自动传播。
+ 观察者自己决定是否需要订阅通知，目标对象对此一无所知。
+ Observer模式是基于事件的UI框架中非常常用的设计模式，也是MVC模式的一个重要组成部分。

---

### *个人注解*
+ 依赖是编译层面的依赖，A依赖B则编译时B要先存在。
+ [初级抽象]观察者为一个对象，类中方法将观察者作为一个参数传入
+ [高级抽象]观察者为一个对象，类中方法将观察者列表`observerList`作为一个参数传入,支持list的add和remove方法，自行订阅通知和取消订阅。
+ 以上抽象，观察者作为一个对象，在发生改变的时候可以发出通知（实现接口方法）而不受类的控制，同时所有订阅此类方法都会接收到通知（List中引用观察者对象）