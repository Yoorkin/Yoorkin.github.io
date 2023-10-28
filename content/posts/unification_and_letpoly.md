+++
title = '完全类型推导指南：Unification and Let polymorphism'
date = 2023-10-24T02:01:30+08:00
draft = false
+++

类型推导指编程语言自动推导出值的数据类型的能力。用大众所熟知的一种粗略的分类方法来说，它是“静态强类型”的编程语言在“编译期”为那些缺少了类型标注的变量或者函数的能力; 与“动态类型”的语言如Js、Python不同，这些缺少类型标注的程序并不需要在运行期间携带它们的类型信息和进行类型检查。近年来许多语言都把这种新潮特性作为宣传的卖点：

```
// C++ 11
auto x = 100; // type of x is `int`
```

```
// C# 9
Point p = new (3, 5); // create a object of Point class
```

程序员不用再不厌其烦地重复写类型了，好耶！但是，早在1973年就诞生过一门编程语言——ML，它不仅有类型推导，而且更激进：它的类型推导能力允许程序员完全不写类型而自动推断所有变量、函数、表达式的类型。比如这样一段ML代码：

```
fun fac 0 = 1
  | fac n = n * fac (n - 1)
```

其中fac是一个计算阶乘的函数，接受一个int作为输入，返回int。加上了类型标注的效果：

```
fun fac (0 : int) : int = 1
  | fac (n : int) : int = n * fac (n - 1)

```

当然你可能也注意到了ML的函数返回并不需要`return`。ML不存在“语句”，它的函数体是一个表达式。同样是表达式的还有“if语句”、“switch语句（match）”、“变量定义语句”，就像现在常宣传的“表达式语言”，这并不新鲜 :)。下面我们简单的认为所有语句、函数、变量都是表达式，就像ML一样：

- “if 语句”
```
val number1 = if true then 1 else 2 
```

- 函数
```
fun sum(x,y) = x + y
```

- “局部变量”

调用f返回a与b的和。

```
fun f(a,b) = let local = a in local + b
```

- “switch 语句”

```
fun 1 = 2
  | 2 = 3
  | 3 = 4
```

回到类型推断的话题上，如果你有使用当今这些带类型推导的语言的经验，你一定常常被某些例子困扰——编译器突然就报告推断不出类型了！一个典型的例子：

```
// 我不是c++
auto fib = [](auto x){
    if(x < 2){
        return x
    } else {
        return fib(x-1) + fib(x-2)
    }
}
```

我对这些语言的类型推导的实现有种极端的猜测：它们也许只是在局限在某些特定的位置如变量声明语句进行推断，如果左边缺少了类型信息，看看右边；如果右边缺少了类型信息，看看左边。当两边都无法单独归纳出一个类型时，编译器气馁地报告编译失败，需要用户多提供一些类型标注。它们缺少一些能力：把类型之间的关系传递到更广的范围、从循环依赖的类型关系中找到规律，就像解方程一样。这些在ML背后的类型推导算法Unification中都不是问题。

# 合一算法（Unification）

合一算法这个名字取自《编译原理》（也就是龙书）中的翻译。尽管没有程序员不知道“龙书”，但是却少有人注意到这个在角落里两页带过的算法，我第一次看到时也并不明白这个算法有什么用。你可以从Types and programing language（下称TAPL）的22.4章找到更详尽的解释。简单来说，它首先扫描整个程序，为每一个需要猜测类型的表达式赋予一个类型变量。然后从程序中收集类型变量之间的约束关系：

|表达式|类型变量|
|-|-|
|fib|a|
|[](auto x){if(x < 2){return x} else {return fib(x-1) + fib(x-2)}}| b|
|x|c|
|if(x < 2){return x} else {return fib(x-1) + fib(x-2)}|d|
|


# Let Polymorphism

## 简单的实现

## Algorithm J

# 完全类型推导？

## Hindley–Milner type system 和 System F

## Unification vs Bidirectional type checking

