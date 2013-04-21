---
layout: post
title: "Why Lambda Expressions in Java"
description: "<p class='justify'>Lambda expressions are coming to Java 8, but apparently they are still encountering some resistance and not all Java developers are convinced of their usefulness. In particular they say that it could be a mistake to try to add some functional features to Java, because they fear that this could compromise its strong object oriented and imperative nature. The purpose of this article is to hopefully remove any further doubt and show clearly, with practical and straightforward examples, why it is not possible for a modern programming language to not support lambda expressions.</p>"
category: java
tags: [lambda]
---
{% include JB/setup %}

<p class="justify">Lambda expressions are coming to Java 8, but apparently they are still encountering some resistance and not all Java developers are convinced of their usefulness. In particular they say that it could be a mistake to try to add some functional features to Java, because they fear that this could compromise its strong object oriented and imperative nature. The purpose of this article is to hopefully remove any further doubt and show clearly, with practical and straightforward examples, why it is not possible for a modern programming language to not support lambda expressions.</p>

* [Why We Need Lambda Expressions in Java - Part 1](http://java.dzone.com/articles/why-we-need-lambda-expressions)

* [Why We Need Lambda Expressions in Java - Part 2](http://java.dzone.com/articles/why-we-need-lambda-expressions)

Beautiful:

```java
public int sumAll(List<Integer> numbers, Predicate&<Integer> p) {
    int total = 0;
    for (int number : numbers) {
        if (p.test(number)) {
            total += number;
        }
    }
    return total;
}

sumAll(numbers, n -> true);
sumAll(numbers, n -> n % 2 == 0);
sumAll(numbers, n -> n > 3);

```
