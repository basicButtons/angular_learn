# 搭建模拟服务器的方法
所要实现的功能：

1.我们可以自己创建db文件（存储的是对象）， 服务器返回的数据是json格式
2.该服务可以启动，就像网文一个远程服务器一样
3.这个服务器是在本地启动的
4.该服务器可以提供 RESTFUL API （GET POST PUT DELETE）

# 实现的方法

    借助： JSON SERVER 来搭建

1.下载安装 json-server 
    sudo npm install -g json-server

2.本地创建 db 文件， 这是一个 json 数据格式的文件。 注意文件的路径

    json 格式：
    key带有双引号 "" ，
    value不带有双引号 ,
    "key":value, ···
    
    但是我们在 Angular 中定义 class 的时候
    这个地方 key 是不带有双引号的
    以分号结尾。因为这个时候实际上一个类的定义，所以自然处理啦。
    数据类型：简单(primitive)数据类型全部都是小写。string，number and so on
            对象(object)数据类型首字母是大些。 Object，Array

3.启动服务
    启动数据库的指令，启动 json-server 并告诉json-server来监视我们所创建的db.json文件(一定要注意文件)
    执行方法：json-server --watch db.json (此时我们已经进入到 db.json 所在的路径) 

4.对数据库进行 CRUD (create read update delate)
    
    查：http://localhost:3000/products?id=1





