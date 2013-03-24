---
layout: post
title: "专注写作"
description: "<p>Scala 的学习曲线很陡，不过，学会之后，用起来应该很爽！</p><p>期待了三年的《<a href='http://manning.com/raychaudhuri/' target='_blank'>Scala in Action</a>》，三月会发布吗？</p>"
category: blog
tags: [java, scala]
---
{% include JB/setup %}

Scala 的学习曲线很陡，不过，学会之后，用起来应该很爽！

期待了三年的《[Scala in Action](http://manning.com/raychaudhuri/)》，三月会发布吗？

范例

```scala
object HelloWorld {
   def main(args: Array[String]) {
     println("Hello, world!")
   }
 }
 ```
或者

 {% highlight scala %}
  object HelloWorld extends App {
   println("Hello, world!")
 }
 {% endhighlight %}

 ----

附：

**Mac Shell javac 中文乱码**

在 MAC OS X 控制台下使用 javac 命令编译 Java 程序时，会出现乱码的情况，现提供一种解决办法：

打开终端( Terminal)窗口，点击桌面左上方的终端(Terminal) –> 偏好设置(Preferences) –> 设置 –> 高级 –> 字符编码 –> 简体中文(GB23112)。

是为测试。


