基于[Road To Coding](https://r2coding.com/#/README ) 学习的记录

## **计算机基础**

### 编程语言

- #### 语言基础

  - ##### 基础语法

    - ###### new 一个对象的过程 `Sheep sheep = new Sheep()`

      1. 类加载：当我们new一个对象时，JVM要首先检查这个符号引用所代表的类是否已经被加载过，如果没用被加载过就要执行相应的类加载过程。
      2. 声明类型引用：声明一个Sheep类型的引用sheep。
      3. 堆内存分配：JVM会在堆中为对象分配内存。
      4. 属性“0”值初始化：为实例化对象的各个属性默认初始化“0”值，如int的初始化“0”值就是0，二一个对象的初始化“0”值就是null。
      5. 对象头设置：主要包括对象的运行时数据（比如hash码、分代年龄、锁状态标志、锁指针、偏向时间戳等）以及类型指针（JVM通过该类型指针来确定该对象是哪个类的实例）。
      6. 属性显式初始化：定义一个类时，针对某个属性字段手动赋值，如`private String name = "codesheep"` ，就在这时候给初始化。
      7. 构造方法初始化：最后是调用类的构造方法来进行构造方法内描述的初始化动作。

    - ###### 反射出一个对象

      -  通过反射机制，拿到类的class对象，然后创造对象。
      - 拿到class对象的三种方式
        - 类名.class
        - 对象名.class
        - Class.forName(全限定类名)
      - 调用`newInstance()`方法来创建一个对象，但是只能使用无参构造方法来创建对象

      ```java
      Sheep sheep3 = (Sheep) Class.forName( "cn.codesheep.article.obj.Sheep" ).newInstance();
      Sheep sheep4 = Sheep.class.newInstance();
      ```

      - 还有一种方法就是通过`java.lang.relect.Constructor`这个类的`newInstance()`方法来创建对象，因为它可以明确指定某个构造器来创建对象。
      - 吧

    - ###### 克隆一个对象

    - 

  - ##### 面向对象

  - ##### 接口

  - ##### 容器

  - ##### 异常

  - ##### 泛型

  - ##### 反射

  - ##### 注解

  - ##### I/O

  - ##### 图形化（Swing）

- #### JVM

  - 类加载机制
  - 字节码执行机制
  - JVM内存模型
  - GC垃圾回收机制
  - JVM性能监控俞故障定位
  - JVM调优

- #### 并发/多线程

  - 并发编程基础
  - 线程池
  - 锁
  - 并发容器
  - 原子类
  - JUC并发工具类

### 数据结构与算法

- 数据结构

  - 字符串
  - 数组
  - 链表
  - 二叉树
  - 堆、栈、队列
  - 哈希

- 算法

  - 查看
  - 排序
  - 贪心
  - 分治
  - 动态规划
  - 回溯

### 计算机网络

- ARP协议
- IP/ICMP协议
- TCP/UDP协议
- DNS/HTTP/HTTPS协议
- Session/Cookie

### 数据库/SQL

- SQL语句书写
- SQL语句优化
- 事务以及隔离级别
- 索引
- 锁

### 操作系统

- 进程/线程
- 并发/锁
- 内存管理和调度
- I/O原理

### 设计模式

- 单例
- 工厂
- 代理
- 策略
- 模板方法
- 观察者
- 适配器
- 责任链
- 建造者

## **研发工具**

### 集成开发环境

- Eclipse
- Intellij IDEA
- VS Code

### Linux 系统

- Linux常用命令
- 基本shell脚本

### 代码管理工具

- Git
- SVN

### 项目管理/构建工具

- Maven
- Gradle

## **应用框架**

### 后端

- **Spring家族**

  - Spring

    - IoC
    - AOP

  - Spring MVC
  - Spring Boot

    - 自动配置、开箱即用
    - 整合web
    - 整合数据库（事务问题）
    - 整合权限

      - Shiro
      - Spring Security

    - 整合各种中间件

      - 缓存
      - MQ
      - RPC框架
      - NIO框架

- **服务器软件**

  - web服务器

    - Nginx

  - 应用服务器

    - Tomcat
    - Jetty
    - Undertow

- **中间件**

  - 缓存

    - Redis

      - 5大数据类型
      - 事务
      - 消息通知
      - 管道
      - 持久化
      - 集群

    - memcache

  - 消息队列

    - RocketMQ
    - RabbitMQ
    - Kafka

  - RC框架

    - Dubbo
    - gRPC
    - Thrift
    - Spring Cloud
    - Netty

- **数据库**

  - ORM框架

    - MyBatis
    - Hibernate
    - JPA

  - 连接池

    - Druid
    - HikariCP
    - C3P0

  - 分库分表

    - MyCat
    - Sharding-JDBC
    - Sharding-Sphere

- **搜索引擎**

  - ElasticSearch
  - Solr

- **分布式/微服务**

  - 服务发现/注册

    - Eureka
    - Consul
    - Zookeeer
    - Nacos

  - 网关

    - Zuul
    - Gateway

  - 服务调用(负载均衡)

    - Ribbon
    - Feign

  - 熔断/降级

    - Hystrix

  - 配置中心

    - Config
    - Apollo
    - Nacos

  - 认证和鉴权

    - Shrio
    - Spring Security
    - Oauth2
    - SSO

  - 分布式事务

    - JTA接口 --- Atomikos组件
    - 2PC、3PC
    - XA模式
    - TCC模式

      - tcc-transaction
      - ByteTCC
      - EasyTransaction
      - Seata

    - SAGA模式

      - ServiceComb
      - Seata

    - LCN模式

      - tx-lcn

  - 任务调度

    - Quartz
    - Elastic-Job

  - 链路追踪与监控

    - Zipkin
    - Sleuth
    - Skywalking

  - 日志分析与监控

    - ELK

      - ElasticSearch
      - Logstash
      - Kibana

- **虚拟化/容器化**

  - 容器技术

    - Docker
    - 容器编排技术

      - Kubernetes
      - Swarm

### 前端

- 基础套餐

  - 三大件

    - HTML
    - JavaScript
    - CSS

  - 基础库

    - JQuery
    - Ajax

- 模板框架

  - JSP/JSTL
  - Thymeleaf
  - FreeMarker

- z组件化框架

  - Node
  - VUE
  - React
  - Angular

## **运维知识**

### web服务器

- Nginx

### 应用服务器

- Tomcat/Jetty/Undertow

### CDN加速

### 持续集成/持续发布

- Jenkins

### 代码质量检查

- sonar

### 日志收集/分析

- ELK



## **学无止境**

### 徒手撕源码

### 光脚造轮子

### 闭眼睛深度调优

### 无惧面试官

## **平稳降落**

### 调平心态、注意健康

