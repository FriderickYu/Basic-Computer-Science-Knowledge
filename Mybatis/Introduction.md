# 啥是MyBatis

`MyBatis`其实就是一个用于持久层的开发框架，用以代替`Java`的`JDBC`

持久层

* 负责将数据保存到数据库，的部分
* JavaEE三层架构：表现层、业务层、持久层

## 快速入门

1. 创建`user`表，添加数据
2. 创建模块，导入坐标
3. 编写`MyBatis`核心配置文件 --> 替换连接信息，解决硬编码问题
4. 编写`SQL`映射文件 --> 统一管理`SQL`语句，解决硬编码问题
5. 编码：
   1. 定义`POJO`类
   2. 加载核心配置文件，获取`SqlSessionFactory`对象
   3. 获取`SqlSession`对象，执行`SQL`语句
   4. 释放资源

## 文件结构

```java
MyBatis-demo
├─.idea
├─src
│  ├─main
│  │  ├─java
│  │  │  └─com
│  │  │      └─ytq
│  │  │          └─pojo
│  │  │          │  └─User.java
│  │  │          └─MyBatisDemo.java
│  │  └─resources
│  │  	└─logback.xml
│  │  	└─mybatis-config.xml
│  │  	└─UserMapper.xml
│  └─test
│      └─java
└─pom.xml
```

* `pom.xml`: 依赖文件，需要的`jar`都在这个文件里面添加所属的依赖
* `mybatis-config.xml`: 办好了对`MyBatis`系统的核心设置，包括了获取数据库连接实例的数据源；还有决定事务的`Mapper`文件
* `UserMapper.xml`: 在这个文件里编写具体的`CRUD`文件
* `MyBatisDemo.java`: 程序入口文件，主要是为了
  * 加载`MyBatis`和核心配置文件，获取`SqlSessionFactory`对象
  * 获取`SqlSession`对象，用它来执行`sql`
  * 执行`sql`
  * 释放资源
* `User.java`: 对数据表的建模映射
