---
layout: post
title: "Class Loaded and Initialized"
description: "<p>As we know .java file is first compiled to .class file at compile time. And we know Java can load a class at run time.</p><p>The confusion is what is the difference between 'load' and 'initialize'. When and how is a Java class loaded and initialized?</p><p>What does it mean by saying 'load a class' ?</p>"
category: java
tags: [class, java]
---
{% include JB/setup %}

As we know .java file is first compiled to .class file at compile time. And we know Java can load a class at run time.

The confusion is what is the difference between “load” and “initialize”. When and how is a Java class loaded and initialized?

## What does it mean by saying “load a class”?

C/C++ is compiled to native machine code first and then it requires a linking step after compilation. What the linking does is combining source files from different places and form an executable program. Java does not do that. The linking-like step for Java is done when they are loaded into JVM.

Different JVMs load classes in different ways, but the basic rule is only loading classes when they are needed. If there are some other classes that are required by the loaded class, they will also be loaded. The loading process is recursive.

## When and how is a Java class loaded?

In Java, loading policies is handled by a ClassLoader. I will create an example to show how and when class is loaded for that sample program.

TestLoader.java

```java
package compiler;
public class TestLoader {
	public static void main(String[] args) {
		System.out.println("test");
	}
}
```

A.java

```java
package compiler;
public class A {
	public void method(){
		System.out.println("inside of A");
	}
}
```

Here is the directory hierarchy in eclipse:

```
|-src
|—–compiler
|————–A.java
|————–TestLoader.java
```

By running the following command, we can get information about each class loaded.

`java -verbose:class -classpath /home/ron/workspace/UltimateTest/bin/ compiler.TestLoader`

The “-verbose:class” option displays information about each class loaded.

Part of output:

```
… …
[Loaded sun.misc.JavaSecurityProtectionDomainAccess from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
[Loaded java.security.ProtectionDomain$2 from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
[Loaded java.security.ProtectionDomain$Key from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
[Loaded java.security.Principal from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
[Loaded compiler.TestLoader from file:/home/xiwang/workspace/UltimateTest/bin/]
test
[Loaded java.lang.Shutdown from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
[Loaded java.lang.Shutdown$Lock from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
```

Now If we change TestLoader.java to the following:

TestLoader.java

```java
package compiler;
public class TestLoader {
	public static void main(String[] args) {
		System.out.println("test");
		A a = new A();
		a.method();
	}
}
```
And run the same command again, the output would be the following:

```
Part of output:
… …
[Loaded sun.misc.JavaSecurityProtectionDomainAccess from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
[Loaded java.security.ProtectionDomain$2 from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
[Loaded java.security.ProtectionDomain$Key from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
[Loaded java.security.Principal from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
[Loaded compiler.TestLoader from file:/home/xiwang/workspace/UltimateTest/bin/]
test
[Loaded compiler.A from file:/home/xiwang/workspace/UltimateTest/bin/]
inside of A
[Loaded java.lang.Shutdown from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
[Loaded java.lang.Shutdown$Lock from /usr/local/java/jdk1.6.0_34/jre/lib/rt.jar]
```

We can see the difference. A.class is loaded only when it is used.

#### A class is loaded:

- when the new bytecode is executed. For example, SomeClass f = new SomeClass();

- when the bytecodes make a static reference to a class. For example, System.out.


## When and how is a Java class initialized?

A class is initialized when a symbol in the class is first used. When a class is loaded it is not initialized.

JVM will initialize superclass and fields in textual order, initialize static, final fields first, and give every field a default value before initialization.

From [ProgramCreek](http://www.programcreek.com/2013/01/when-and-how-a-java-class-is-loaded-and-initialized/).
