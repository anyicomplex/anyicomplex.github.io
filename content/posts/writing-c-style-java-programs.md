---
title: "用C语言的风格写Java程序"
date: 2022-02-13T08:52:46-05:00
lastmod: 2022-02-13T09:37:59-05:00
draft: false
tags: [Java, C/C++]
categories: IT
---

## 可行性
都说Java是纯面向对象的编程语言，那么能不能在Java中写面向过程风格的代码呢？  
**Java中虽然没有指针，但有引用，所以答案显然是可以的。**
## 风格的区别
先来看两段伪代码：    
### C语言风格
```c
struct Foo foo;
change_foo_value(&foo, 0);
```
### Java风格
```java
Foo foo = new Foo();
foo.changeValue(0);
```
这同样也能体现面向对象和面向过程两种设计模式的区别。  
两种风格都不错，是吧？
## 实际应用中的问题
如果某个方法需要返回两种值，该怎么写程序？  
**设需求为：用程序启动Shell脚本，获取脚本的返回值和输出。**
### C语言风格
```c
int exec_script(char *script_path, char *output) {
	int exit_code;
	// Business logic
	...
	return exit_code;
}
```
### Java风格
```java
class Result {
	public final int exitCode;
	public final String output;
	public Result(int exitCode, String output) {
		this.exitCode = exitCode;
		this.output = output;
	}
}

Result execScript(String scriptPath) {
	int exitCode;
	StringBuilder outputBuffer = new StringBuilder();
	// Business logic
	...
	return new Result(exitCode, outputBuffer.toString());
}
```
如果不想在Java中为这个方法新定义一个类，这时候该怎么办呢？  
也许我们可以借鉴一下C语言的风格：
```java
int execScript(String scriptPath, StringBuilder output) {
	int exitCode;
	// Business logic
	...
	return exitCode;
}
```
或者这样：
```java
String execScript(String scriptPath, int[] exitCode) {
	StringBuilder outputBuffer = new StringBuilder();
	// Business logic
	...
	return outputBuffer.toString();
}
```

## 总结
这让我想到了GNOME社区出品的[Vala](https://wiki.gnome.org/Projects/Vala)语言:D