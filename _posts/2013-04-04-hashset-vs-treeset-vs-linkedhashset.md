---
layout: post
title: "HashSet vs TreeSet"
description: "<p class='justify'>In a set, there are no duplicate elements. That is one of the major reasons to use a set. There are 3 commonly used implementations of Set in Java: HashSet, TreeSet and LinkedHashSet. When and which to use is an important question. In brief, if we want a fast set, we should use HashSet; if we need a sorted set, then TreeSet should be used; if we want a set that can be read by following its insertion order, LinkedHashSet should be used.</p>"
category: java
tags: [set, treeset]
---
{% include JB/setup %}

<p class="justify">In a set, there are no duplicate elements. That is one of the major reasons to use a set. There are 3 commonly used implementations of Set in Java: HashSet, TreeSet and LinkedHashSet. When and which to use is an important question. In brief, if we want a fast set, we should use HashSet; if we need a sorted set, then TreeSet should be used; if we want a set that can be read by following its insertion order, LinkedHashSet should be used. </p> 

## 1. Set Interface 

<p class="justify">Set interface extends Collection interface. In a set, no duplicates are allowed. Every element in a set must be unique. We can simply add elements to a set, and finally we will get a set of elements with duplicates removed automatically. </p> 

![diagram of Collection](/assets/images/2013/02/java-collection-hierarchy.jpeg)

## 2. HashSet vs. TreeSet vs. LinkedHashSet 

<p class="justify">HashSet is Implemented using a hash table. Elements are not ordered. The add, remove, and contains methods has constant time complexity O(1). TreeSet is implemented using a tree structure(red-black tree in algorithm book). The elements in a set are sorted, but the add, remove, and contains methods has  time complexity of O(log (n)). It offers several methods to deal with the ordered set like first(), last(), headSet(), tailSet(), etc.  LinkedHashSet is between HashSet and TreeSet. It is implemented as a hash table with a linked list running through it, so it provides the order of insertion. The time complexity of basic methods is O(1).  </p>  

## 3. TreeSet Example

```java
TreeSet tree = new TreeSet();
tree.add(12);
tree.add(63);
tree.add(34);
tree.add(45);

Iterator iterator = tree.iterator();
System.out.print("Tree set data: ");
while (iterator.hasNext()) {
    System.out.print(iterator.next() + " ");
}
```

Output is sorted as follows:

`Tree set data: 12 34 45 63`

Now let's define a Dog class as follows:

```java
class Dog {
	int size;

	public Dog(int s) {
		size = s;
	}

	public String toString() {
		return size + "";
	}
}
```

Let's add some dogs to TreeSet like the following:

```java
import java.util.Iterator;
import java.util.TreeSet;

public class TestTreeSet {
	public static void main(String[] args) {
		TreeSet dset = new TreeSet();
		dset.add(new Dog(2));
		dset.add(new Dog(1));
		dset.add(new Dog(3));

		Iterator iterator = dset.iterator();
		while (iterator.hasNext()) {
			System.out.print(iterator.next() + " ");
		}
	}
}
```

Compile ok, but run-time error occurs:

```
Exception in thread "main" java.lang.ClassCastException: 
collection.Dog cannot be cast to java.lang.Comparable 
at java.util.TreeMap.put(Unknown Source) 
at java.util.TreeSet.add(Unknown Source) 
at collection.TestTreeSet.main(TestTreeSet.java:22) 
```

Because TreeSet is sorted, the Dog object need to implement java.lang.Comparable's compareTo() method like the following:

```java
class Dog implements Comparable{
	int size;

	public Dog(int s) {
		size = s;
	}

	public String toString() {
		return size + "";
	}

	@Override
	public int compareTo(Dog o) {
	 &nbsp; &nbsp; &nbsp; &nbsp;return size - o.size;
	}
}
```

The output is: 

`1 2 3`

## 4. HashSet Example

```java
HashSet dset = new HashSet();
dset.add(new Dog(2));
dset.add(new Dog(1));
dset.add(new Dog(3));
dset.add(new Dog(5));
dset.add(new Dog(4));
Iterator iterator = dset.iterator();
while (iterator.hasNext()) {
	System.out.print(iterator.next() + " ");
}
```

Output:

`5 3 2 1 4`

Note the order is not certain. 

## 5. LinkedHashSet Example

```java
LinkedHashSet dset = new LinkedHashSet();
dset.add(new Dog(2));
dset.add(new Dog(1));
dset.add(new Dog(3));
dset.add(new Dog(5));
dset.add(new Dog(4));
Iterator iterator = dset.iterator();
while (iterator.hasNext()) {
	System.out.print(iterator.next() + " ");
}
```

The order of the output is *certain* and it is the insertion order. 

`2 1 3 5 4`

## 6. Performance testing

The following method tests the performance of the three class on add() method. 

```java
public static void main(String[] args) {
	Random r = new Random();

	HashSet hashSet = new HashSet();
	TreeSet treeSet = new TreeSet();
	LinkedHashSet linkedSet = new LinkedHashSet();

	// start time
	long startTime = System.nanoTime();
	for (int i = 0; i < 1000; i++) {
		int x = r.nextInt(1000 - 10) + 10;
		hashSet.add(new Dog(x));
	}
	// end time
	long endTime = System.nanoTime();
	long duration = endTime - startTime;
	System.out.println("HashSet: " + duration);
	
	// start time
	startTime = System.nanoTime();
	for (int i = 0; i < 1000; i++) {
		int x = r.nextInt(1000 - 10) + 10;
		treeSet.add(new Dog(x));
	}
	// end time
	endTime = System.nanoTime();
	duration = endTime - startTime;
	System.out.println("TreeSet: " + duration);

	// start time
	startTime = System.nanoTime();
	for (int i = 0; i < 1000; i++) {
		int x = r.nextInt(1000 - 10) + 10;
		linkedSet.add(new Dog(x));
	}
	// end time
	endTime = System.nanoTime();
	duration = endTime - startTime;
	System.out.println("LinkedHashSet: " + duration);

}
```

From the output below, we can clearly wee that HashSet is the fastest one. 

```
HashSet: 2244768 
TreeSet: 3549314 
LinkedHashSet: 2263320
```

From [DZone](http://java.dzone.com/articles/hashset-vs-treeset-vs) by [Ryan Wang](http://java.dzone.com/users/xiaoran-wang).



