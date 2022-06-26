# 创建对象的方法

## 1. new 一个对象

- ###### new 一个对象的过程 `Sheep sheep = new Sheep()`

  1. 类加载：当我们new一个对象时，JVM要首先检查这个符号引用所代表的类是否已经被加载过，如果没用被加载过就要执行相应的类加载过程。
  2. 声明类型引用：声明一个Sheep类型的引用sheep。
  3. 堆内存分配：JVM会在堆中为对象分配内存。
  4. 属性“0”值初始化：为实例化对象的各个属性默认初始化“0”值，如int的初始化“0”值就是0，二一个对象的初始化“0”值就是null。
  5. 对象头设置：主要包括对象的运行时数据（比如hash码、分代年龄、锁状态标志、锁指针、偏向时间戳等）以及类型指针（JVM通过该类型指针来确定该对象是哪个类的实例）。
  6. 属性显式初始化：定义一个类时，针对某个属性字段手动赋值，如`private String name = "codesheep"` ，就在这时候给初始化。
  7. 构造方法初始化：最后是调用类的构造方法来进行构造方法内描述的初始化动作。

  

  ## 2. 反射出一个对象

  -  通过反射机制，拿到类的class对象，然后创造对象。
  -  拿到class对象的三种方式
     - 类名.class
     - 对象名.class
     - Class.forName(全限定类名)
  -  调用`newInstance()`方法来创建一个对象，但是只能使用无参构造方法来创建对象

  ```java
  Sheep sheep3 = (Sheep) Class.forName( "cn.codesheep.article.obj.Sheep" ).newInstance();
  Sheep sheep4 = Sheep.class.newInstance();
  ```

  - 还有一种方法就是通过`java.lang.relect.Constructor`这个类的`newInstance()`方法来创建对象，因为它可以明确指定某个构造器来创建对象。

  

  

  

  

  ## 3.克隆一个对象

  