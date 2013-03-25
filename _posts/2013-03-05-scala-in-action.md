---
layout: post
title: "Scala in Action"
description: "<p>Scala 的学习曲线很陡，不过，学会之后，用起来应该很爽！</p><p>期待了三年的《<a href='http://manning.com/raychaudhuri/' target='_blank'>Scala in Action</a>》，三月会发布吗？</p><p style='text-align:justify; text-justify:inter-ideograph'>Even within a single application, programming problems often lend themselves to a particular style of programming — functional, imperative, dynamic — but most programming languages require you to choose a single approach before you start. Scala provides a more flexible option. Scala is a statically typed programming language that blends the object oriented and functional programming models, giving you the flexibility to use the right approach for each specific case. And it's really good! Scala's type system is one of the best out there, and its type inference allows you to write succinct type safe code, crucial for large enterprise teams. Because Scala runs on the JVM, it's immediately practical for any Java shop to start using Scala.</p><p style='text-align:justify; text-justify:inter-ideograph'>Scala in Action is a comprehensive tutorial that introduces Scala through clear explanations and numerous hands-on examples. Because Scala is a rich and deep language, it can be daunting to absorb all the new concepts at once. This book takes a how-to approach, explaining language concepts as you explore familiar programming challenges that you face in your day-to-day work.</p><p style='text-align:justify; text-justify:inter-ideograph'>You won't just get the theory of functional programming. Instead, you'll learn to do concurrent programming using Scala's Actors and Akka libraries. You won't just discuss integration strategies, you'll learn to effectively mix Scala and Spring. You won't just talk about ways to simplify programming, you'll learn to build DSLs and other productivity tools.</p>"
category: book
tags: [java, scala]
---
{% include JB/setup %}

<table class="table"><tr>
	<td>
	<a href="http://www.manning.com/raychaudhuri/" target="_blank"><img src="http://www.manning.com/raychaudhuri/raychaudhuri_cover150.jpg" alt="Cover"></a></td>
	<td>
		<h3>Beginning Scala</h3>
<h5>Written by Lift Scala web framework founder and lead</h5>

<p>By Nilanjan Raychaudhuri</p>

<p>Publisher: Manning</p>

<p>Softbound print: March 2013 (est.)</p>

<p>Pages: 525</p>
</td></tr></table>

<p style='text-align:justify; text-justify:inter-ideograph'>Even within a single application, programming problems often lend themselves to a particular style of programming — functional, imperative, dynamic — but most programming languages require you to choose a single approach before you start. Scala provides a more flexible option. Scala is a statically typed programming language that blends the object oriented and functional programming models, giving you the flexibility to use the right approach for each specific case. And it's really good! Scala's type system is one of the best out there, and its type inference allows you to write succinct type safe code, crucial for large enterprise teams. Because Scala runs on the JVM, it's immediately practical for any Java shop to start using Scala.</p>

<p style='text-align:justify; text-justify:inter-ideograph'>Scala in Action is a comprehensive tutorial that introduces Scala through clear explanations and numerous hands-on examples. Because Scala is a rich and deep language, it can be daunting to absorb all the new concepts at once. This book takes a "how-to" approach, explaining language concepts as you explore familiar programming challenges that you face in your day-to-day work.</p>

<p style='text-align:justify; text-justify:inter-ideograph'>You won't just get the theory of functional programming. Instead, you'll learn to do concurrent programming using Scala's Actors and Akka libraries. You won't just discuss integration strategies, you'll learn to effectively mix Scala and Spring. You won't just talk about ways to simplify programming, you'll learn to build DSLs and other productivity tools.</p>


#####Part 1 Scala: the basics 

1. Why Scala?
2. Getting Started
3. OOP in Scala
4. Having fun with functional data structures
5. Functional programming

#####Part 2 Working with Scala 

6. Building web application in functional style
7. Connecting to a database
8. Building scalable and extensible components
9. Making concurrent programming easy with actors
10. Building confidence with testing

#####Part 3 Advanced Steps 

11. Interoperability between Scala and Java
12. Scalable and distributed applications using Akka

----

Scala 的学习曲线很陡，不过，学会之后，用起来应该很爽！

期待了三年的《[Scala in Action](http://manning.com/raychaudhuri/)》，三月会发布吗？

----

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


