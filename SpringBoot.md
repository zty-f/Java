Spring Boot
===========

![image-20200801031429514](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9naXRlZS5jb20vd29fYmVsbC9QaWN0dXJlQmVkL3Jhdy9tYXN0ZXIvaW1hZ2UvaW1hZ2UtMjAyMDA4MDEwMzE0Mjk1MTQucG5n?x-oss-process=image/format,png)

![![image-20200801031429514](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9naXRlZS5jb20vd29fYmVsbC9QaWN0dXJlQmVkL3Jhdy9tYXN0ZXIvaW1hZ2UvaW1hZ2UtMjAyMDA4MDEwMzE0Mjk1MTQucG5n?x-oss-process=image/format,png)

![image-20210710095805348](C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210710095805348.png)



![image-20210710100352032](C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210710100352032.png)



](C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210710095805348.png)



![image-20210710100352032](C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210710100352032.png)









dubbo   Jar包  java服务框架，提供高性能的RPC调用

# springboot+dubbo+zookeeper使用流程

![image-20210713155739834](C:\Users\86134\AppData\Roaming\Typora\typora-user-images\image-20210713155739834.png)





![å¨è¿éæå¥å¾çæè¿°](https://img-blog.csdnimg.cn/20210506205031902.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTYyOTI4NQ==,size_16,color_FFFFFF,t_70)





认识SpringSecurity
==================

Spring Security 是针对Spring项目的安全框架，也是Spring Boot底层安全模块默认的技术选型，他可以实现强大的Web安全控制，对于安全控制，我们仅需要引入 spring-boot-starter-security 模块，进行少量的配置，即可实现强大的安全管理！

记住几个类：

> - WebSecurityConfigurerAdapter：自定义Security策略
> - AuthenticationManagerBuilder：自定义认证策略
> - @EnableWebSecurity：开启WebSecurity模式

Spring Security的两个主要目标是 “认证” 和 “授权”（访问控制）。

**“认证”（Authentication）**

> 身份验证是关于验证您的凭据，如用户名/用户ID和密码，以验证您的身份。
>
> 身份验证通常通过用户名和密码完成，有时与身份验证因素结合使用。

**“授权” （Authorization）**

> 授权发生在系统成功验证您的身份后，最终会授予您访问资源（如信息，文件，数据库，资金，位置，几乎任何内容）的完全权限。
>
> 这个概念是通用的，而不是只在Spring Security 中存在。



# Shiro简介

###1.1、Shiro 是什么？

Apache Shiro 是 Java 的一个安全（权限）框架。

Shiro 可以非常容易的开发出足够好的应用，其不仅可以用在 JavaSE 环境，也可以用在 JavaEE 环境。

Shiro 可以完成：认证、授权、加密、会话管理、与Web 集成、缓存等。

下载地址

官网：http://shiro.apache.org/
github：https://github.com/apache/shiro

## 1.2、有哪些功能？

- **Authentication:身份认证/登录，验证用户是不是拥有相应的身份**



- **Authorization:授权，即权限验证，验证某个已认证的用户是否拥有某个权限；即判断用户是否能进行什么操作，如：验证某个用户是否拥有某个角色。或者细粒度的验证某个用户对某个资源是否具有某个权限**



- **Session Management:会话管理，即用户登录后就是一次会话，在没有退出之前，它的所有信息都在会话中；会话可以是普通JavaSE环境，也可以是Web 环境的**



- **Cryptography:加密，保护数据的安全性，如密码加密存储到数据库，而不是明文存储**



- **Web Support:Web 支持，可以非常容易的集成到Web 环境**



- **Caching:缓存，比如用户登录后，其用户信息、拥有的角色/权限不必每次去查，这样可以提高效率**



- **Concurrency:Shiro支持多线程应用的并发验证，即如在一个线程中开启另一个线程，能把权限自动传播过去**



- **Testing:提供测试支持**



- **“Run As”:允许一个用户假装为另一个用户（如果他们允许）的身份进行访问**



- **Remember Me:记住我，这个是非常常见的功能，即一次登录后，下次再来的话不用登录了**

### Shiro实现登录拦截

在ShiroConfig中的getShiroFilterFactoryBean方法中添加如下配置

- anon： 无需认证就可以访问
- authc： 必须认证了才能访问
- user： 必须拥有记住我功能才能用
- perms： 拥有对某个资源的权限才能访问
- role： 拥有某个角色权限
