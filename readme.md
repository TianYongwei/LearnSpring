# Learn Spring

> 学习Spring的关键是理解“注解派生性”。

> Spring之所以可以不用 web.xml ，做到所谓的约定大于配置，两方面原因在起作用：
- 一是 servlet3.0 版本新增若干注解，使得 Servlet, Filter, Listener 可以不必声明在 xml 中，而是可以以类加注解的形式出现，这样web.xml 就不是必须的了。
- 一是 WebApplicationInitializer 这个类，做了很多 web 容器初始化的工作。

> spring 运维管理 spring-boot actuator （management.security.enabled = false）

- [springboot(十九)：使用Spring Boot Actuator监控应用 - 纯洁的微笑博客](http://www.ityouknow.com/springboot/2018/02/06/spring-boot-actuator.html)
- http://localhost:8080/beans 可以查看spring管理的beans
- http://localhost:8080/env 查看profile等

## 参考
- [【 分类 】- Spring - dm_vincent的专栏（后端工程师，前端技术爱好者。） - CSDN博客](https://blog.csdn.net/dm_vincent/article/category/5632803)