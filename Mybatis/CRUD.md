# 增删改查

## 配置文件增删改查

在配置文件中完成增删改查的操作，总是需要遵循以下的步骤：

1. 编写接口方法：`Mapper`接口
   1. 确定参数
   2. 确定返回类型
2. 编写`SQL`语句，还有对应的`SQL`映射文件
3. 执行方法，测试

如果`Java`类中属性与实际数据表列名不一样时，可以使用一下方法进行映射

```xml
<resultMap id="brandResultMap" type="com.ytq.pojo.Brand">
     <result column="brand_name" property="brandName"/>
     <result column="company_name" property="companyName"/>
 </resultMap>

<select id="selectAll" resultMap="brandResultMap">
  select * from tb_brand;
</select>
```

`column`其实就是代表数据库列名，`property`代表在实体类中的属性名；当然在`select`标签内需要返回`resultMap`中规定的`id`

## 注解完成增删改查
