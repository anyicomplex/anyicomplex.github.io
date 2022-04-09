---
title: "Writing C-style Java Programs"
description: "This article represents only my personal view, welcome to leave a message to discuss"
date: 2022-02-13T08:52:46-05:00
lastmod: 2022-03-26T10:23:15-04:00
draft: false
tags: [Java, C, C++]
categories: IT
---

# Feasibility

Java is said to be a pure object-oriented programming language, so can you write procedural-oriented C-style code in Java?  
**There are no pointers in Java, but there are references, so the answer is obviously yes.**

# The difference in style

Let's start with two pieces of pseudo-code.

## C style

```c
struct Foo foo;
change_foo_value(&foo, 0);
```

## Java style

``` java
Foo foo = new Foo();
foo.changeValue(0);
```
This also shows the difference between the two design patterns, object-oriented and procedure-oriented.  
Both styles are good, right?

# Problems during develop

If a method needs to return two values, how should I write the program?  
**Let the requirement be: execute a shell script in the program and get both the return code and the output.**

## C style

```c
int exec_script(char *script_path, char **output) {
	int exit_code;
	// Business logic
	...
	return exit_code;
}
```

## Java style

``` java
static class Result {
	public final int exitCode;
	public final String output;
	public Result(int exitCode, String output) {
		this.exitCode = exitCode;
		this.output = output;
	}
}

static Result execScript(String scriptPath) {
	int exitCode;
	StringBuilder outputBuffer = new StringBuilder();
	// Business logic
	...
	return new Result(exitCode, outputBuffer.toString());
}
```
What if we don't want to define a new class for this method in Java?  
Maybe we can take a page from C:
```java
static int execScript(String scriptPath, StringBuilder output) {
	int exitCode;
	// Business logic
	...
	return exitCode;
}
```
Or this:
``` java
static String execScript(String scriptPath, int[] exitCode) {
	StringBuilder outputBuffer = new StringBuilder();
	// Business logic
	...
	return outputBuffer.toString();
}
```

# Thoughts

This reminds me of the [Vala](https://wiki.gnome.org/Projects/Vala) programming language from the GNOME community :D