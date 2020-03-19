# 组件之间的事件绑定（event binding）

应用场景 parent 组件内嵌了一个 child component， child 的 complete 中又一个button
点击这个 button 然后将 child 中的数据传递给 parent component

此时数据流从自顶向下，变自底向上 child -> parent

用到的知识点： Output 、 EvenEmitter

实现思路：
    1.构建 child 组件的事件绑定
    2.构建 parent 组件的事件绑定
    3.实现两者的关联。

实现过程：
    为了美化，我们引入 bootstrap 到 index.html 中。

知识点：设计模式中的观察者模式， EventEmitter 是一个实现了观察这模式的对象， 他管理一系列的订阅者，并向其发布事件的对象。

观察者设计模式： 举例来说， server 返回的数据，放在一个地方，只有去取的时候才能拿到。

举例场景：
        报刊中心（分发中心）
        这里对应着不止一个订阅者。

        只有订阅的人才有资格拿到。

        有的框架中有十分明确的一个 obverser center 

        angualr 没有明确的 obverser center ，但是它有一个明确的 subscribe

        subscribe 本身是一个方法，用于订阅数据的变化。

注意：
        这里的 Output 是 child component 的输出

        @Input、@Output 都是以 child component 为参考物。

        @Input、@Output 都是定义在 child component 中的。