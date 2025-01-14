# Spring-boot 开发脚手架

## 项目介绍
提供快速的搭建spring，spring boot项目，提供spring boot阔展等，希望通过大家一起学习人人都可以堆各种组件当架构尸吓尿面试官，迎娶白富美（HRBP），该项目中大多数总结来自于抄袭一些优秀开源项目，比如pom依赖管理就是抄袭的
spring boot的项目管理方式。

## 功能介绍
集成tk-mybatis，并扩展了BaseService 和 LogicService(带逻辑删除)，提供日志记录，线程内MDC日志Id，统一的restful返回标准，基于tk-mybatis的逆向代码生成工具，提供基于redisson的注解式分布式锁DLock，提供自己扩展的
spring boot starter，提供springcloud统一数据解析和异常传递。

## 模块介绍

### easy-dependencies
该模块管理所有的jar包集成，整合spring boot和spring cloud等。

### easy-parent
该模块主要为其他模块和开发应用模块提供一个parent模块，使用类似于spring-boot-parent,在pom.xml中加入如下配置
```
  <parent>
        <artifactId>easy-parent</artifactId>
        <groupId>com.vartime.easy</groupId>
        <version>${VERSION}</version>
   </parent>
```

### easy-common
该模块是easy的一个基础模块，提供lombok，基础BaseObject(该基类有惊喜自带bean-copy懒人必备)和常用utils等工具

### easy-framework
该模块是easy的核心模块，提供spring的扩展等

### easy-spring-boot
该模块是对spring-boot的扩展，提供统一返回JSON格式，自定义过滤规则和swagger-ui-bootstrap等

### easy-spring-boot-tk-mybatis
该模块是对mapper-spring-boot-starter的一个扩展，新增了对基础LogicEntity实体，commonMapper，BaseService,BaseLogicService等实现

### easy-generator
该模块是代码生成器模块，当前该模块只是实现了对tk-mybatis自动生成代码做了扩展，大部分代码生成思路来自于drtrang，感谢drtrang[https://github.com/drtrang] 的开源工具，感谢大师我会继续抄袭的，并在该工具上做了逻辑删除等扩展，该模块下计划实现restful和vue模版代码常用curd生成。

### easy-spring-cloud-feign
该模块是实现之前代码中easy-spring-boot中提供了对接口的统一返回，原计划是在该模块中自动解包，实现异常传递等功能，该模块功能会在后续中补充

### easy-spring-boot-distributed-lock
该模块是基于redisson(redis的儿子这名字取得好奇怪)提供的RLock实现的基于注解形式的分布式锁(懒人必备)DLock，模块大部分思路和实现来自于开源工程klock，github[https://github.com/kekingcn/spring-boot-klock-starter] 该大师好久没维护了，我拿过来扩展了些功能，之后将介绍具体用法。
