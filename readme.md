# Learn Spring

> 学习Spring的关键是理解注解的“派生性”。

> Spring之所以可以不用 web.xml ，做到所谓的约定大于配置，两方面原因在起作用：
- 一是 servlet3.0 版本新增若干注解，使得 Servlet, Filter, Listener 可以不必声明在 xml 中，而是可以以类加注解的形式出现，这样web.xml 就不是必须的了。
- 一是 WebApplicationInitializer 这个类，做了很多 web 容器初始化的工作。

> spring 管理 （manager.security.enabled = false）
- http://localhost:8080/beans 可以查看spring管理的beans
- http://localhost:8080/env 查看profile等

