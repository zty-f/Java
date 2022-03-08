学习前言
--------

### 1.1 学习前提

熟练使用SpringBoot 微服务快速开发框架

了解过Dubbo + Zookeeper 分布式基础

电脑配置内存不低于8G(我自己的是16G)

![image-20210713094626568](C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210713094626568.png)

![image-20210713095227024](C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210713095227024.png)

### 1.2 文章大纲

Spring Cloud 五大组件

服务注册与发现——Netflix Eureka

负载均衡：

客户端负载均衡——Netflix Ribbon
服务端负载均衡：——Feign(其也是依赖于Ribbon，只是将调用方式RestTemplete 更改成Service 接口)
断路器——Netflix Hystrix

服务网关——Netflix Zuul

分布式配置——Spring Cloud Config





### 1.3 常见面试题

1.1 什么是微服务？

1.2 微服务之间是如何独立通讯的？

#### REST HTTP 协议         RPC TCP 协议    异步：消息中间件

1.3 SpringCloud 和 Dubbo有那些区别？

1.4 SpringBoot 和 SpringCloud，请谈谈你对他们的理解

1.5 什么是服务熔断？什么是服务降级？

1.6 微服务的优缺点分别是什么？说下你在项目开发中遇到的坑

1.7 你所知道的微服务技术栈有哪些？列举一二

1.8 Eureka和Zookeeper都可以提供服务注册与发现的功能，请说说两者的区别



### 什么是微服务？

就目前而言，对于微服务，业界并没有一个统一的，标准的定义。
但通常而言，微服务架构是一种架构模式，或者说是一种架构风格，它体长将单一的应用程序划分成一组小的服务，每个服务运行在其独立的自己的进程内，服务之间互相协调，互相配置，为用户提供最终价值，服务之间采用轻量级的通信机制(HTTP)互相沟通，每个服务都围绕着具体的业务进行构建，并且能狗被独立的部署到生产环境中，另外，应尽量避免统一的，集中式的服务管理机制，对具体的一个服务而言，应该根据业务上下文，选择合适的语言，工具(Maven)对其进行构建，可以有一个非常轻量级的集中式管理来协调这些服务，可以使用不同的语言来编写服务，也可以使用不同的数据存储。

再来从技术维度角度理解下：

**微服务化的核心**就是将传统的一站式应用，根据业务拆分成一个一个的服务，彻底地去耦合，每一个微服务提供单个业务功能的服务，一个服务做一件事情，从技术角度看就是一种小而独立的处理过程，类似进程的概念，能够自行单独启动或销毁，拥有自己独立的数据库。



1.4 微服务优缺点
----------------

优点

- 单一职责原则；

- 每个服务足够内聚，足够小，代码容易理解，这样能聚焦一个指定的业务功能或业务需求；

- 开发简单，开发效率高，一个服务可能就是专一的只干一件事；

- 微服务能够被小团队单独开发，这个团队只需2-5个开发人员组成；

- 微服务是松耦合的，是有功能意义的服务，无论是在开发阶段或部署阶段都是独立的；

- 微服务能使用不同的语言开发；

- 易于和第三方集成，微服务允许容易且灵活的方式集成自动部署，通过持续集成工具，如jenkins，Hudson，bamboo；

- 微服务易于被一个开发人员理解，修改和维护，这样小团队能够更关注自己的工作成果，无需通过合作才能体现价值；

- 微服务允许利用和融合最新技术；

- 微服务只是业务逻辑的代码，不会和HTML，CSS，或其他的界面混合;

- 每个微服务都有自己的存储能力，可以有自己的数据库，也可以有统一的数据库；

缺点

- 开发人员要处理分布式系统的复杂性；
- 多服务运维难度，随着服务的增加，运维的压力也在增大；
- 系统部署依赖问题；
- 服务间通信成本问题；
- 数据一致性问题；
- 系统集成测试问题；
- 性能和监控问题；

微服务技术栈有哪些？
--------------------

![image-20210713163813331](C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210713163813331.png)





![image-20210713164055656](C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210713164055656.png)



**Spring Cloud** 为开发者提供了快速构建分布式系统中一些常见模式的工具（例如配置管理、服务发现、熔断器、智能路由、微代理、控制总线、一次性令牌、全局锁、领导选举、分布式会话、集群状态）。分布式系统的协调导致了样板模式，使用 Spring Cloud 开发人员可以快速建立实现这些模式的服务和应用程序。它们将适用于任何分布式环境，包括开发人员自己的笔记本电脑、裸机数据中心和托管平台（如 Cloud Foundry）。

特征
----

Spring Cloud 专注于为典型用例和可扩展性机制提供良好的开箱即用体验以覆盖其他用例。

- 分布式/版本化配置
- 服务注册和发现
- 路由
- 服务到服务呼叫
- 负载均衡
- 断路器
- 全局锁
- 领导选举和集群状态
- 分布式消息传递

### 3.2 SpringCloud和SpringBoot的关系

- SpringBoot专注于快速方便的开发单个个体微服务；-jar

- SpringCloud是关注全局的微服务协调整理治理框架，它将SpringBoot开发的一个

- 个单体微服务，整合并管理起来，为各个微服务之间提供：配置管理、服务发现、断路器、路由、为代理、事件总栈、全局锁、决策竞选、分布式会话等等集成服务；

- SpringBoot可以离开SpringCloud独立使用，开发项目，但SpringCloud离不开

  SpringBoot，属于依赖关系；

  + SpringBoot专注于快速、方便的开发单个个体微服务，SpringCloud关注全局的服务治理框架；

### 3.3 Dubbo 和 SpringCloud技术选型

1. 分布式+服务治理Dubbo
目前成熟的互联网架构，应用服务化拆分 + 消息中间件

<img src="C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210713171907117.png" alt="image-20210713171907117" style="zoom: 200%;" />



### 3.4 SpringCloud能干嘛？

- Distributed/versioned configuration 分布式/版本控制配置
- Service registration and discovery 服务注册与发现
- Routing 路由
- Service-to-service calls 服务到服务的调用
- Load balancing 负载均衡配置
- Circuit Breakers 断路器
- Distributed messaging 分布式消息管理



SpringCloud没有采用数字编号的方式命名版本号，而是采用了**伦敦地铁站的名称**，同时根据字母表的顺序来对应版本时间顺序，比如最早的Realse版本：Angel，第二个Realse版本：Brixton，然后是Camden、Dalston、Edgware，目前最新的是Hoxton SR4 CURRENT GA通用稳定版。



自学参考书：
------------

SpringCloud Netflix 中文文档：https://springcloud.cc/spring-cloud-netflix.html
SpringCloud 中文API文档(官方文档翻译版)：https://springcloud.cc/spring-cloud-dalston.html
SpringCloud中国社区：http://springcloud.cn/
SpringCloud中文网：https://springcloud.cc







4.Eureka服务注册中心
--------------------

### 5.1 什么是Eureka

Netflix在涉及Eureka时，遵循的就是API原则.
Eureka是Netflix的有个子模块，也是核心模块之一。Eureka是基于REST的服务，用于定位服务，以实现云端中间件层服务发现和故障转移，服务注册与发现对于微服务来说是非常重要的，有了服务注册与发现，只需要使用服务的标识符，就可以访问到服务，而不需要修改服务调用的配置文件了，功能类似于Dubbo的注册中心，比如Zookeeper.

### 5.2 原理理解

Eureka基本的架构

Springcloud 封装了Netflix公司开发的Eureka模块来实现服务注册与发现 (对比Zookeeper).

Eureka采用了C-S的架构设计，EurekaServer作为服务注册功能的服务器，他是服务注册中心.

而系统中的其他微服务，使用Eureka的客户端连接到EurekaServer并维持心跳连接。这样系统的维护人员就可以通过EurekaServer来监控系统中各个微服务是否正常运行，Springcloud 的一些其他模块 (比如Zuul) 就可以通过EurekaServer来发现系统中的其他微服务，并执行相关的逻辑.



Eureka注册中心项目简单步骤：

1. 导入依赖

2. 编写配置文件
3. 开启这个功能@EnableXXXXXX
4. 配置类

<img src="C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210714190527163.png" alt="image-20210714190527163" style="zoom:200%;" />



<img src="C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210714190739319.png" alt="image-20210714190739319" style="zoom:200%;" />

6.Ribbon：负载均衡(基于客户端)
------------------------------

### 6.1 负载均衡以及Ribbon

**Ribbon是什么？**

Spring Cloud Ribbon 是基于Netflix Ribbon 实现的一套客户端负载均衡的工具。
简单的说，Ribbon 是 Netflix 发布的开源项目，主要功能是提供客户端的软件负载均衡算法，将 Netflix 的中间层服务连接在一起。Ribbon 的客户端组件提供一系列完整的配置项，如：连接超时、重试等。简单的说，就是在配置文件中列出 LoadBalancer (简称LB：负载均衡) 后面所有的及其，Ribbon 会自动的帮助你基于某种规则 (如简单轮询，随机连接等等) 去连接这些机器。我们也容易使用 Ribbon 实现自定义的负载均衡算法！
**Ribbon能干嘛？**

LB，即负载均衡 (LoadBalancer) ，在微服务或分布式集群中经常用的一种应用。
负载均衡简单的说就是将用户的请求平摊的分配到多个服务上，从而达到系统的HA (高用)。
常见的负载均衡软件有 Nginx、Lvs 等等。
Dubbo、SpringCloud 中均给我们提供了负载均衡，SpringCloud 的负载均衡算法可以自定义。
负载均衡简单分类：
**集中式LB**
即在服务的提供方和消费方之间使用独立的LB设施，如Nginx(反向代理服务器)，由该设施负责把访问请求通过某种策略转发至服务的提供方！
**进程式 LB**
将LB逻辑集成到消费方，消费方从服务注册中心获知有哪些地址可用，然后自己再从这些地址中选出一个合适的服务器。
Ribbon 就属于进程内LB，它只是一个类库，集成于消费方进程，消费方通过它来获取到服务提供方的地址！





7.Feign：负载均衡(基于服务端)
-----------------------------

### 7.1 Feign简介

**Feign**是声明式Web Service客户端，它让微服务之间的调用变得更简单，类似controller调用service。SpringCloud集成了Ribbon和Eureka，可以使用Feigin提供负载均衡的http客户端

只需要创建一个接口，然后添加注解即可~

Feign，主要是社区版，大家都习惯面向接口编程。这个是很多开发人员的规范。调用微服务访问两种方法

- 微服务名字 【ribbon】
- 接口和注解 【feign】
- Feign能干什么？

Feign旨在使编写Java Http客户端变得更容易
前面在使用Ribbon + RestTemplate时，利用RestTemplate对Http请求的封装处理，形成了一套模板化的调用方法。但是在实际开发中，由于对服务依赖的调用可能不止一处，往往一个接口会被多处调用，所以通常都会针对每个微服务自行封装一个客户端类来包装这些依赖服务的调用。所以，Feign在此基础上做了进一步的封装，由他来帮助我们定义和实现依赖服务接口的定义，在Feign的实现下，我们只需要创建一个接口并使用注解的方式来配置它 (类似以前Dao接口上标注Mapper注解，现在是一个微服务接口上面标注一个Feign注解)，即可完成对服务提供方的接口绑定，简化了使用Spring Cloud Ribbon 时，自动封装服务调用客户端的开发量。
Feign默认集成了Ribbon

利用Ribbon维护了MicroServiceCloud-Dept的服务列表信息，并且通过轮询实现了客户端的负载均衡，而与Ribbon不同的是，通过Feign只需要定义服务绑定接口且以声明式的方法，优雅而简单的实现了服务调用。




8.2 什么是Hystrix？
-------------------

 **Hystrix**是一个应用于处理分布式系统的延迟和容错的开源库，在分布式系统里，许多依赖不可避免的会调用失败，比如超时，异常等，Hystrix 能够保证在一个依赖出问题的情况下，不会导致整个体系服务失败，避免级联故障，以提高分布式系统的弹性。

 **“断路器”**本身是一种开关装置，当某个服务单元发生故障之后，通过断路器的故障监控 (类似熔断保险丝) ，向调用方返回一个服务预期的，可处理的备选响应 (FallBack) ，而不是长时间的等待或者抛出调用方法无法处理的异常，这样就可以保证了服务调用方的线程不会被长时间，不必要的占用，从而避免了故障在分布式系统中的蔓延，乃至雪崩。



#### 8.3 Hystrix能干嘛？

- 服务降级
- 服务熔断
- 服务限流
- 接近实时的监控
- …





#### 8.4 服务熔断

什么是服务熔断?
 熔断机制是赌赢雪崩效应的一种微服务链路保护机制。

 当扇出链路的某个微服务不可用或者响应时间太长时，会进行服务的降级，进而熔断该节点微服务的调用，快速返回错误的响应信息。检测到该节点微服务调用响应正常后恢复调用链路。在SpringCloud框架里熔断机制通过Hystrix实现。Hystrix会监控微服务间调用的状况，当失败的调用到一定阀值缺省是5秒内20次调用失败，就会启动熔断机制。熔断机制的注解是：@HystrixCommand。

服务熔断解决如下问题：

当所依赖的对象不稳定时，能够起到快速失败的目的；
快速失败后，能够根据一定的算法动态试探所依赖对象是否恢复。



#### 8.5 服务降级

什么是服务降级?
 服务降级是指 当服务器压力剧增的情况下，根据实际业务情况及流量，对一些服务和页面有策略的不处理，或换种简单的方式处理，从而释放服务器资源以保证核心业务正常运作或高效运作。说白了，就是尽可能的把系统资源让给优先级高的服务。

资源有限，而请求是无限的。如果在并发高峰期，不做服务降级处理，一方面肯定会影响整体服务的性能，严重的话可能会导致宕机某些重要的服务不可用。所以，一般在高峰期，为了保证核心功能服务的可用性，都要对某些服务降级处理。比如当双11活动时，把交易无关的服务统统降级，如查看蚂蚁深林，查看历史订单等等。

服务降级主要用于什么场景呢？当整个微服务架构整体的负载超出了预设的上限阈值或即将到来的流量预计将会超过预设的阈值时，为了保证重要或基本的服务能正常运行，可以将一些 不重要 或 不紧急 的服务或任务进行服务的 延迟使用 或 暂停使用。

降级的方式可以根据业务来，可以延迟服务，比如延迟给用户增加积分，只是放到一个缓存中，等服务平稳之后再执行 ；或者在粒度范围内关闭服务，比如关闭相关文章的推荐。






#### 8.6 服务熔断和降级的区别

服务熔断—>服务端：某个服务超时或异常，引起熔断~，类似于保险丝(自我熔断)
服务降级—>客户端：从整体网站请求负载考虑，当某个服务熔断或者关闭之后，服务将不再被调用，此时在客户端，我们可以准备一个 FallBackFactory ，返回一个默认的值(缺省值)。会导致整体的服务下降，但是好歹能用，比直接挂掉强。
触发原因不太一样，服务熔断一般是某个服务（下游服务）故障引起，而服务降级一般是从整体负荷考虑；管理目标的层次不太一样，熔断其实是一个框架级的处理，每个微服务都需要（无层级之分），而降级一般需要对业务有层级之分（比如降级一般是从最外围服务开始）
实现方式不太一样，服务降级具有代码侵入性(由控制器完成/或自动降级)，熔断一般称为自我熔断。
熔断，降级，限流：

限流：限制并发的请求访问量，超过阈值则拒绝；

降级：服务分优先级，牺牲非核心服务（不可用），保证核心服务稳定；从整体负荷考虑；

熔断：依赖的下游服务故障触发熔断，避免引发本系统崩溃；系统自动执行和恢复




#### 8.7 Dashboard 流监控



9.Zull路由网关
--------------



### 什么是zuul?

 Zull包含了对请求的路由(用来跳转的)和过滤两个最主要功能：

 其中路由功能负责将外部请求转发到具体的微服务实例上，是实现外部访问统一入口的基础，而过滤器功能则负责对请求的处理过程进行干预，是实现请求校验，服务聚合等功能的基础。Zuul和Eureka进行整合，将Zuul自身注册为Eureka服务治理下的应用，同时从Eureka中获得其他服务的消息，也即以后的访问微服务都是通过Zuul跳转后获得。



注意：Zuul 服务最终还是会注册进 Eureka

提供：代理 + 路由 + 过滤 三大功能！

Zuul 能干嘛？

- 路由
- 过滤



10.Spring Cloud Config 分布式配置
---------------------------------



**Spring Cloud Config为分布式系统中的外部配置提供服务器和客户端支持。**使用Config Server，您可以在所有环境中管理应用程序的外部属性。客户端和服务器上的概念映射与Spring Environment和PropertySource抽象相同，因此它们与Spring应用程序非常契合，但可以与任何以任何语言运行的应用程序一起使用。随着应用程序通过从开发人员到测试和生产的部署流程，您可以管理这些环境之间的配置，并确定应用程序具有迁移时需要运行的一切。服务器存储后端的默认实现使用git，因此它轻松支持标签版本的配置环境，以及可以访问用于管理内容的各种工具。很容易添加替代实现，并使用Spring配置将其插入。

### 概述

**分布式系统面临的–配置文件问题**

微服务意味着要将单体应用中的业务拆分成一个个子服务，每个服务的粒度相对较小，因此系统中会出现大量的服务，由于每个服务都需要必要的配置信息才能运行，所以一套集中式的，动态的配置管理设施是必不可少的。spring cloud提供了configServer来解决这个问题，我们每一个微服务自己带着一个application.yml，那上百个的配置文件修改起来，令人头疼！



### 什么是SpringCloud config分布式配置中心？



- spring cloud config 为微服务架构中的微服务提供集中化的外部支持，配置服务器为各个不同微服务应用的所有环节提供了一个中心化的外部配置。

-  spring cloud config 分为服务端和客户端两部分。

- 服务端也称为 分布式配置中心，它是一个独立的微服务应用，用来连接配置服务器并为客户端提供获取配置信息，加密，解密信息等访问接口。

- 客户端则是通过指定的配置中心来管理应用资源，以及与业务相关的配置内容，并在启动的时候从配置中心获取和加载配置信息。配置服务器默认采用git来存储配置信息，这样就有助于对环境配置进行版本管理。并且可用通过git客户端工具来方便的管理和访问配置内容。

### spring cloud config 分布式配置中心能干嘛？

#### **集中式管理配置文件**

不同环境，不同配置，动态化的配置更新，分环境部署，比如 /dev /test /prod /beta /release
运行期间动态调整配置，不再需要在每个服务部署的机器上编写配置文件，服务会向配置中心统一拉取配置自己的信息
当配置发生变动时，服务不需要重启，即可感知到配置的变化，并应用新的配置
将配置信息以REST接口的形式暴露
**spring cloud config 分布式配置中心与GitHub整合**

 由于spring cloud config 默认使用git来存储配置文件 (也有其他方式，比如自持SVN 和本地文件)，但是最推荐的还是git ，而且使用的是 http / https 访问的形式。





HTTP服务具有以下格式的资源：

```xml
/{application}/{profile}[/{label}]
/{application}-{profile}.yml
/{label}/{application}-{profile}.yml
/{application}-{profile}.properties
/{label}/{application}-{profile}.properties
```



11.GateWay 工作流程
===================

### gateway 三大理念

- 1.Predicate 断言
- 2.Route  路由
- 3.Filter  过滤器

gateway 核心：
1.路由转发
2.执行过滤链

filter 分为
pre 可以做日志记录 ，流量监控 ， 权限校验 等操作
post 可以做日志记录 ，流量监控 等操作

### Gateway能干什么



![在这里插入图片描述](https://img-blog.csdnimg.cn/20201105154909913.png#pic_center)

### 网关的3大核心概念



![在这里插入图片描述](https://img-blog.csdnimg.cn/20201105160939306.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3lhbmdzaGVuZ3dlaTIzMDYxMg==,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201105160709681.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3lhbmdzaGVuZ3dlaTIzMDYxMg==,size_16,color_FFFFFF,t_70#pic_center)



### SpringCloud Gateway的特性



![在这里插入图片描述](https://img-blog.csdnimg.cn/20201105155802180.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3lhbmdzaGVuZ3dlaTIzMDYxMg==,size_16,color_FFFFFF,t_70#pic_center)

### SpringCloud Gateway与zuul的区别



![4.](https://img-blog.csdnimg.cn/20201105160030273.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3lhbmdzaGVuZ3dlaTIzMDYxMg==,size_16,color_FFFFFF,t_70#pic_center)

