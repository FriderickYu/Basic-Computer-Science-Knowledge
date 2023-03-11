# Mapper代理

1. 定义与`SQL`映射文件同名的`Mapper`接口，并且将`Mapper`接口和`SQL`映射文件放置在同一个目录下
2. 设置`SQL`映射文件的`namespace`属性为`Mapper`接口全限定名
3. 在`Mapper`接口中定义方法，方法名就是`SQL`映射文件中`SQL`语句的`id`，并保持参数类型和返回值类型一致
4. 编码
   1. 通过`Sqlsession`的`getMapper`方法获取`Mapper`接口的代理对象
   2. 调用对应方法完成`SQL`的执行

正因为接口文件与映射文件放到了一个目录下，所以可以在配置文件中改变映射规则`<package name="com.ytq.mapper"/>`
