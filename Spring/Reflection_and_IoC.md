# 反射 Reflection

简而言之，通过反射，我们可以在**运行时**获得程序或程序集中每一个**类型的成员和成员的信息**。程序中一般的对象的类型都是在编译期就确定下来的，而 `Java` 反射机制可以动态地创建对象并调用其属性，这样的对象的类型在编译期是未知的。所以我们可以通过反射机制直接创建对象，即使这个对象的类型在编译期是未知的。

反射的核心是 `JVM` 在运行时才动态加载类或调用方法/访问属性，它不需要事先（写代码的时候或编译期）知道运行对象是谁。

Java 反射主要提供以下功能：

* 在运行时判断任意一个对象所属的类；
* 在运行时构造任意一个类的对象；
* 在运行时判断任意一个类所具有的成员变量和方法（通过反射甚至可以调用`private`方法）；
* 在运行时调用任意一个对象的方法

注意，是在**运行时，而非编译时**

## 获得Class对象

使用`Class`类的`forName`静态方法

`Class.forName(driver)`

直接获取某一个对象的`class`，比如：

`Class<?> klass = int.class;`

`Class<?> classInt = Integer.TYPE;`

调用某个对象的`getClass()`方法，比如

`StringBuilder str = new StringBuilder("123");`

`Class<?> klass = str.getClass();`

## 判断是否为某个类的实例

一般用`instanceof`来判断是否为某个类的实例。同时我们也可以借助反射中`Class`对象的`isInstance()`方法来判断是否为某个类的实例

## 创建实例

使用`Class`对象的`newInstance()`方法来创建`Class`对象对应类的实例

```
Class<?> c = String.class;
Object str = c.newInstance();
```

先通过`Class`对象获取指定的`Constructor`对象，再调用`Constructor`对象的`newInstance()`方法

```java
// 获取String所对应的Class对象
Class<?> c = String.class;
// 获取String类带一个String参数的构件器
Constructor constructor = c.getConstructor(String.class);
// 根据构造器创建实例
OIbject obj = constructor.newInstance("23333");
```

## 获取方法

获取某个`Class`对象的方法集合，主要有以下方法：

`getDeclaredMethods`方法返回类或接口声明的所有方法

`getMethods`方法返回某个类的所有公用方法

`getMethod`方法返回一个特定的方法

## 获取类的成员变量（字段）信息

* `getFiled`: 访问公有的成员变量
* `getDeclaredField`: 所有已声明的成员变量

[Spring的IoC容器为什么用反射，而不用new创建对象](https://blog.51cto.com/u_15281317/2942325)
