# Learn Spring

Bean相关
|注解|关联注解|实现方式|
|@Bean|@Configuration||

学习Spring的关键
1. 理解“注解派生性”。
2. 注解就相当于在业务开发中的功能需求，重点是理解加上注解之后程序如何将注解的作用发挥出来的
3. 包扫描
4. 扫描到不同的注解，spring会有什么不同的举动
5. 从 @SpringBootApplition 注解开始看起，该注解派生自其它若干个注解`注解的派生性（继承性）`
6. 要想明白源码中注解为何如此解析首先需要明白该注解是如何定义的`注解的定义很重要`
7. Spring之所以可以不用 web.xml ，做到所谓的约定大于配置，两方面原因在起作用：
    - 一是 servlet3.0 版本新增若干注解，使得 Servlet, Filter, Listener 可以不必声明在 xml 中，而是可以以类加注解的形式出现，这样web.xml 就不是必须的了。
    - 一是 WebApplicationInitializer 这个类，做了很多 web 容器初始化的工作。
8. spring 运维管理 spring-boot actuator （management.security.enabled = false）
    - [springboot(十九)：使用Spring Boot Actuator监控应用 - 纯洁的微笑博客](http://www.ityouknow.com/springboot/2018/02/06/spring-boot-actuator.html)
    - http://localhost:8080/beans 可以查看spring管理的beans
    - http://localhost:8080/env 查看profile等
9. @profile 派生自 @conditional

知识点
@Bean -> @Configuratiion
@Enbalexxx -> @Import
@Configuration 派生自 @Component
@Configuration 配合 @Bean 使用
@PropertySource("classpath:/jdbc.properties")  
@Value()

@Value("我是个普通字符串")
private String nornal;

@Value("#{systemEnvironment['os.name']}")
private String osName;

@Value("#{T(java.lang.Math).random()*1000.0}")
private double randomNumber;

@Value("#{demoService.anotherValue}")
private String anotherValue;

@Value("classpath:ch2/value/test.txt")
private Resource testFile;

@Value("http://www.baidu.com")
private Resource testUrl;

@Value("${book.name}")
private String bookName;

@ComponentScan(basePackages = "com.spring.test")
@ComponentScans
@Repeatable(ComponentScans.class) —— 来自Java8

@Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE)
1、singleton
2、prototype
3、request、session、global session（介绍）

@Bean
@Lookup 和 <lookup-method/>标签 改变单例类的属性


1. [【译】spring框架中的@Import注解 - 个人文章 - SegmentFault 思否](https://segmentfault.com/a/1190000011068471)

## 参考
1. [【 分类 】- Spring - dm_vincent的专栏（后端工程师，前端技术爱好者。） - CSDN博客](https://blog.csdn.net/dm_vincent/article/category/5632803)
2. [fangjian0423/springboot-analysis: 💥 something about springboot](https://github.com/fangjian0423/springboot-analysis)
3. [SpringBoot源码分析之SpringBoot的启动过程 | Format's Notes](https://fangjian0423.github.io/2017/04/30/springboot-startup-analysis/)
4. [Format's Notes](http://fangjian0423.github.io/)
5. [springboot 源码解析 - Google 搜索](https://www.google.com.hk/search?q=springboot+%E6%BA%90%E7%A0%81%E8%A7%A3%E6%9E%90&oq=springboot+%E6%BA%90%E7%A0%81%E8%A7%A3%E6%9E%90+&aqs=chrome..69i57j0.5858j0j7&sourceid=chrome&ie=UTF-8)
6. [Spring Boot自动配置的"魔法"是如何实现的？ | SylvanasSun's Blog](https://sylvanassun.github.io/2018/01/08/2018-01-08-spring_boot_auto_configure/)
7. [Spring Boot自动配置 - Google 搜索](https://www.google.com.hk/search?newwindow=1&safe=strict&ei=-28AXKDAOMiZ8gWJ6ZzIDg&q=Spring+Boot%E8%87%AA%E5%8A%A8%E9%85%8D%E7%BD%AE&oq=Spring+Boot%E8%87%AA%E5%8A%A8%E9%85%8D%E7%BD%AE&gs_l=psy-ab.3..0i7i30.90599.92582..92980...0.0..0.155.621.1j4......0....1..gws-wiz.......33i160.Nq1t7DBvyTw)
8. [Spring 框架的设计理念与设计模式分析](https://www.ibm.com/developerworks/cn/java/j-lo-spring-principle/index.html)
- [Spring 各种注解备注 - 个人文章 - SegmentFault 思否](https://segmentfault.com/a/1190000013094650)
- [spring 常用注解 - 程序园](http://www.voidcn.com/article/p-vnuuxhnq-bcq.html)
- [Spring常用注解介绍【经典总结】 - 阿飞(dufyun)的博客 - CSDN博客](https://blog.csdn.net/u010648555/article/details/76299467)
- [spring注解大全启用 - 筱进GG - CSDN博客](https://blog.csdn.net/zhaokejin521/article/details/50455651)