---
layout: post
title: "New Features in JDK"
description: "<p>我最初学习 Java 的时候，公司的大多数应用，都是基于 JDK 1.4.2.14，因此我也是从这个版本入手。搜索 ArrayList 的教程，发现诸如泛型的代码，对其中的 &lt; &gt; 甚是不解，请教同事，才知道就是 JDK5 引进的新功能，泛型。当是时，JDK6 已经发布了。</p><p>但公司为了稳定起见，不会着急更新。直到现在，核心应用都是还是 JDK6。</p><p>后来专门花了不少精力学习 JDK5 的新特性，除了泛型，还有自动封装箱，增强 for 循环，极大的提高了生产效率，至今印象深刻。</p><p>六年过去了，Java 早已易主，而 JDK8 的发布也指日可待，这里重新整理一下 JDK5 以来，Java 主版本的新功能，不能总是过着刀耕火种，茹毛饮血的生活。</p>"
category: java
tags: [java, jdk]
---
{% include JB/setup %}

我最初学习 Java 的时候，公司的大多数应用，都是基于 JDK 1.4.2.14，因此我也是从这个版本入手。搜索 ArrayList 的教程，发现诸如此类的代码：

```java
List<User> members = new ArrayList<User>();
members.add(new User());
...
```

对其中的 &lt; &gt; 甚是不解，请教同事，才知道就是 JDK5 引进的新功能，泛型。当是时，JDK6 已经发布了。

但公司为了稳定起见，不会着急更新。直到现在，核心应用都是还是 JDK6。

后来专门花了不少精力学习 JDK5 的新特性，除了泛型，还有自动封装箱，增强 for 循环，极大的提高了生产效率，至今印象深刻。

六年过去了，Java 早已易主，而 JDK8 的发布也指日可待，这里重新整理一下 JDK5 以来，Java 主版本的新功能，不能总是过着刀耕火种，茹毛饮血的生活。

## [Java Version History](http://en.wikipedia.org/wiki/Java_version_history)

1. JDK Alpha and Beta (1995)

2. JDK 1.0 (January 23, 1996)

3. JDK 1.1 (February 19, 1997)

4. J2SE 1.2 (December 8, 1998)

5. J2SE 1.3 (May 8, 2000)

6. J2SE 1.4 (February 6, 2002)

7. J2SE 5.0 (September 30, 2004)

8. Java SE 6 (December 11, 2006)

9. Java SE 7 (July 28, 2011)

## [JDK 5 Tiger](http://docs.oracle.com/javase/1.5.0/docs/)

[New Features and Enhancements J2SE 5.0](http://docs.oracle.com/javase/1.5.0/docs/relnotes/features.html)

- [Generics](http://docs.oracle.com/javase/1.5.0/docs/guide/language/generics.html)

- [Enhanced for Loop](http://docs.oracle.com/javase/1.5.0/docs/guide/language/foreach.html)

- [Autoboxing / Unboxing](http://docs.oracle.com/javase/1.5.0/docs/guide/language/autoboxing.html)

- [Typesafe Enums](http://docs.oracle.com/javase/1.5.0/docs/guide/language/enums.html)

- [Varargs](http://docs.oracle.com/javase/1.5.0/docs/guide/language/varargs.html)

- [Static Import](http://docs.oracle.com/javase/1.5.0/docs/guide/language/static-import.html)

- [Metadata (Annotations)](http://docs.oracle.com/javase/1.5.0/docs/guide/language/annotations.html)

[介绍 JDK 5.0 中的泛型](http://www.ibm.com/developerworks/cn/education/java/j-generics/)

[Tiger 中的注释，第 1 部分: 向 Java 代码中添加元数据](http://www.ibm.com/developerworks/cn/java/j-annotate1/)

[Tiger 中的注释，第 2 部分: 定制注释](http://www.ibm.com/developerworks/cn/java/j-annotate2.html)

## [JDK 6 Mustang](http://docs.oracle.com/javase/6/docs/)

[Features and Enhancements Java SE 6](http://www.oracle.com/technetwork/java/javase/features-141434.html)

- Improved User Experience

- Security Features and Enhancements

- Integrated Web Services

- Scripting Language Support (JSR223)

- Enhanced Management and Serviceability

- Increased Developer Productivity

-  Built in Apache Derby 

以下来自 达内 的培训课件：

- Desktop 类和 SystemTray 类

- 使用 JAXB2 来实现对象与 XML 之间的映射

- 理解 StAX 

- 使用 Compiler API

- 轻量级 HttpServer

- 插入式注解处理 API 

- 用 Console 开发控制台程序 

- 嵌入式数据库 Derby

- CommonAnnotations 

- Web 服务元数据 

- 更简单强大的 JAX-WS 

- 脚本语言支持

- JTable 的排序和过滤

[IBM Developerworks Java SE 6 新特性系列](http://www.ibm.com/developerworks/cn/java/j-lo-jse6/)

## [JDK 7 Dolphin](http://docs.oracle.com/javase/7/docs/)

[Java SE 7 Features and Enhancements](http://www.oracle.com/technetwork/java/javase/jdk7-relnotes-418459.html)

- Binary Literals

- [Strings in switch Statements](http://docs.oracle.com/javase/7/docs/technotes/guides/language/strings-switch.html)

- [The try-with-resources Statement](http://docs.oracle.com/javase/7/docs/technotes/guides/language/try-with-resources.html)

- [Catching Multiple Exception Types and Rethrowing Exceptions with Improved Type Checking](http://docs.oracle.com/javase/7/docs/technotes/guides/language/catch-multiple.html)

- Underscores in Numeric Literals

- [Type Inference for Generic Instance Creation](http://docs.oracle.com/javase/7/docs/technotes/guides/language/type-inference-generic-instance-creation.html)

- [Improved Compiler Warnings and Errors When Using Non-Reifiable Formal Parameters with Varargs Methods](http://docs.oracle.com/javase/7/docs/technotes/guides/language/non-reifiable-varargs.html)

- [JDBC 4.1](http://docs.oracle.com/javase/7/docs/technotes/guides/jdbc/jdbc_41.html)

中文资料

1. [OSchina Java 7 的新特性一览表](http://www.oschina.net/news/20119/new-features-of-java-7)

2. [Ken's blog](http://www.iamcoding.com/)

- [JDK7新特性一 概述](http://www.iamcoding.com/?p=19)

- [JDK7新特性二 语法](http://www.iamcoding.com/?p=83)

- [JDK7新特性三 JDBC4.1](http://www.iamcoding.com/?p=111)

- [JDK7新特性四 NIO2.0 文件系统](http://www.iamcoding.com/?p=114)

- [JDK7新特性五 fork/join 框架](http://www.iamcoding.com/?p=116)

- [JDK7新特性六 监听文件系统的更改](http://www.iamcoding.com/?p=125)

- [JDK7新特性七 遍历文件树](http://www.iamcoding.com/?p=128)

- [JDK7新特性八 异步io/AIO](http://www.iamcoding.com/?p=130)



 