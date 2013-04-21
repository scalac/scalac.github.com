---
layout: post
title: "Java vs Python"
description: "<p class='justify'>Some people have claimed that Python is more <b>productive</b> than Java. It is dangerous to make such a claim, because it may take several days to prove that throughly. From a high level view, Java is statically typed, which means all variable names have to be explicitly declared. In contrast, Python is dynamically typed, which means declaration is not required. There is a huge debate between dynamic typing and static typing in programming languages. This post does not talk about that. However, there is one thing that can be agreed – Python is an interpreted language with elegant syntax and that makes it a very good option for scripting and rapid application development in many areas.</p>"
category: java
tags: [java, python]
---
{% include JB/setup %}

<p class="justify">Some people have claimed that Python is more <b>productive</b> than Java. It is dangerous to make such a claim, because it may take several days to prove that throughly. From a high level view, Java is statically typed, which means all variable names have to be explicitly declared. In contrast, Python is dynamically typed, which means declaration is not required. There is a huge debate between dynamic typing and static typing in programming languages. This post does not talk about that. However, there is one thing that can be agreed – Python is an interpreted language with elegant syntax and that makes it a very good option for scripting and rapid application development in many areas.</p>

<p class="justify">In this comparison, I will try to cover some basic language components, such as string, control flow, class, inheritance, file i/o, etc. All of them will be compared by using side-by-side examples. I hope this can provide java programmers a general idea of how Python and Java do the same thing differently. By a glance of the code below, we can easily realize that Python code is much shorter, even though some Java “class shell” (In Java everything starts with a class definition) is not listed. This might be one reason why Python can be more productive.</p>

## Hello World 

Start with the simplest program. Java needs a lot of words for printing just a string. This is the first example showing Python is more concise.

```java
public class Main {
  public static void main(String[] args) {
     System.out.println("hello world");
   }
}
```

```python
print "hello world";
```

<p class="justify">Fist of all, whatever we do in Java, we need start with writing a class, and then put our desired method(s) inside. This is sometimes very annoying and it does waste time. In Python, you can simply start writing your code, and then run it.</p>


## String Operations

```java
public static void main(String[] args) {
  String test = "compare Java with Python";
	for(String a : test.split(" "))
	System.out.print(a);
}
```

```python
a="compare Python with Java";
print a.split();
```

There are a lot of string related functions in Python which is as good as or better than Java, for example, lstrip(), rstrip(), etc.

## Control Flow

```java
int condition=10;
 
//if
if(condition>10)
	System.out.println("> 10");
else
	System.out.println("<= 10");
 
//while
while(condition>1){
	System.out.println(condition);
	condition--;
}
 
//switch
switch(condition){
	case 1: 
	System.out.println("is 1"); 
	break;
	case 2: 
	System.out.println("is 2"); 
	break;
}
 
//for
for(int i=0; i<10; i++){
	System.out.println(i);
}
```

```python
condition=10;
 
# if
if condition > 10:
    print ">10";
elif condition == 10:
    print "=10";
else:
    print "<10";        
 
#while
while condition > 1:
    print condition;
    condition = condition-1;
 
#switch
def f(x):
    return {
        1 : 1,
        2 : 2,
    }[x]
print f(condition);
 
#for    
for x in range(1,10):
    print x;
```

## Class and Inheritance

```java
class Animal{
	private String name;
	public Animal(String name){
		this.name = name;
	}
	public void saySomething(){
		System.out.println("I am " + name);
	}
}
 
class Dog extends Animal{
	public Dog(String name) {
		super(name);
	}	
	public void saySomething(){
		System.out.println("I can bark");
	}
}
 
public class Main {
	public static void main(String[] args) {
		Dog dog = new Dog("Chiwawa");
		dog.saySomething();
 
	}
}
```

```python
class Animal():
        def __init__(self, name):
            self.name = name
 
        def saySomething(self):
            print "I am " + self.name    
 
class Dog(Animal):
        def saySomething(self):
            print "I am "+ self.name \
            + ", and I can bark"
 
dog = Dog("Chiwawa") 
dog.saySomething()
```
When you extend a base class, there is no requirement such as defining an explicit constructor for implicit super constructor.

## File I/O

```java
File dir = new File(".");// get current directory
File fin = new File(dir.getCanonicalPath() + File.separator
				+ "Code.txt");
FileInputStream fis = new FileInputStream(fin);
// //Construct the BufferedReader object
BufferedReader in = new BufferedReader(new InputStreamReader(fis));
String aLine = null;
while ((aLine = in.readLine()) != null) {
	// //Process each line, here we count empty lines
	if (aLine.trim().length() == 0) {
	}
}
 
// do not forget to close the buffer reader
in.close();
```

```python
myFile = open("/home/xiaoran/Desktop/test.txt")
 
print myFile.read();
```

As we can see that there are a lot of classes we need to import to simply read a file, and in addition, we have to handle the exception thrown by some methods. In Python, it is two lines.

## Collections

```java
import java.util.ArrayList;
 
public class Main {
	public static void main(String[] args) {
		ArrayList<String> al = new ArrayList<String>();
		al.add("a");
		al.add("b");
		al.add("c");
		System.out.println(al);
	}
}
```

```python
aList = []
aList.append("a");
aList.append("b");
aList.append("c");
print aList;
```

These comparisons only stand on the surface of Python, for real programming, the Python doc is still the best place to go for reference.

From [ProgramCreek](http://www.programcreek.com/2012/04/java-vs-python-why-python-can-be-more-productive/).