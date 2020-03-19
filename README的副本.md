# 应用场景

    获取到后台的数据，并展示在 web 页面上，数据来源 https://jsonplaceholder.typicode.com/photos

# 实现思路

    1.构建 angualr 工程

    2.引入（import） HttpClientModule 

    3.通过 observable  (可观察对象)，获得到server 的数据。

    4.通过订阅  （subscribe） 这个observable，给component 传输数据
    
    5.在组件的html，显示后台的数据，以card 样式展示出来。

    6.优化 创建一个 service 通过 service 注入，获取到后台的数据，

    7.service 给组件 提供数据。

#  创建符号

    $ng service xx

    @Injectable({
        providedIn: 'root'  //元数据
    })

    依赖注入（DI：Dependency injection）

    依赖：当一个“东西”运行时，需要依赖另外一个东西
    注入：把所依赖的东西拿过来

    一个 service 就是一个药方，药方的提供者就是（service）

    护士拿着药方，来完成注射（inject）
    root ： 把整个 service 放到一个dependency injection (DI系统)，而且对于所有的组件都是可用的。

# 实现思路
    
    1.创建一个 service

    2.在创建 service 中，调用httpClient(本身是一个service)

    3.service 都有一个返回值，返回一个 observable 